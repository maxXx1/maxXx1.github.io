---
layout: post
title: Výměna WiFi karty na ThinkPadu - Error 1802
tags:
- hash-wordpress
- hash-import-2023-08-28-13-25
---

_Dneska jsem měnil wifi kartu na IBM ThinkPad T42 a čekalo mě nemilé překvapení…_  
  
V tomto kousku byl starší wifi modul připojený přes mini PCI nepodporující nové standardy (a/b/g) a proto se majitel rozhodl kartu nechat vyměnit. Není se čemu divit vzhledem ke stáří tohoto modelu. Nepochybuji o tom, že v tehdejší době byl obsažený modul (výrobce Samsung) špičkou na trhu avšak dnes je již jeho výkon nedostatečný.

<!--more-->

Rozhodl jsem se ho nahradit modulem&nbsp;[Intel PRO/Wireless 2915abg Mini PCI](http://support.lenovo.com/en_US/downloads/detail.page?DocID=DS003878)&nbsp;nejenom proto, že jsem ho měl zrovna po ruce (použitý, vytažen z počítače, který již odešel do křemíkového nebe), ale také proto, že na stránkách IBM jsou na něj oficiální ovladače. A hlavně podporuje dané standardy a/b/g. Tudíž velmi zvýší citlivost signálu.

Problém nastal hned po prvním spuštění po výměně modulu, protože ThinkPad si hlídá to, jakými komponenty je osazen. Postrádá to sice logiku a v dnešní době jsem se s tím již u žádného výrobce nesetkal. S kompatibilitou nemá problém, spíše se jedná o brzdu proti neservisním zásahům. To že detekoval jinou kartu a nehodlá s ní spolupracovat, ba co víc ani pokračovat v bootování mi dal jasně najevo chybovou hláškou:

_„ERROR 1802: Unauthorized network card is plugged-in. Power off and removed miniPCI network card.“_  
  
Naštěstí minimálně pro mnoho modelů včetně T42 (podrobný seznam modelů na [thinkwiki](http://www.thinkwiki.org/wiki/Problem_with_unauthorized_MiniPCI_network_card)) existuje jednoduchá ultilitka, která tento problém řeší. Pro ostatní modely je to trochu složitější, ale na thinkwiki jsem našel mnoho návodů.

U tohoto modelu (a jemu podobných) stačí pouze stáhnout malé [ISO](http://www.maxxx.cz/download/no-1802-iso/), poté ho vypálit. Doporučuji přepisovatelné CD (CD-RW) nebo vytvořit bootovatelný flash disk (max 512MB, FAT32), protože ultilita má pouze něco kolem 6MB. Nyní z něho staří nabootovat a napsat příkaz:  
„no-1802„  
Pod kterým se skrývá 18ti bytes dlouhý .com soubor, který nastaví nejvyšší byt v CMOS na adrese 0x6a.

[![](http://3.bp.blogspot.com/-4YPwObUxFeU/UfA2B6WOtmI/AAAAAAAADMU/DLvqQrYHrII/s320/20079.jpg)](http://3.bp.blogspot.com/-4YPwObUxFeU/UfA2B6WOtmI/AAAAAAAADMU/DLvqQrYHrII/s1600/20079.jpg)

**Tuto úpravu musíte provádět dokud je v počítači původní karta** , po provedení této úpravy stačí notebook vypnout a přistoupit k vlastní výměně.

Pro novější modely (ThinkPad T43/T43p/R52/X41) je již nutná úprava biosu. O upravený BIOS si si můžete požádat na fóru [mydigitallife.info](http://forums.mydigitallife.info/threads/5866-LENOVO-(IBM)-Bioses-especially-Thinkpad/page218?p=344779#post344779), kde se zabývali i konkrétně touto chybou.

Podobnou chybou trpí i starší notebooky HP, avšak u nich je úprava o něco složitější. Více na&nbsp;[Hacking BIOS HP Pavilion – whitelist](http://airdump.cz/hacking-bios-hp-pavilion/). (návod v češtině)

<!--kg-card-end: html-->