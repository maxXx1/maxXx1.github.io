---
layout: post
title: Instalace OpenWRT na TP-Link TL-WR841ND
date: '2014-09-18 19:34:00'
tags:
- open-wrt
- tp-link
- hash-wordpress
- hash-import-2023-08-28-13-25
---

V poslední době se zase objevuje více a více [zavirovaných routerů](http://blog.trendmicro.com/trendlabs-security-intelligence/mobile-devices-used-to-execute-dns-malware-against-home-routers/). Nyní se teda nejedná o technický problém, jako tomu bylo v případě chyby [rom-0](https://www.maxxx.cz/2014/06/13/zranitelnost-rom-0-na-vlastni-kuzi/), ale pouze o selhání lidského faktoru (výchozí nebo žádné heslo pro vstup do administrace). V rámci řešení bezpečnostních problémů u zákazníků (aktualizace FW, kontrola přístupových údajů a správnosti DNS) se vyřazovali starší kusy routerů.

Dostal se mi do ruky dlouhodobě velmi populární router [TP-Link&nbsp;TL-WR841N](http://cz.tp-link.com/download/TL-WR841N_V5.html)D&nbsp;ve verzi v5, která se začala prodávat někdy v roce&nbsp;2010 a během stejného roku byla nahrazena HW revizí v6. Problém tohoto routeru (důvod vyřazení) je, že tato hw revize je ze strany výrobce nepodporována (viz. odkaz výše).

[![fw-update](https://www.maxxx.cz/wp-content/uploads/2016/10/fw-update.png)](https://www.maxxx.cz/wp-content/uploads/2016/10/fw-update.png)

> **HW specifikace**
> 
> SoC:&nbsp;AR7240 rev 2  
> Frekvence:&nbsp;400 MHz  
> Výrobce flash chipu: Hynix  
> Velikost flash:&nbsp;4 MB  
> Typ RAM:&nbsp;Hynix HY5DU561622FTP-5  
> Velikost RAM:&nbsp;32 MB  
> Wifi:&nbsp;Atheros AR9280 Rev:2  
> Ethernet:&nbsp;AR7240 built-in  
> USB: není  
> Kondenzátory: nějaký čínský shit

[![img_20161010_144317](https://www.maxxx.cz/wp-content/uploads/2016/10/IMG_20161010_144317-1024x576.jpg)](https://www.maxxx.cz/wp-content/uploads/2016/10/IMG_20161010_144317.jpg)

Po HW stránce byl router v pořádku, po té SW to byla katastrofa. Prehistorické webové rozhraní chtělo po každé změně restart zařízení, několikrát mě to vyhodilo přímo z administrace s tím, že se musím znova přihlásit atd. Zákazníkem udávaná závada byla nemožnost připojení k WiFi. Rozhodl jsem se tedy, že místo generovaní elektro odpadu ho zkusím po vzoru&nbsp;[TL-WR741ND](https://www.maxxx.cz/2016/02/11/tl-wr741nd-dd-wrt/) oživit.

### OpenWrt 15.05.1 (Chaos Calmer)

K mému překvapení jsem na stránce podpory [OpenWrt](https://wiki.openwrt.org/toh/tp-link/tl-wr841nd)zjistil, že pro můj model (a HW revizi) je dostupná [poslední verze](https://forum.openwrt.org/viewtopic.php?pid=315110#p315110) jejich alternativního FW. Tak jsem se rozhodl ji vyzkoušet.

Poslední verze je již v základu vybavena webovým prostředím LuCi. Není tudíž nutné použití SSH příkazů ani Telnetu při prvním spuštění po nahrání OpenWrt.

### Instalace

1. Nejprve překontrolujeme **hw revizi** na spodní straně zařízení.  
[![img_20161010_144039](https://www.maxxx.cz/wp-content/uploads/2016/10/IMG_20161010_144039-1024x576.jpg)](https://www.maxxx.cz/wp-content/uploads/2016/10/IMG_20161010_144039.jpg)
2. **Pokud máte verzi 1.x až 10.x, tak můžete pokračovat dále.** Pokud máte verzi verzi 11.x, tak již bohužel OpenWrt nenainstalujte, protože [podléhá regulaci](https://www.root.cz/clanky/regulace-routeru-zakazou-nam-openwrt/).
3. Na [OpenWrt wiki](https://wiki.openwrt.org/toh/tp-link/tl-wr841nd), přesněji na stránce věnované všem revizím vašeho zařízení&nbsp;stáhněte [OpenWrt Install Image verze 5](https://downloads.openwrt.org/chaos_calmer/15.05.1/ar71xx/generic/openwrt-15.05.1-ar71xx-generic-tl-wr841nd-v5-squashfs-factory.bin).
4. Stažený soubor _„openwrt-15.05.1-ar71xx-generic-tl-wr841nd-v5-squashfs-factory.bin“_ přejmenujte např.&nbsp;na _„openwrt.bin“,_ protože starší HW revize mají problém s adresou delší než 64 znaků.
5. Nyní **proveďte HARD RESET** vašeho routeru pomocí tlačítka, které se nachází na zadní straně&nbsp;(nejlépe tužkou nebo párátkem po dobu alespoň 10s).
6. Vaše resetované zařízení **připojte pouze k napájení a** propojte ho ethernetovým kabelem **k počítači** na kterém máte _„openwrt.bin“_.

> **Přihlaste se do webové administrace** – ale neměňte žádné nastavení!  
>   
> Adresa: [192.168.1.1](http://192.168.1.1/)  
> Uživatel: admin  
> Heslo: admin

1. V menu&nbsp;webového rozhraní routeru zvolte **System tools** – **Firmware Upgrade&nbsp;** následně&nbsp; **Browse** ,&nbsp;vyberte vámi stažený soubor _„openwrt.bin“_ a klikněte na tlačítko&nbsp; **Upgrade**.
2. Teď už stačí jen čekat na dokončení upgrade.&nbsp;Dojde k odpojení routeru od počítače, dokončení instalace poznáte na tom, že se Vám opět aktivuje síťové připojení v počítači.
3. Nyní zkuste obnovit stránku ([http://192.168.1.1/](http://192.168.1.1/)). Nyní by se měla již zobrazit přihlašovací obrazovka GUI LuCi.  
[![openwrt](https://www.maxxx.cz/wp-content/uploads/2016/10/openwrt-1024x439.png)](https://www.maxxx.cz/wp-content/uploads/2016/10/openwrt.png)
4. Pokud se přihlašovací dialog zobrazí, můžete rovnou kliknout na **„Go to password configuration“** , kde si nastavíte vlastní heslo k přihlašovacímu jménu root.
5. Blahopřeji! Máte doma Linuxový router 🙂
<!--kg-card-end: html-->