---
layout: post
title: 'GTA: Vice City na Windows 7 i 8 v HD kabátě'
date: '2013-12-14 19:51:00'
tags:
- gta
- windows
- hash-wordpress
- hash-import-2023-08-28-13-25
---

„Nostalgie je vlezlá svině!“ Kdo by nechtěl znovu prožít příběh italského elegána Tommyho Vercettiho ve městě Vice City z poloviny 80. let… Tato hra pro mě byla vždy nejoblíbenějším dílem série. Nejenom proto, že to bylo první GTA kterému jsem naprosto propadl, ale také tím jaký má styl a v jaké době se odehrává. Hra je sice úžasně stylizovaná, ale na dnešní dobu již velmi technologicky zastaralá. Nastavení dohlednosti,&nbsp;brightness a rozlišení (které sice v defaultu podporuje i 1080p, ale neodpovídá poměru stran dnešních FullHD monitorů) je nedostatečné. Proto Vám poradím, jak původní Vice City upravit pomocí módů tak, aby bylo oku lahodící.

<!--more-->

Upravoval jsem tak, abych zachoval co nejvíce z původní hry a nenarušil tak nostalgické vzpomínání.

Začneme tedy tím, že nainstalujeme vaší 2 CD nebo DVD verzi hry. Hra sice udává podporu pouze na Windows 98, 98SE, ME, 2000, XP, ale nainstalovat a spustit by měla jít bez problému i na nejnovějších verzích systému Vista, 7, 8 a v mém případě nejnovějších 8.1 v 64bitovém provedení. Před instalací doporučuji aktualizovat knihovny [DirectX](http://www.microsoft.com/cs-cz/download/details.aspx?id=35)&nbsp;pomocí online instalátoru (po ukončení instalace již nebudete muset instalovat DX 9.0c). Hru jsem instaloval včetně rádiových stanic.  
\* v případě digitální distribuce se o vše postará daná platforma.

![]( __GHOST_URL__ /wp-content/uploads/2013/12/gta-install.png)

### Verze hry

Hra z mé [DVD verze](http://www.cenega.cz/kolekceklasiky/hry/gtavicecity.html)&nbsp;od Cenegy&nbsp;šla spustit i bez režimu kompatibility, abych pravdu řekl u DVD verze hry ani tento režim nastavit nelze. U 2CD verze spouštějte v režimu pro Windows XP (SP2) a nastavte, aby se soubor spouštěl s oprávněním správce. Nastavíte to po kliknutí na spouštěcí soubor či jeho zástupce na ploše druhým tlačítkem ve vlastnostech – záložka „Kompatibilita“. A spuštěním hry si ověřte, že je vaše hra nastavena správně. Dále pokud vlastníte 2CD verzi, nainstalujeme opravný patch verze 1.1, který stáhneme nejlépe [z oficiálního zdroje](http://updates.rockstargames.com/patches/vicecity/vicepatch_11.zip). DVD verze již patch obsahuje! Patch 1.1 opravuje hlavně problémy s grafickými kartami. Během instalace patche je velmi důležité, aby jste ručně opravili cestu ke složce s hrou na správnou cestu:

    C:\PROGRAM FILES (X86)\ROCKSTAR GAMES\GRAND THEFT AUTO VICE CITY

 ![]( __GHOST_URL__ /wp-content/uploads/2013/12/komaptibilita.png)

Další možností je koupit hru v digitální distribuci. Např. na [Steam](http://store.steampowered.com/app/12110/),&nbsp;což jsem také učinil a později vyzkouším, jestli tyto modifikace budou fungovat i na digitální distribuci a do článku tento fakt doplním.V případě steam verze hry je cesta ke složce s hrou:

    C:\PROGRAM FILES (X86)\STEAM\Steamapps\Common\Grand Theft Auto Vice City

![]( __GHOST_URL__ /wp-content/uploads/2013/12/patch.png)

### Nefunkční myš na Windows 7/8

Pokud vám po startu hry (nikoliv v menu) přestala fungovat myš a nereaguje na vaše pohyby, tak vám chybí DLL knihovna&nbsp;DINPUT8.DLL. Tu musíte stáhnout a nahrát do složky s hrou. Liší se pro 32bitovou a 64bitovou verzi systému!

Stáhněte tedy&nbsp;[32 bitovou](https://mega.co.nz/#!K5RkRIRa!bToP5myjXQKfZ2rh31oNzWYSAhcTNOfMmQHr3bNjmgs)&nbsp;nebo &nbsp;[64 bitovou](https://mega.co.nz/#!TooXSAqI!AL6tmFUORvq4n8Id-_-C9WFmJ7MyUn7AsOKFo6Ki6cI)&nbsp;verzi souboru, uložte ji do složky s hrou a myš by měla fungovat.

Tato chyba se mi objevila u 2CD verze a Steam verze, u DVD verze hry však nikoliv.

### **Vice Cry 1.7.2**

Jako první nainstalujeme mód zvaný Vice Cry, při instalaci si opět musíte dát pozor na zadávanou cestu instalace, protože ve výchozím nastavení je špatně! Tento mód [stáhnete ve verzi 1.7](http://www.moddb.com/mods/vice-cry/downloads/vice-cry-17) ze stránek moddb.com stejně jako jeho dva opravné patche [1.7.1](http://www.moddb.com/mods/vice-cry/downloads/vice-cry-patch-171)&nbsp;a [1.7.2](http://www.moddb.com/mods/vice-cry/downloads/vice-cry-patch-172)…

**Tento mód mění a přidává do hry:**

Změněno 100% přírody

LOD systém pro palmy

Bažina se speciální vegetací

HQ mapa v radaru a HUD +&nbsp;ikony zbraní ve vysoké kvalitě

Auta s více detaily (vložena auta z XBOX verze)

Nový Tropical island

Přemodelovány pickupy

Nové částečné efekty

Upravena světla dopravy

Opraveno mnoho texturových a mapových chyb

Opraveny chyby v .IDE

3D Grass (volitelné)

Nebyly změněny podoby budov ani modely aut!

[![]( __GHOST_URL__ /wp-content/uploads/2013/12/collage-1024x297.jpg)]( __GHOST_URL__ /wp-content/uploads/2013/12/collage.jpg)

CLEO Mód\*pokud budete hru hrát s touto modifikací, tak vaše uložené pozice nepůjdou použít pro čistou verzi hry a naopak.

Pokud nainstalujete modifikace Vice Cry, tak se již s instalací CLEO módu nebudete muset štvát, protože Vice Cry tento mód již obsahuje. Tento mód slouží pro jednoduchou instalaci a spuštění dalších úprav a přídavných funkcí do hry. Stačí pouze danou věc (staženou úpravu a modifikaci) přetáhnout do složky CLEO, která se nachází ve složce s hrou. Tato úprava se následně automaticky aktivuje ve hře. Modifikace s touto jednoduchou instalací naleznete např. [zde](http://www.gtagarage.com/mods/browse.php?C=14)

### Widescreen Fix

Hra sice již v základu podporuje všechna možná rozlišení včetně 1080p a tváří se, že by měla umět i roztáhnout obraz do širokoúhlého formátu (Widescreen). To však neumí, protože i po nastavení těchto hodnot nemá obraz správný poměr stran a vše je moc velké. Na dnešních monitorech je již značně omezující, když vidíte jen malou část zorného pole. K opravení tohoto nešvaru by vám měla pomoci úprava zvaná&nbsp;Widescreen Fix. Velmi oblíbená je verze&nbsp;[Proper Widescreen Fix v4](http://www.gtagarage.com/mods/show.php?id=15521), ale vzhledem k tomu, že byla dlouhou dobu neaktualizovaná, tak já použil mód&nbsp;[Widescreen Fix Remake](http://www.gtagarage.com/mods/show.php?id=23407). Tento mód stačí stáhnout a soubor „vc\_widescreenfix\_remake.asi“ nakopírovat do složky „mss“, která se nachází ve složce s hrou. Rozdíl je skutečně citelný a bez této úpravy si hraní již nedokážu představit.

[![]( __GHOST_URL__ /wp-content/uploads/2013/12/collage2-1024x287.jpg)]( __GHOST_URL__ /wp-content/uploads/2013/12/collage2.jpg)

### Load Screen Remover

Při přejíždění z ostrovu na ostrov se vždy zobrazí obrázek signalizující načítaní dalšího ostrovu, to je však na dnešních počítačích naprosto zbytečné, protože to zvládají v reálném čase, proto „Load screen“ vždy jen problikne a to obtěžuje. Proto můžete úpravou map souborů docílit toho aby se nezobrazoval. Slouží k tomu úprava [Vice City Load Screen Remover](http://www.thegtaplace.com/downloads/f4672-vice-city-load-screen-remover). Po stažení a rozbalení ze složky „install“ překopírujte „map.zon“ do složky&nbsp;&nbsp;„Data“ která se nachází ve složce s hrou. A soubor „islandsf.ipl“ do složky&nbsp;„data/maps/islandsf/“.

[![]( __GHOST_URL__ /wp-content/uploads/2013/12/collage3-1024x379.jpg)]( __GHOST_URL__ /wp-content/uploads/2013/12/collage3.jpg)

### Hi-res Loadscreen

Vstup do hry a načítání zkrášluje velmi známý load screen, který však časem již ubral na atraktivitě. Vinou velkého rozlišení monitorů se zdá býti obrázek roztahaný a jsou vidět kostky. Proto i tento load screen lze nahradit [Hi-Res Loadscreenem](http://www.gtagarage.com/mods/show.php?id=21472), který má plné detaily a vysoké rozlišení. Je v několika variantách. Verze 1 je nejkvalitnější, verze 2 méně a je určena pro použití tam kde první verze nefunguje (objevuje se jen černá obrazovka). A dále jsou upraveny pro různé poměry stran monitoru (16:10, 16:9, 5:4 a 4:3). Instalace je jednoduchá. Soubor „LOADSC0.txd“ nakopírujeme do složky „txd“ která se nachází ve složce s hrou a přepíšeme původní soubor.

[![]( __GHOST_URL__ /wp-content/uploads/2013/12/image_48605-1024x576.jpg)]( __GHOST_URL__ /wp-content/uploads/2013/12/image_48605.jpg)

### ENBSeries \*nepoužívám

Toto je velmi rozporuplná modifikace, po její instalaci je hra opravdu nádherná, přidá do hry rozmazávání a odlesky. Avšak po její instalaci již nebude ve hře fungovat intro. Může se stávat, že při ukázkách (na začátku mise nebo po ní) bude obraz problikávat a ve vysokých rychlostech bude blikat či poskakovat HUD. Myš občas v menu neklikala. Avšak vše ostatní bude dokonalé. Instalace je jednoduchá stačí stáhnout aktuální [ENBSeries](http://www.thegtaplace.com/downloads/f6526-enbseries-gtavc-v00075c3-graphics)&nbsp;a rozbalit ho do složky s hrou. Poté a poté upravit soubor „enbseries.ini“ nebo přepsat [tímto](https://mega.co.nz/#!H0JnRQqK!LFonRHgNWRDwfwri9wBwwDTSkelgv_61xIhOde1bksM), který jsem upravil dle svého uvážení a vyzkoušel (viz. screenshoty). Mód můžete ve hře libovolně zapínat a vypínat klávesovou zkratkou „Shift+F12“. A velkým bonusem je, že když vytvoříte screenshot pomocí klávesy „Printscr“, tak se vám uloží do složky s hrou (ve formátu enb\*rok\*měsíc\*den\*hodina\*minuta\*sekunda ), takže budete moci fotit ve hře bez nutnosti vracet se zpět do systému nebo používat další program (např. Fraps).

[![]( __GHOST_URL__ /wp-content/uploads/2013/12/collage4-1024x297.jpg)]( __GHOST_URL__ /wp-content/uploads/2013/12/collage4.jpg)

### DrawDistance Mód

Tato modifikace je také docela sporadická. Měla by být obsažena již v módu Vice Cry, ale přitom při přejíždění z jednoho ostrova do druhého po probliknutí loadscreenu se vždy začal druhý ostrov načítat znovu i když byl již v dálce načtený. Řešení tohoto problému je, že stáhnete&nbsp;[Spaceeinstein’s DrawDistance Mod](http://www.gtagarage.com/mods/show.php?id=876)&nbsp;a soubory obsažené v archívu nakopírujete do složky „data“ ve složce s hrou. Ta úprava totiž zruší zóny načítání. [Tato modifikace](http://www.thegtaplace.com/downloads/f2372-vice-city-x10-draw-distance) by měla dohlednost zvednout až 10x. Po stažení stačí soubor „timecyc.dat“ překopírovat do složky „data“ ve složce s hrou a přepsat tak původní soubor. Screeny ukazují hru po instalaci x10&nbsp;DrawDistance Módu, ale již po instalaci&nbsp;Spaceeinstein’s DrawDistance Modu…

[![]( __GHOST_URL__ /wp-content/uploads/2013/12/collage5-1024x307.jpg)]( __GHOST_URL__ /wp-content/uploads/2013/12/collage5.jpg)

### Frame Limit Adjuster

Zvýšení limitu snímků je pro hru a hlavně pro její plynulost velice důležitá, lze tak učinit pomocí [ultility](http://www.gtagarage.com/mods/show.php?id=7650). Nebo pomocí [CLEO módu](http://www.gtagarage.com/mods/show.php?id=15178), který po rozbalení stačí nakopírovat dvojici souborů (60vcframelimiter.cs a 60vcframelimiter.txt) do složky „cleo“&nbsp;která se nachází ve složce s hrou. A podle toho jak změníte číslovku v názvu souboru nastavíte limit počtu snímků za sekundu (0-99).

### Trails

Tento efekt, který upravuje barevné spektrum a rozmazávání. Byl použit u PS2/3 verze hry a z PC verze byl byl na poslední chvíli z neznámých důvodů odstraněn. Hlavně díky tomu poslouží k aktivaci tohoto efektu jen CLEO script, který dokonce přidá možnost zapnout a vypnout tento efekt do nabídky nastavení. O tom jestli jen tento efekt dobrý či ne se na internetu vedou sáhodlouhé [diskuze](http://www.neoseeker.com/forums/3496/t233924-poll-trails-no-trails/). Avšak díky tomu, že se dá v menu jednoduše odstranit, tak není nic proti ničemu si stáhnout&nbsp;[Vice City Trails](http://www.gtagarage.com/mods/show.php?id=22416)&nbsp;a rozbalený soubor „vctrails.asi“ zkopírovat do složky „mss“ která se nachází ve složce s hrou.

[![]( __GHOST_URL__ /wp-content/uploads/2013/12/collage6-1024x307.jpg)]( __GHOST_URL__ /wp-content/uploads/2013/12/collage6.jpg)

### Skiny

Uvádím jen tak pro úplnost. Každý si může vytvořit svůj vlastní pomocí šablony uložené ve složce „skins“ která se nachází ve složce s hrou. Nebo do této složky nahrát jakýkoliv skin z internetu. Možná je trochu zajímavostí, že po dlouhých letech se na [oficiálních stránkách](http://www.rockstargames.com/vicecity/pc/index.htm)&nbsp;v sekci download objevil skin označený jako „Exclusive Tommy Vercetti“.

### Lokalizace

S českou a slovenskou lokalizací byl vždy problém, protože jich existuje několik a žádná není dokonalá. Většina češtin nahrazuje ve hře španělštinu (takže Anglická lokalizace je stále dostupná) a kromě textur překládá skutečně vše včetně diakritiky. Lokalizace by vždy měla být instalována až na úplný závěr, protože s instalací úprav hry se může snadno stát, že se nějakým způsobem rozhodí. &nbsp;Nejrozšířenější čeština je od Raptora tu stáhnete např. [zde](http://cestiny.idnes.cz/grand-theft-auto-vice-city-dc0-/Hry.aspx?c=A030610_89995_bw-cestiny-hry_bw)&nbsp;nebo [zde](http://www.porse.cz/Gta_4_demo/Grand_Theft_Auto_Vice_City_cestina.html), ale právě ta trpí také nejvíce neduhy. Např.  
1. U první mise za Corteze (Falešná svině) se zasekne hra při vjezdu do lakovny.
2. U mise Death Row (Cela Smrti) se taktéž může stát, že se vám hra zasekne na konci mise, kdy vykládáte Lance u nemocnice.  
3. U poslední mise za Corteze (Všichni na palubu) zásek před začátkem mise.

U prvního případu lze použít hvězdičky na sražení hledanosti, v ostatních případech budete muset před začátkem mise přepnout hru do angličtiny. U mé DVD verze byla přiložena čeština od společnosti Conega a ta byla bezproblémová i pod náporem modifikací.

### Ikona

Pokud budeme velcí puntičkáři, tak si jistě všimneme toho, že i ikona již ztratila na kráse a proto se můžeme směle poohlédnou po náhradě. Například [zde](http://www.iconarchive.com/show/mega-games-pack-23-icons-by-3xhumed/GTA-Vice-City-new-5-icon.html)&nbsp;lze stáhnout ikonu ve formátu .ico, která připomíná originální ikonu&nbsp;a nebo [zde](http://www.iconarchive.com/show/mega-games-pack-23-icons-by-3xhumed/GTA-Vice-City-new-5-icon.html)&nbsp;ikonu kterou vidíte v úvodu tohoto článku. Stačí stáhnout formát .ico, nakopírovat nejlépe do složky „Icons“, která se nachází ve složce s hrou a u zástupce na ploše změnit ikonu právě na tuto.

### Závěr

Pokud jste článek dočetli až sem, tak vás potěším, protože chystám pokračování… Nebo pouze doplním informace do tohoto článku. Jedná se o to, že všechno testování jsem prováděl na DVD verzi hry od Cenegy, která není na internetu ke stažení a mnoho lidí ji nevlastní. Chtěl bych tedy doporučit koupi této krabicové DVD verze hry, protože je skutečně bezproblémová, vč. české lokalizace. Budu se však do článku snažit doplnit i zkušenosti s digitální distribucí hry (Steam). Kdybyste měli jakýkoliv dotaz či připomínku, zanechte ji prosím zde v komentáři. Děkuji za pozornost…

[![]( __GHOST_URL__ /wp-content/uploads/2013/12/2013-12-12-17.13.04-1024x768.jpg)]( __GHOST_URL__ /wp-content/uploads/2013/12/2013-12-12-17.13.04.jpg)

Článek byl inspirován [tímto](http://hosting.cecak.cz/forum-modifikace/viewtopic.php?p=922 "forum") fórum postem….
<!--kg-card-end: html-->