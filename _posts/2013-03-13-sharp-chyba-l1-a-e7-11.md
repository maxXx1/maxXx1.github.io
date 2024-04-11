---
title: "SHARP a chyba L1 a E7-11"
date: "2013-03-13"
category: Hardware
tags: 
  - "Tiskárna"
image: 
  path: /img/2013-03-13-sharp-chyba-l1-a-e7-11/2013-03-13-10.21.04.jpg
  alt: Sharp
---

Právě se mi do ruky dostala již velmi stará kopírka SHARP AR 122E N, která hlásila velmi ošemetnou chybu L1 (L1-00). Chyba se projevuje tak, že po spuštění kopírky se pouze pohne hlava skenovacího zařízení (cca. 3cm) vpřed a poté opět zaparkuje.

{% include embed/youtube.html id='o8aUDcaDJ7w' %}

Základní téze této chyby dle oficiální podpory je ta, že hlava skeneru je zamčena pomocí zámku na levé straně zařízení, pod skenovací plochou (viz. obrázek).

![lock](/img/2013-03-13-sharp-chyba-l1-a-e7-11/2013-03-13-10.20.44.jpg)
_Zámek skenovací hlavy_

Ale vzhledem ke stáří tiskárny se tato chyba může objevovat velmi nahodile, protože je řízena elektronikou, která je úzce provázána právě s elektronikou skenovací hlavy, která je v kopírce nejvíce namáhána a paradoxně má nejmenší garantovanou životnost. 
Pořizovací náklady / náklady spojené s opravou této jednotky bych přirovnal k opravě tiskové hlavy u levných tiskáren. Mnohokrát převyšují cenu zařízení.

Tiskárna se určitým způsobem "restartuje" při vytažení tonerové kazety, aby poznala, že je dodán nový spotřební materiál i když tomu tak ve skutečnosti není. Proto postup na odstranění této chyby zahrnuje i tento úkon. Proto zveřejním postup, který pomohl v mém případě.

1. Zkontrolovat na levé straně pod skenovací plochou zámek skenovací hlavy, který musí být v poloze "odemčeno" (rozpojený zámek)
2. Vyndat tonerovou kazetu z pravé části tiskárny (pozor sype to!)
3. Vypnout zařízení. Pozor, nejenom tlačítkem v levé části zařízení, odpojit úplně od sítě.
4. Počkat 70 sekund, během kterých by měla tiskárna zapomenout staré instrukce (a poté při spuštění načíst nové).
5. Vrátit tonerovou kazetu a spustit zařízení.

Pokud tento postup nepomohl, tak jej zkuste po delší době kdy je zařízení opojeno od proudu opakovat.
Pokud nepomůže ani toto (nebo se přidají další chyby), tak jste se zřejmě dostaly do mrtvého bodu, kdy jediné co pomůže, je výměna skenovací hlavy či pouze její elektroniky.

> S touto chybou se úzce váže také `chyba E7-11`, která se týká světelné lampy na skenovací hlavě (a soustavy zrcadel), která se dá vyřešit v lepších případech sejmutím skla a očištěním bílého pruhu (na levé straně vespod viz. obrázek) na kterém si lampa přes soustavu zrcadel srovnává světelnost. 
Ovšem pokud se tato chyba objeví společně s `chybou L1-00` značí to jediné - nutná výměna skenovací hlavy či minimálně lampy/CCD snímače... (nerentabilní!)
{: .prompt-info }

![scannner](/img/2013-03-13-sharp-chyba-l1-a-e7-11/2013-03-13-12.47.53.jpg)

V krajních případech, pokud ovšem víte, že očistění skla pomohlo, můžete vzít bílou (nejlépe modelářskou) barvu a bílý proužek pro korekci světelných lamp překreslit na spodní část skla.