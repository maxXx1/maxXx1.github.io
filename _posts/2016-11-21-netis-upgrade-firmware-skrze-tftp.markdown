---
layout: post
title: Netis - upgrade firmware skrze TFTP
date: '2016-11-21 13:38:33'
tags:
- fw
- netis
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Tento postup se používá k oživení routerů různých značek při specifických problémech. Například, když vaše zařízení nebootuje nebo je jeho managment skrze webové rozhraní nedostupný. Osobně jsem se setkal i s několika případy divného chování routeru této značky (Série WF24XX), které se vrátili z reklamace funkční a jediným zásahem bylo, přehrání firmware pomocí této metody.

Během této operace by měl být váš anti-virový program dočasně vypnutý, protože by mohl tento proces blokovat.

1. Na stránkách [netis-systems.com](http://netis-systems.com/)&nbsp;stáhněte aktuální firmware pro váš typ zařízení. (V mém případě WF2419).
2. Stáhněte program [TFTPD](http://tftpd32.jounin.net/tftpd32_download.html)&nbsp;(postačí standard edition) a nainstalujte.
3. Spusťte program TFTPD32 (nebo TFTPD64) **s oprávněním správce**.
4. Na vašem počítači (rozhraní Ethernet) si nastavte statickou IP adresu&nbsp; **192.168.1.5&nbsp;** a ujistěte se, že je vypnuté rozhraní wifi.
5. Připojte síťový kabel do zásuvky označené **LAN4** a propojte s počítačem.
6. Router odpojte od napájení.
7. Držte (pomocí sponky nebo tužky) tlačítko reset po dobu alespoň **2-3 sec** a připojte napájení.
8. Po připojení napájení pusťte tlačítko reset.  
Router by měl být v „boot mode“ to poznáte tak, že pouze kontrolka **LAN4 a Power LED blikají**.
9. V programu TFTPD vyberte záložku „ **TFTP Client** “ a nastavte:  
**Host:** 192.168.1.6  
**Local file:** Umístění staženého souboru aktuálního firmware.
10. Poté klikněte na tlačítko „ **Put** „
11. Po úspěšném uploadu firmware do vašeho zařízení se vám zobrazí informační okno.
12. **Počkejte 1-2 minuty** dokud vidíte všechny LEDky blikat a pak zařízení odpojte od napájení.
13. Po opětovném připojení routeru k napájení zkontrolujte jestli vše funguje jak má.  
**Wifi síť:** Netis **heslo:** password  
**Web managment:** 192.168.1.1
14. Nezapomeňte zrušit ruční nastavení Ethernetu.
<figure class="is-layout-flex wp-block-gallery-1 wp-block-gallery columns-3 is-cropped"><ul class="blocks-gallery-grid">
<li class="blocks-gallery-item"><figure><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161121121448.png"><img decoding="async" loading="lazy" width="391" height="334" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161121121448.png" alt="" data-id="4329" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161121121448.png" data-link="https://maxxx.cz/?attachment_id=4329" class="wp-image-4329" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161121121448.png 391w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161121121448-300x256.png 300w" sizes="(max-width: 391px) 100vw, 391px"></a></figure></li>
<li class="blocks-gallery-item"><figure><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161121123303.png"><img decoding="async" loading="lazy" width="391" height="334" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161121123303.png" alt="" data-id="4331" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161121123303.png" data-link="https://maxxx.cz/?attachment_id=4331" class="wp-image-4331" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161121123303.png 391w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161121123303-300x256.png 300w" sizes="(max-width: 391px) 100vw, 391px"></a></figure></li>
<li class="blocks-gallery-item"><figure><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161121132108.png"><img decoding="async" loading="lazy" width="391" height="334" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161121132108.png" alt="" data-id="4332" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161121132108.png" data-link="https://maxxx.cz/?attachment_id=4332" class="wp-image-4332" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161121132108.png 391w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161121132108-300x256.png 300w" sizes="(max-width: 391px) 100vw, 391px"></a></figure></li>
<li class="blocks-gallery-item"><figure><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161121122022.png"><img decoding="async" loading="lazy" width="400" height="455" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161121122022.png" alt="" data-id="4330" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161121122022.png" data-link="https://maxxx.cz/?attachment_id=4330" class="wp-image-4330" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161121122022.png 400w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161121122022-264x300.png 264w" sizes="(max-width: 400px) 100vw, 400px"></a></figure></li>
</ul></figure>

**Pozn.&nbsp;** U některých novějších verzí FW routerů značky Netis je program TFTPD32 přibalen přímo v archívu pod názvem „How to use TFTP Upgrade the Firmware of router“ i se stručným návodem v angličtině.

<!--kg-card-end: html-->