---
title: "Unifi - Manuální adopce zařízení"
date: "2024-06-25"
tags: 
  - "Unifi"
category: "Síť"
image: 
  path: "img/2024-06-25-unifi-manualni-adopt/ubnt-logo.jpg"
  alt: "UBNT"
---

Často se stává, že zařízení nelze adoptovat normání cestou přímo v Unifi Controlleru. Controller jej prostě z nějakého důvodu nevidí a nebo se zařízení nachází v jiné sub síti. V takových případech je nutné koncovému zařízení (switch, AP atd.) říct, kde přesně se jeho controller nachází.

Takzvaný set-inform je velmi důležitý nejenom při adopci zařízení, které prostě z nějakého důvodu controller nevidí, ale také při migraci controlleru, migraci sites a nebo pokud controller běží z cloudu.

## Nastavení Controlleru

Předpokládejme, že máme controller nastavený správně a ze sítě na něj jde vidět. Případným nesrovnalostem můžete předejít tak, že v nastavení controlleru přepíšete natvrdo adresu "Inform host" a povolíte, aby byl controller dohledatelný na L2 úrovni:
**Settings - > System -> Advanced -> Inform Host / Network Discovery** na adresu controlleru (tedy tu, co vidítě v adresním řádku) a zkontrolujete povolení discovery.

![inform-host-ip](/img/2024-06-25-unifi-manualni-adopt/inform-host-ip.png)
_zde se jedná o ip adresu, ale může se jednat i o dns název_

## Informování koncového zařízení

Příkaz "set-inform" jednoduše nasměruje dané zařízení na ten správný controller.
Budeme předpokládat, že vaše zařízení je vyresetováno do defaultu a nabízí se k adopci
- Legacy zařízení: žlutá barva LED
- Aktuální zařízení: bílá barva LED

> Mezi controllerem a koncovým zařízením by musí být vždy prostupný TCP port 8080
{: .prompt-warning }

### Příklad
Pro náš příklad budeme předpokládat, že koncové zařízení obdrželo od DHCP adresu `192.168.0.5` a controller se nachází na adrese `192.168.0.20`

### SSH
Na libovnolném zařízení, které se nachází ve stejné síti, jako koncové zařízení si spusťte Terminál a připojte se k zařízení (SW, AP atd.) pomocí výchozího jména `ubnt` a hesla `ubnt` na výchozím SSH portu `22`.
Zařízení si v síti můžete vyhledat pomocí libovolného IP scanneru.
Ve Windows terminálu bude formát takového příkazu vypadat takto:

```shell
 ssh ubnt@192.168.0.5 -p 22
```

- Následně potvrdíte fingerprint příkazem `yes`, dále výchozí heslo `ubnt` a měl by vás přivítat welcome screen vašeho unifi zařízení.
- Zařízení informujeme o adrese controlleru příkazem:

```shell
 set-inform http://192.168.0.20:8080/inform
```

![unifi-ssh](/img/2024-06-25-unifi-manualni-adopt/unifi-ssh.png)

- v této chvíli můžeme úplně opustit terminál pomocí příkazu `exit` a pokud tento magický packet doputoval až ke controlleru, tak se v něm zobrazí dané zařízení v "Unifi devices" s nabídkou `Adopt`
- po úspěšné adopci si zařízení přejímá přihlašovací údaje SSH z controlleru

### Nejběžnější unifi příkazy

- `info` - zobrazí informace o zařízení
- `set-default` - vyresetuje zařízení do továrního nastavení
- `upgrade https://<firmware-adresa>.bin` - upgraduje zařízení
- `fwupdate --url https://<firmware-adresa>.bin` - update fw
- `reboot` - restartuje zařízení
- `poweroff` - vypne zařízení
- `uptime` - ukáže jak dlouho je zařízení zapnuté

### Ostatní BusyBox příkazy

Na Unifi zařízení můžete vyvolávat i klasické shell příkazy, které by vám taky mohli pomoci s nastavením zařízení, zde je pár příkladů:

- `ifconfig` - vypíše nastavení interface
- `ip address add 192.168.0.5/24 dev br0` - nastavení statické IP adresy na výchozí bridge
- `ip route` - vypíše defaultní gw
- `ip route add default via 192.168.0.1` - nastavní výchozí gw na danou hodnotu
- `echo "nameserver 192.168.0.1" > /etc/resolv.conf` - nastaví DNS server
- `ping 1.1.1.1` - zkontroluje konektivitu na danou IP
- `arp -a` - zobrazí arp tabulku
- `ip neigh` - zobrazí okolní zařízení