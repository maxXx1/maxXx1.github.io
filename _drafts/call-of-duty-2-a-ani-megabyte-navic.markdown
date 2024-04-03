---
layout: post
title: Call of Duty 2 a ani megabyte navíc
tags:
- cod
- config
- windows
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Určitě se na internetu povalují různé portable verze této slavné hry, ale není nad to když si člověk něco udělá sám. Proto bych Vás rád provedl způsobem jak Call of Duty 2 osekat na **pouhý Multiplayer** a tím ušetřit velké množství místa např. pro přenos na flash discích do škol či zaměstnání, kde je zakázáno instalovat hry.

Tímto samozřejmě nechci nikoho nabádat k tomu, aby ve škole místo výuky dělal něco jiného než má. I když přesně toto byl důvod proč jsem své doby začal experimentovat s portable verzí osekaného Call of Duty 2..

<!--more-->

**Začneme** z čisté instalace hry, to bude nejlepší.  
Česká verze hry měla problém v instalaci s kopírováním některých souborů, které se museli kopírovat ručně z _DVD/setup/data_ !  
I vzhledem k tomuto problému později vyšel CZ patch verze 1.3, který řešil tento problém. Takže spíše doporučuji nainstalovat ten, který můžete stáhnout například ze serveru&nbsp;[uloz.to](http://uloz.to/4664928/cod2-patch-1-3-cz.exe).

- Nyní přistoupíme k vlastní úpravě.
- nejdříve smažte všechny složky kromě main, miles a pb.
- smažte CoD2SP\_s.exe (spouští SP -\> nefunkční!).
- ve složce main ponechte pouze soubory:&nbsp;_iw\_01.iwd – iw\_10.iwd, iw\_13.iwd – iw\_15.iwd a soubory localized\_english\_iw00.iwd, localized\_english\_iw05.iwd, localized\_english\_iw09.iwd, localized\_english\_iw10.iwd a localized\_english\_iw11.iwd_

_ **Poznámka:** &nbsp;_Soubory _.iwd_ jsou balíky dalších souborů a lze je otevřít (např. ve WinRARu). Bohužel soubory iw\_xx.iwd nejdou ořezat, protože se to dostalo do konfliktu z anticheaterem (PunkBusterem), který by Vás vyhazoval ze hry, kvůli upraveným souborům.

- avšak dle výše zmíněné poznámky jdou osekat soubory_&nbsp;localized\_english\_iw00.iwd_ a _localized\_english\_iw05.iwd_
- _smažte složku&nbsp;soundbattlechatter_ (jsou to hlasy velitelů z Single Playeru).
- tím jsme se dostali ke konci, nyní můžeme osekanou hru nakopírovat na přenosné médium.

 ![](http://2.bp.blogspot.com/-7pioZ31XAB4/U0gzepIlfbI/AAAAAAAAHXA/q3JpnZFBtFw/s1600/cod2_multi_08.jpg)

_ **Úkony na c** __ **ílovém PC:** _ Na cílovém PC, tedy na sestavě na které bude chtít hrát budete muset implementovat CD klíč do registrů OS, hru jako takovou ale nemusíte nikam kopírovat.

Klíč implementujete buďto přes herního klienta a to tak, že přímo ve hře.

_hra – \> multiplayer option -\> CD-key_

**nebo**

Dosazením přímo de registru a to tak že třeba do [tohoto](https://onedrive.live.com/redir?resid=34CCF43311348C66!10954&authkey=!AP8XsSRfX8AlaCo&ithint=file%2creg "key.reg") předem připraveného souboru pouze vložíte svůj cd klíč a na cílovém počítači pouze spustíte.

**Editace souboru:** &nbsp;Editujte soubor (na soubor klepnete pravým tlačítkem a dejte upravit). Pak doplňte svůj cd key mezi uvozovky za „codkey“= a uložte..reg soubor si přiložte třeba do složky s hrou.  
Pokud jste jako já hrdým vlastníkem originálního cd keye, tak doporučuji vytvořit si ještě jeden .reg soubor který tyto hodnoty bude na daném PC nulovat.
<!--kg-card-end: html-->