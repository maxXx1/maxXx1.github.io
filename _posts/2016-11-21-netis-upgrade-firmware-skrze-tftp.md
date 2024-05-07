---
title: "Netis - upgrade firmware skrze TFTP"
date: "2016-11-21"
category:
  - "Síť"
tags: 
  - "Netis"
image: 
    path: "/img/2016-11-21-netis-upgrade-firmware-skrze-tftp/wf2419d.png"
    alt: Netis WF2419D
---

Tento postup se používá k oživení routerů různých značek při specifických problémech. Například, když vaše zařízení nebootuje nebo je jeho managment skrze webové rozhraní nedostupný. Osobně jsem se setkal i s několika případy divného chování routeru této značky (Série WF24XX), které se vrátili z reklamace funkční a jediným zásahem bylo, přehrání firmware pomocí této metody.

Během této operace by měl být váš anti-virový program dočasně vypnutý, protože by mohl tento proces blokovat.

1. Na stránkách [netis-systems.com](https://netis-systems.com/) stáhněte aktuální firmware pro váš typ zařízení. (V mém případě WF2419).
2. Stáhněte program [TFTPD](https://tftpd32.jounin.net/tftpd32_download.html) (postačí standard edition) a nainstalujte.
3. Spusťte program TFTPD32 (nebo TFTPD64) **s oprávněním správce**.
4. Na vašem počítači (rozhraní Ethernet) si nastavte statickou IP adresu `192.168.1.5` a ujistěte se, že je vypnuté rozhraní wifi.<br>
![tcpip](/img/2016-11-21-netis-upgrade-firmware-skrze-tftp/snip_20161121122022.png)
5. Připojte síťový kabel do zásuvky označené **LAN4** a propojte s počítačem.
6. Router odpojte od napájení.
7. Držte (pomocí sponky nebo tužky) tlačítko reset po dobu alespoň **2-3 sec** a připojte napájení.
8. Po připojení napájení pusťte tlačítko reset.  
    Router by měl být v "boot mode" to poznáte tak, že pouze kontrolka **LAN4 a Power LED blikají**.
9. V programu TFTPD vyberte záložku "**TFTP Client**" a nastavte:  
    **Host:** `192.168.1.6`  
    **Local file:** Umístění staženého souboru aktuálního firmware.
10. Poté klikněte na tlačítko "**Put**"
11. Po úspěšném uploadu firmware do vašeho zařízení se vám zobrazí informační okno.
![tftpd](/img/2016-11-21-netis-upgrade-firmware-skrze-tftp/snip_20161121121448.png)
![tftpd2](/img/2016-11-21-netis-upgrade-firmware-skrze-tftp/snip_20161121123303.png)
![tftpd3](/img/2016-11-21-netis-upgrade-firmware-skrze-tftp/snip_20161121132108.png)
12. **Počkejte 1-2 minuty** dokud vidíte všechny LEDky blikat a pak zařízení odpojte od napájení.
13. Po opětovném připojení routeru k napájení zkontrolujte jestli vše funguje jak má.  

>**Wifi síť:** `Netis` **heslo:** `password`  
>**Web managment:** `192.168.1.1`
{: .prompt-info }

Nezapomeňte zrušit ruční nastavení Ethernetu.

**Pozn.** U některých novějších verzí FW routerů značky Netis je program TFTPD32 přibalen přímo v archívu pod názvem "How to use TFTP Upgrade the Firmware of router" i se stručným návodem v angličtině.
