---
title: Wireguard VPN mezi Unifi a Mikrotikem
date: 2025-11-03
tags:
  - Mikrotik
  - Unifi
category: Síť
image:
  path: "/img/2024-10-18-unifi-mikrotik-s2s-ipsec/mikrotik-unifi.png"
  alt: Wireguard
---

Dlouhou dobu jsem řešil, jak spravovat zařízení Mikrotik vzdáleně. Mám jich požehnaně, ale nejedná se úplně o zařízení zákazníků - spíše rodina a kamarádi. Nikdy jsem neměl ambice tvořit vzdálený přístup do těchto sítí. Pouze na gateway bez veřejné IP adresy, mnohdy schované za NATem poskytovatele. 

# Unifi Network

## 1. Vytvoření WireGuard serveru

Nastavení → VPN → VPN Server → Vytvořit nový

 - Typ: WireGuard
 - Název: WG na Mikrotiky
 - Adresa serveru: `Rozhraní WAN`
 - Port `51825`
 - IP Brány: `192.168.3.1` (Rozsah /24)

## 2. Vytvoření peeru (Klienta)

Klienti → Přidat klienta

 - Název: Mikrotik 1
 - Autorizace: Ruční
 - IP rozhraní: 192.168.3.x
 - Předsdílený klíč: není třeba
 - Sítě vzdáleného klienta: také není třeba

## Konfigurační soubor

Pokud v tomto kroku stáhnete konfigurační soubor `nazev.conf`, tak jej na Mikrotiku v novější verzi můžete prostě importovat a tím přeskočit kroky se zakládáním rozhraní a peeru.

# Mikrotik RouterOS

## 1. Vytvoření WireGuard rozhraní

```shell
/interface wireguard add name=wg1 listen-port=51825
```

`listen-port` můžeš nechat defaultní nebo nastavit jiný – není důležitý pro klienta, pokud nečeká příchozí spojení.

## 2. Nastavení IP adresy na WG rozhraní

```shell
/ip address add address=192.168.3.2/24 interface=wg-unifi
```

Tohle je IP Mikrotiku v rámci WireGuard subnetu.

## 3. Přidání peeru (Na Unifi)

```shell
/interface wireguard peers add interface=wg-unifi \
public-key="PUBLIC_KEY_UNIFI_WG" \
endpoint-address="VEREJNA_IP_UNIFI_WG" \
endpoint-port=51825 \
allowed-address=192.168.3.1/32,"ADRESA_VNITRNI_SITE_UNIFI/24" \
persistent-keepalive=25
```

Nahraď `PUBLIC_KEY_UNIFI_WG` veřejným klíčem Unifi a `VEREJNA_IP_UNIFI_WG` IP adresou Unifi.  
`allowed-address` říká, že provoz na Unifi (`192.168.3.1`) a z jeho `VNITRNI_SITE` půjde přes tunel.

## 4. Firewall pravidlo (pokud máš aktivní firewall)

/ Mikrotik defaultně nemá blokující pravidla, ale pro jistotu:

```shell
/ip firewall filter add chain=input action=accept src-address=192.168.3.0/24 
/ip firewall filter add chain=forward action=accept src-address=192.168.3.0/24
```

Tím povolíš provoz z WireGuard subnetu.

## 5. Statická trasa zpět na Unifi

```shell
/ip route add dst-address="ADRESA_VNITRNI_SITE_UNIFI/24" gateway=192.168.3.1
```

Bez této trasy Mikrotik neví, kam poslat odpovědi na zařízení z LAN UCG-Fiber.
