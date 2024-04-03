---
layout: post
title: LTLM N7 - Instalace ROM
date: '2016-03-10 12:30:39'
tags:
- ltlm
- nezarazene
- unbrick
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Dnes se mi dostal do ruky tablet, který se v ČR prodával pod názvem [LTLM N7](https://www.alza.cz/ltlm-d7-d2040780.htm#alternativy)&nbsp;a&nbsp;samozřejmě se jedná o dovoz z Číny, kde se vyrábí pod názvem [MaPan MX710](http://www.maixin-china.net/software/MX710.html).

**HW specifikace** jsou:

> Model: A70X Allwinner A20 Tablet  
> CPU: ARM Cortex A7 1.2GHz dual core (Allwinner A20)  
> Display: 7″ LCD, 800×480  
> RAM: 512MB  
> ROM: interní paměť 4GB + microSDHC (do 32GB)  
> Konektivita: microUSB, USB 2.0, 2x webkamera, WiFi  
> OS: Google Android 4.2.2

[Český manuál](https://drive.google.com/file/d/0B3aDgwyDZ8ObU0Zxb2JpTTJWdnM/view?usp=sharing) k tomuto zařízení zařízení

### Problém:

Tento konkrétní kus se vždy při zapnutí zasekl na logu/nápise Android a odmítal naběhnout do systému.

### Recovery

Dobrou zprávou je, že tento model má již klasické android recovery, do kterého se dá dostat podržením kombinace kláves **power + volume down** (tlačítko zapnutí a zeslabení hlasitosti podržet po dobu 10s).

V recovery lze provést **wipe cache** a **wipe data/factory reset**. Poté můj tablet již naběhl až do systému, ale systém byl SW poškozen – hlásil chybu:  
„ **Aplikace Browser přestala pracovat** „.

### Instalace ROM

Proto jsem přistoupil k nahrání celé čisté ROM. Tuto ROM jsem nenašel od našeho českého pře-prodejce [LTLM](http://www.ltlm.cz/), který prostě neposkytuje pro své zařízení absolutně žádnou podporu.&nbsp;&nbsp;Poohlédl jsem se u výrobce chipsetu [Allwinner](http://www.allwinnertech.com/en/clq/processora/A20.html)&nbsp;a použil jeho nástroj i firmware s tímto postupem:

1. **Stáhněte** flash tool [PhoenixSuit](http://www.maxxx.cz/download/phoenixsuit-1-10/), [firmware](https://mega.nz/#!LgBhTCrK!Av7OPEHRJtImszz73JySQKh7eHRd8chZh71fl-PJr8k) a rozbalte.
2. Poté spusťte instalaci driverů s oprávněním správce&nbsp;**Phoenix(Drv)Install.exe**
3. V tabletu povolte **ladění USB**  
Nastavení – Pro vývojáře – ladění USB
4. Spusťte&nbsp; **PhoenixSuit.exe** (s oprávněním správce) – ten by měl detekovat váš tablet.  
 ![](http://192.168.20.2/wordpress/wp-content/uploads/2016/03/phoenixsuite.png)
5. Nyní přejděte do záložky **firmware** klikněte na **image** a vyhledejte:  
„_PH\_A70X\_auto\_auto\_gc0309-gc0309\_81xx\_20131107.img_„
6. Následně klikněte na „ **upgrade** “ a „ **YES** “ (format upgrade mode)
7. Počkejte než se tablet upgraduje a pak klikněte na „ **OK** “  
 ![](http://192.168.20.2/wordpress/wp-content/uploads/2016/03/phoenixsuite2.png)

> Pokud váš systém vůbec nenaběhne a nemůžete povolit ladění USB, tak lze celý postup provádět z recovery. (V recovy by se měl váš tablet taktéž detekovat jako ADB Device!)

Nyní by mělo být **hotovo!** Tablet po spuštění spustí automaticky program na kalibraci otáčení obrazovky – ten můžete ukončit. V nastavení bude nutné nastavit český jazyk.

Rom je čistá bez LTLM spouštěcích animací, v systému jsou předinstalovány jen Adobe Flash, Reader a Chrome, které lze bez problémů odinstalovat a [Go Weather EX](https://play.google.com/store/apps/details?id=com.gau.go.launcherex.gowidget.weatherwidget), [Tranparent weather clock](https://play.google.com/store/apps/details?id=com.droid27.transparentclockweather) – které můžete buďto updatovat (skrze Google Play) a používat nebo deaktivovat.

[![](http://192.168.20.2/wordpress/wp-content/uploads/2016/03/20160310_114627-scaled-1-577x1024-1-169x300.jpg)](http://192.168.20.2/wordpress/wp-content/uploads/2016/03/20160310_114627-scaled-1-577x1024-1.jpg)

Alternativně by mělo jít použít **LiveSuit** s firmwarem [MaPan\_MX710\_Android\_Jelly\_Bean\_4.2.2\_Os\_Root\_Firmware\_20131023](https://mega.nz/#!jppg2YZL!wTiijZ_1qF27SB1OIIG6OOhy2v4KgzWmSwBaEhPy0Aw)

**Známe chyby:**

- Nelze změnit domovskou stránku (Baidu) ve vestavěném prohlížeči.  
Prohlížeč nelze ani zakázat, takže řešením je [použít alternativu](https://play.google.com/store/search?q=browser&c=apps&docType=1&sp=CAFiCQoHYnJvd3NlcnoFGADAAQKKAQIIAQ%3D%3D:S:ANO1ljLt524)
- Na některých revizích nefunguje kamera  
Řešením je instalace&nbsp;camera.apk z externího zdroje
<!--kg-card-end: html-->