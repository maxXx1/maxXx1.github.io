---
title: "IPsec site-to-site VPN mezi Unifi USG a Mikrotikem"
date: "2024-10-18"
tags: 
  - "Mikrotik"
  - "Unifi"
category: "Síť"
image: 
  path: "/img/2024-10-18-unifi-mikrotik-s2s-ipsec/mikrotik-unifi.png"
  alt: "Site-to-site"
---

# Jak vytvořit IPsec site-to-site VPN mezi Unifi USG a Mikrotikem

#### Použitý hardware a verze software
 - Unifi USG-Ultra v4.0.20
 - Network aplikace v8.5.6
 - Mikrotik RBD52G-5HacD2HnD (arm)
 - RouterOS v7.8

## Konfigurace Mikrotiku ve Winboxu
___
### Záložka: IP -> IPsec -> Peers

| Přidat nový          |                                       |
| -------------------- | ------------------------------------- |
| Enabled              | ✓                                     |
| Name                 | USG-01                                |
| Address              | Veřejná IP na WANu našeho USG         |
| Port                 | prázné                                |
| Local Address        | Veřejná IP na WANu našeho Mikrotiku   |
| Profile              | default (následně změnit na profile1) |
| Exchange Mode        | main                                  |
| Passive              | ne                                    |
| Send INITIAL_CONTACT | ano                                   |

![peer](/img/2024-10-18-unifi-mikrotik-s2s-ipsec/ipsec-peer.png)

### Záložka: IP -> IPsec -> Profiles

| Nový profil          |                                  |
| -------------------- | -------------------------------- |
| Name                 | profile1                         |
| Hash Algorithms      | sha1                             |
| Encryption Algorithm | aes-128                          |
| DH Group             | modp1024 (=DH Group 2), modp2048 |
| Proposal Check       | obey                             |
| Lifetime             | 1d 00:00:00                      |
| Lifebytes            | prázdné                          |
| Nat Traversal        | ne (pokud není za NATem)         |
| DPD Interval         | 60s                              |
| DPD Maximum Failures | 5                                |

![profile](/img/2024-10-18-unifi-mikrotik-s2s-ipsec/ipsec-profile.png)

### Záložka: IP -> IPsec -> Identities

| Přidat nový           |                      |
| --------------------- | -------------------- |
| Enabled               | ✓                    |
| Peer                  | USG-01               |
| Auth. Method          | pre shared key       |
| Secret                | nakopírujte váš klíč |
| Policy Template Group | default              |
| Notrack Chain         | prázdné              |
| My ID Type            | auto                 |
| Remote ID Type        | auto                 |
| Match By              | remote id            |
| Mode Configuration    | prázdné              |
| Generate Policy       | no                   |

![identity](/img/2024-10-18-unifi-mikrotik-s2s-ipsec/ipsec-identity.png)

### Záložka: IP -> IPsec -> Proposals

| Přidat nový      |              |
| ---------------- | ------------ |
| Enabled          | ✓            |
| Name             | proposal-usg |
| Auth. Algorithms | sha1         |
| Encr. Algorithms | aes-128 cbc  |
|                  | aes-256 cbc  |
|                  | aes-128 ctr  |
| Lifetime         | prázdné      |
| PFS Group        | modp1024     |

![proposal](/img/2024-10-18-unifi-mikrotik-s2s-ipsec/ipsec-proposal.png)

### Záložka: IP -> IPsec -> Policies
* Zakázat default

| Přidat nový IPsec Policy |                                                                                                               |
| ------------------------ | ------------------------------------------------------------------------------------------------------------- |
| Enabled                  | ✓                                                                                                             |
| Src. Address             | Adresa interní Mikrotik sítě (celé sítě např. 192.168.1.0/24)                                                 |
| Src. Port                | prázdné                                                                                                       |
| Dst. Address             | Adresa interní USG sítě                                                                                       |
| Dst. Port                | prázdné                                                                                                       |
| Protocol                 | 255 (all)                                                                                                     |
| Action                   | encrypt                                                                                                       |
| Level                    | unique ( Default je "require", ale pokud chcete navázat připojení z více subnetů, tak potřebujete "unique". ) |
| IPsec Protocols          | esp                                                                                                           |
| Tunnel                   | ano                                                                                                           |
| SA Src. Address          | Mikrotik WAN addresa                                                                                          |
| SA Dst. Address          | USG WAN addresa                                                                                               |
| Proposal                 | proposal-usg                                                                                                  |

### Záložka: IP -> Firewall -> NAT

| Nové NAT Rule |                   |
| ------------- | ----------------- |
| Chain         | srcnat            |
| Src. Address  | LAN síť Mikrotiku |
| Dst. Address  | LAN síť USG       |
| Action        | Accept            |

* Postuňte pravidlo ve firewallu nahoru.

## Konfigurace Unifi

### Settings -> VPN -> Site-to-Site VPN -> Create New 

| VPN Type         | IPsec                                 |
| ---------------- | ------------------------------------- |
| Name             | mikrotik-usg-vpn                      |
| Pre-Shared Key   | do IP -> IPsec -> Identities - Secret |
| Local IP         | WAN port na kterém je veřejná IP      |
| Remote IP / Host | Veřejná IP na WANu Mikrotiku          |

| Network Configuration |                                           |
| --------------------- | ----------------------------------------- |
| VPN Type              | Route based                               |
| Tunel IP              | ne                                        |
| Remote Network(s)     | Static                                    |
| Subnet                | Adresa interní Mikrotik sítě (x.x.x.0/24) |

| **Advanced Options** | Manual |
| Key Exchange Version | IKEv1
| IKE Encryption | AES-128
| IKE Hash | SHA1
| DH Group | 2 (14 je default)
| Lifetime | 28800
| ESP Encryption | AES-128
| ESP Hash | SHA1
| DH Group | 2
| Lifetime | 3600
| PFS | ano, povolit Prefect Forward Secrecy
| Local Authentication ID | Auto
| Remote Authentication ID | Auto
| Maximum Transmission Unit | Auto
| Route Distance | 30 je default |

![site-to-site](/img/2024-10-18-unifi-mikrotik-s2s-ipsec/usg-ipsec.png)

Pokud vše půjde jak má, tak na Mikrotiku bude vidět, jak si zařízení vyměnily certifikáty

### Mikrotik -> IPsec -> Installed SAs

|     | SPI      | Src. Address     | Dst. Address     | Auth. Algorithm | Encr. Algorithm | Encr. Key Size | Current Bytes |
| --- | -------- | ---------------- | ---------------- | --------------- | --------------- | -------------- | ------------- |
| EH  | xy123z4  | WAN IP Unifi     | WAN IP Mikrotiku | sha1            | aes cbc         | 128            | 123000        |
| EH  | x012y3z4 | WAN IP Mikrotiku | WAN IP Unifi     | sha1            | aes cbc         | 128            | 321000        |

Zdroje: [Github/iisti](https://github.com/iisti/how-to-usg-mikrotik-ipsec-vpn) a [Willie Howe](https://www.youtube.com/watch?v=70EIA4bF820)
