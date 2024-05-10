---
title: "GTA: Vice City - Steam/Windows 8.1 HD modifikace"
date: "2015-04-18"
category: Hry
tags: 
  - "GTA"
  - "Steam"
  - "Windows-8.1"
image: 
  path: "/img/2015-04-18-gta-vice-city-steamwindows-8-1-hd-modifikace/vice_city.jpg"
  alt: Vice City by professor adagio
---

Zde bych rád navázal na svůj předešlý článek, který jsem zveřejnil před více než rokem a sliboval jsem v něm, že se k problematice GTA: Vice City modifikací vrátím. Opatřil jsem si tedy [Steam verzi](https://store.steampowered.com/app/12110/ "steam") hry a s překvapením zjistil, že na nejnovějších systémech (Windows 8 / 8.1) funguje velmi obstojně a mnoho modifikací z původního článku za tu dobu vyšlo ve finálních verzích či bylo nahrazeno lepším řešením. Vezmeme to pěkně popořádku od instalace až po úpravy...

## Instalace a první spuštění

Po instalaci by hra měla jít bez větších obtíží normálně spustit. Před prvním spuštěním se bude provádět doinstalace DirectX a možná také funkce DirectPlay. Kdyby funkce DirectPlay nešla standardní cestou nainstalovat, tak stačí vypnout anti-virový program (pouze po čas instalace) a Steam spustit s oprávněním správce.

Hra bude ale ve své podstatě vypadat opravdu špatně, až se budete divit - jak jste tohle vůbec mohli hrát a nebude ve hře fungovat ani myš. Resp. myš nebude reagovat na váš klik. To je zapříčiněno chybějící .dll knihovnou. Našel jsem modifikaci na simulaci Full HD rozlišení, která tuto knihovnu obsahuje nýbrž pro její použití budeme muset prvně rozběhat CLEO což je běhové prostředí pro ostatní modifikace. Toto běhové prostředí obsahuje Vice Cry, takže tím začneme.

## Vice Cry 1.8 + HOTFIX

První věc, která mě po více než roce od posledního článku opravdu mile překvapila je, že základ našeho modifikování - tedy balík Vice Cry je ve své finální verzi 1.8 a jeho vývoj je tedy definitivně dokončen. Tento mód mění veškerou vegetaci včetně palem, přidává HQ radar, ikony zbraní, nový HUD, modely aut z XBOX verze, tropical island, efekty, světla a mnoho dalšího...

<iframe src="http://www.moddb.com/media/iframe/1238592" width="560" height="350" frameborder="0" scrolling="no" allowfullscreen="allowfullscreen"></iframe>

Avšak **nemění** vlastnosti aut ani budov! A díky tomu je plně kompatibilní s mltiplayerem...

Jak jsem již zmínil výše, součástí tohoto balíku je také **CLEO** mód, který nám výrazně usnadní instalaci dalších modifikací.

**Instalace:** Jednoduše stáhněte [základní balík](https://www.moddb.com/mods/vice-cry/downloads/vice-cry-18 "vice cry"), [opravný balík](https://www.moddb.com/mods/vice-cry/downloads/vice-cry-hotfix "hotfix") a při instalaci vyplňte správnou cestu k vaší hře tedy...

```
C:\Program Files (x86)\Steam\steamapps\common\Grand Theft Auto Vice City
```

## Widescreen Fixes

Avšak i po tak velkém zásahu je HUD ve hře nepřiměřeně velké rozlišení a myš stále nereaguje tak jak by jsme chtěli. Proto jsem našel variantu Widescreen Fixu, která obsahuje mimo konfigurovatelný CLEO script pro vysoké rozlišení také knihovnu `dinput8.dll`, která naučí myš poslušnosti.  Tuto variantu jsem vybral i proto, že mi přijde její vývoj dotažen do konce a je plně konfigurovatelná přes přiložený .ini soubor.

![pred1](/img/2015-04-18-gta-vice-city-steamwindows-8-1-hd-modifikace/2015-04-18_00002.jpg)
_Před_
![po1](/img/2015-04-18-gta-vice-city-steamwindows-8-1-hd-modifikace/2015-04-18_00004.jpg)
_Po_

**Instalace:** Stáhněte balík určený pro Vice City z [githubu projektu](https://thirteenag.github.io/widescreen_fixes_pack#gtavc "rozlišení") a obsah složky `GTAVC_widescreen_fix` rozbalte do složky s hrou.

## Silent Patch

Dále využijeme toho, že máme k dipozici CLEO mód a nainstalujeme tzv. Silent Patch který mimochodem ještě doopravuje drobné chybičky v texturách, ale hlavně opravuje lagy na vysokých FPS ve chvíli kdy je vypnutý omezovač snímků za sekundu, správné vykreslení odrazů na mokré vozovce (nahrazuje Road Reflections Fix), oprava stínů u textů a mnoho dalších oprav zejména zvuků...

Tento patch má ještě další dodatek a to v podobě .dll knihovny, která opravuje i to na co samotný script nestačí. ddraw.dll vnutí hře rozlišení pracovní plochy jako defaultní (už nikdy více neuvidíte 640x480). Byla odstraněna závislost na DirectPlay což by mělo zvýšit stabilitu na Windows 8. Opravuje také pády po startu hry a chybu nedostupnosti grafické paměti.

**Instalace:**  Obě části stáhnete [zde](https://www.gtagarage.com/mods/show.php?id=25368 "silentpatch") a obsah archívů jednoduše rozbalíte do složky s hrou.

## Lokalizace

Nyní již můžeme přikročit ke kroku, který by se měl provádět až v závěru, aby nebyl rozhozen ostatními úpravami a to je lokalizace do češtiny. Jak jsem již zmínil v původním článku - na internetu se českých lokalizací povaluje několik, avšak většina z nich má velký bug, který způsobuje to, že hra padá při některých misích a neleze ani korektně ukončit. Proto bych rád vyzkoušel tento vlastní balík. Poznánka: Bohužel prozatím musím uznat, že i tato čeština způsobuje zamrznutí hry u některých misí (tento problém budu nadále řešit).

**Instalace:** Balík stáhnete [zde](https://mega.co.nz/#!2k42TLyK!qNlXWsajLSyrRDD5_kv-hK-jthFuige-r9SLL0ROU3s "čeština"). Rozbalte přímo do složky s hrou či libovolně jinam a pak obsahem přepište původní soubory ve složce s hrou.

## Drobné úpravy a nastavení

Ještě teď hra nefunguje naprosto dokonale (např. úvodní intro se nezobrazuje) atd. atd. tyhle detaily by mělo doladit vynucená módu komaptibility pro spouštěcí .exe souboru. Já osobně doporučuji **režim kompatibility pro Windows 98/Me**.

V poslední řadě bych rád upozornil, že pro někoho nežádoucí **efekt stopy** (trials) jdou nyní vypnout/zapnout přímo z prostředí menu.

![pred2](/img/2015-04-18-gta-vice-city-steamwindows-8-1-hd-modifikace/2015-04-18_00004.jpg)
_Před_

![po2](/img/2015-04-18-gta-vice-city-steamwindows-8-1-hd-modifikace/2015-04-18_00003.jpg)
_Po_

## Závěr

A to by bylo tedy asi úplně vše. Kdyby mě napadla další modifikace, kterou by se tento "kokteil" dal vylepšit, tak ji doplním. Zbylé informace můžete dohledat v původním článku.
