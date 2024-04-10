---
title: "Výměna WiFi karty na ThinkPadu - Error 1802"
date: "2013-07-24"
category: Hardware
tags: 
  - "Laptop"
image:
  path: /img/page/thinkpad.jpg
  alt: IBM ThinkPad  
---

_Dneska jsem měnil wifi kartu na IBM ThinkPad T42 a čekalo mě nemilé překvapení..._

V tomto kousku byl starší wifi modul připojený přes mini PCI nepodporující nové standardy (a/b/g) a proto se majitel rozhodl kartu nechat vyměnit. 
Není se čemu divit vzhledem ke stáří tohoto modelu. Nepochybuji o tom, že v tehdejší době byl obsažený modul (výrobce Samsung) špičkou na trhu avšak dnes je již jeho výkon nedostatečný.

Rozhodl jsem se ho nahradit modulem [Intel PRO/Wireless 2915abg Mini PCI](https://support.lenovo.com/us/en/downloads/ds003878) nejenom proto, že jsem ho měl zrovna po ruce (použitý, vytažen z počítače, který již odešel do křemíkového nebe), ale také proto, že na stránkách IBM jsou na něj oficiální ovladače. A hlavně podporuje dané standardy a/b/g. Tudíž velmi zvýší citlivost signálu.

Problém nastal hned po prvním spuštění po výměně modulu, protože ThinkPad si hlídá to, jakými komponenty je osazen. Postrádá to sice logiku a v dnešní době jsem se s tím již u žádného výrobce nesetkal. S kompatibilitou nemá problém, spíše se jedná o brzdu proti neservisním zásahům. To že detekoval jinou kartu a nehodlá s ní spolupracovat, ba co víc ani pokračovat v bootování mi dal jasně najevo chybovou hláškou:

`ERROR 1802: Unauthorized network card is plugged-in. Power off and removed miniPCI network card.`

Naštěstí minimálně pro mnoho modelů včetně T42 (podrobný seznam modelů na thinkwiki) existuje jednoduchá ultilitka, která tento problém řeší. Pro ostatní modely je to trochu složitější, ale na thinkwiki jsem našel mnoho návodů.
viz. [ThinkWiky](https://www.thinkwiki.org/wiki/Problem_with_unauthorized_MiniPCI_network_card)

## Otestované funkční modely

| A31, A31 2652-Q3U, A31 2652-1U6 |
| A31p, A31p 2653-CU5, A31p 2653-R3U |
| G40 2384-EHU |
| R40 2682-HU2, R40 2682-K2G, R40 2681, R40 2896-GZU |
| R50 1830-48G |
| R50e 1834-BZG |
| R51 |
| T30, T30 2637 |
| T40, T40 2373, T40 2373-8CU, T40 2373-94G, T40 2374-GG2, T40 2374-DG1 |
| T41, T41 2374-7JG |
| T42, T42 2373-BX9 |
| T42p |
| X24 |
| X30 |
| X31, X31 2672-U31 |
| X40 |

## Otestované nefunkční modely

| R32 |
| R60 |
| T60 |
| Z60t |
| X41 2525-6NH |
| Lenovo x100e |
| Lenovo x120e |

## Návod

U tohoto modelu (a jemu podobných) stačí pouze stáhnout malé ISO, poté ho vypálit. Doporučuji přepisovatelné CD (CD-RW) nebo vytvořit bootovatelný flash disk (max 512MB, FAT32), protože ultilita má pouze něco kolem 6MB. Nyní z něho staří nabootovat a napsat příkaz:
`no-1802`
Pod kterým se skrývá 18ti bytes dlouhý .com soubor, který nastaví nejvyšší byt v CMOS na adrese `0x6a`.

~~no-1802-cd.zip~~

Tuto úpravu musíte provádět dokud je v počítači původní karta, po provedení této úpravy stačí notebook vypnout a přistoupit k vlastní výměně.

Pro novější modely (ThinkPad T43/T43p/R52/X41) je již nutná úprava biosu. O upravený BIOS si si můžete požádat na [MDF fóru](https://forums.mydigitallife.net/forums/bios-mods.25/), kde se zabývali i konkrétně touto chybou.

Podobnou chybou trpí i starší notebooky HP, avšak u nich je úprava o něco složitější.