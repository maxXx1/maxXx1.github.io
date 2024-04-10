---
title: "Call of Duty 2 vlastní portable verze"
date: "2011-08-08"
category: Hry
tags: 
  - "COD2"
image:
  path: /img/2013-10-20-call-of-duty-2-na-windows-8-1/cod2.jpg
  alt: Call of Duty2  
---

Určitě se na internetu povalují různé portable verze této slavné hry, ale není nad to když si člověk něco udělá sám. Proto bych Vás rád provedl způsobem jak Call of Duty 2 osekat na pouhý Multiplayer a tím ušetřit velké množství místa např. pro přenos na flash discích do škol či zaměstnání, kde je zakázáno instalovat hry.
Tímto samozřejmě nechci nikoho nabádat k tomu, aby ve škole místo výuky dělal něco jiného než má. I když přesně toto byl důvod proč jsem své doby začal experimentovat s portable verzí osekaného Call of Duty 2..

Začneme z čisté instalace hry, to bude nejlepší.
Česká verze hry měla problém v instalaci s kopírováním některých souborů, které se museli kopírovat ručně z `DVD/setup/data`{: .filepath} !
I vzhledem k tomuto problému později vyšel CZ patch verze 1.3, který řešil tento problém. Takže spíše doporučuji nainstalovat ten...

<a href="https://www.moddb.com/games/call-of-duty-2/downloads/call-of-duty-2-pc-patch-v-13" title="Download Call of Duty 2 (PC) Patch v 1.3 - ModDB" target="_blank"><img src="https://button.moddb.com/download/medium/110548.png" alt="Call of Duty 2 (PC) Patch v 1.3" /></a>

Nyní přistoupíme k vlastní úpravě.

- nejdříve smažte všechny složky kromě `main`, `miles` a `pb`.
- smažte `CoD2SP_s.exe` (spouští SP -> nefunkční!).
- ve složce main ponechte pouze soubory: `iw_01.iwd` - `iw_10.iwd`, `iw_13.iwd` - `iw_15.iwd` a soubory `localized_english_iw00.iwd`, `localized_english_iw05.iwd`, `localized_english_iw09.iwd`, `localized_english_iw10.iwd` a `localized_english_iw11.iwd`

>Soubory `*.iwd` jsou balíky dalších souborů a lze je otevřít (např. ve [7Zip](https://www.7-zip.org/)). Bohužel soubory `iw_xx.iwd` nejdou ořezat, protože se to dostalo do konfliktu z anticheaterem (PunkBusterem), který by Vás vyhazoval ze hry, kvůli upraveným souborům
{: .prompt-tip }

- avšak dle výše zmíněné poznámky jdou osekat soubory `localizedenglishiw00.iwd` a `localizedenglishiw05.iwd`
- smažte složku `soundbattlechatter` (jsou to hlasy velitelů z Single Playeru).
- tím jsme se dostali ke konci, nyní můžeme osekanou hru nakopírovat na přenosné médium.

__Úkony na cílovém PC:__ Na cílovém PC, tedy na sestavě na které bude chtít hrát budete muset implementovat CD klíč do registrů OS, hru jako takovou ale nemusíte nikam kopírovat.
Klíč implementujete buďto přes herního klienta a to tak, že přímo ve hře.
`hra - > multiplayer option -> CD-key`{: .filepath}

