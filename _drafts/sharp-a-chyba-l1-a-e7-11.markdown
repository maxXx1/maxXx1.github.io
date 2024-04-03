---
layout: post
title: SHARP a chyba L1 a E7-11
tags:
- nezarazene
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Právě se mi do ruky dostala již velmi stará kopírka SHARP&nbsp;AR 122E N, která hlásila velmi ošemetnou chybu L1 (L1-00). Chyba se projevuje tak, že po spuštění kopírky se pouze pohne hlava skenovacího zařízení (cca. 3cm) vpřed a poté opět zaparkuje.

Základní téze této chyby dle oficiální podpory je ta, že hlava skeneru je zamčena pomocí zámku na levé straně zařízení, pod skenovací plochou (viz. obrázek).

<!--more-->

| [![](http://1.bp.blogspot.com/-hy4BGoYc9cg/UUBFzuPIelI/AAAAAAAACsw/QIJpHdfMuak/s400/2013-03-13+10.20.44.jpg)](http://1.bp.blogspot.com/-hy4BGoYc9cg/UUBFzuPIelI/AAAAAAAACsw/QIJpHdfMuak/s1600/2013-03-13+10.20.44.jpg) |
| **Zámek skenovací hlavy** |

Ale vzhledem ke stáří tiskárny se tato chyba může objevovat velmi nahodile, protože je řízena elektronikou, která je úzce provázána právě s elektronikou skenovací hlavy, která je v kopírce nejvíce namáhána a paradoxně má nejmenší garantovanou životnost. Pořizovací náklady / náklady spojené s opravou této jednotky bych přirovnal k opravě tiskové hlavy u levných tiskáren. Mnohokrát převyšují cenu zařízení.

Tiskárna se určitým způsobem „restartuje“ při vytažení tonerové kazety, aby poznala, že je dodán nový spotřební materiál i když tomu tak ve skutečnosti není. Proto postup na odstranění této chyby zahrnuje i tento úkon. Proto zveřejním postup, který pomohl v mém případě.

**1.** Zkontrolovat na levé straně pod skenovací plochou zámek skenovací hlavy, který musí být v poloze „odemčeno“ (rozpojený zámek)  
**2.** Vyndat tonerovou kazetu z pravé části tiskárny (pozor sype to!)  
**3.** Vypnout zařízení. Pozor, nejenom tlačítkem v levé části zařízení, odpojit úplně od sítě.  
**4.** Počkat 70 sekund, během kterých by měla tiskárna zapomenout staré instrukce (a poté při spuštění načíst nové).  
**5.** Vrátit tonerovou kazetu a spustit zařízení.

Pokud tento postup nepomohl, tak jej zkuste po delší době kdy je zařízení opojeno od proudu opakovat.  
Pokud nepomůže ani toto (nebo se přidají další chyby), tak jste se zřejmě dostaly do mrtvého bodu, kdy jediné co pomůže, je výměna skenovací hlavy či pouze její elektroniky.

![](http://www.maxxx.cz/wp-includes/js/tinymce/themes/advanced/img/trans.gif)

**Poznámka:** &nbsp;S touto chybou se úzce váže také chyba E7-11, která se týká světelné lampy na skenovací hlavě (a soustavy zrcadel), která se dá vyřešit v lepších případech sejmutím skla a očištěním bílého pruhu (na levé straně vespod viz. obrázek) na kterém si lampa přes soustavu zrcadel srovnává světelnost. Ovšem pokud se tato chyba objeví společně s chybou &nbsp;L1-00 značí to jediné – nutná výměna skenovací hlavy či minimálně lampy/CCD snímače… (nerentabilní!)

[![](http://2.bp.blogspot.com/-B16hkIH77pY/UUBrJQqm8dI/AAAAAAAACtM/e3h0RpP8xN4/s320/2013-03-13+12.47.53.jpg)](http://2.bp.blogspot.com/-B16hkIH77pY/UUBrJQqm8dI/AAAAAAAACtM/e3h0RpP8xN4/s1600/2013-03-13+12.47.53.jpg)

V krajních případech, pokud ovšem víte, že očistění skla pomohlo, můžete vzít bílou (nejlépe modelářskou) barvu a bílý proužek pro korekci světelných lamp překreslit na spodní část skla.
<!--kg-card-end: html-->