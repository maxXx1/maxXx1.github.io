---
title: "COD2 - Bindy, scripty, příkazy"
date: "2015-04-20"
tags: 
  - "COD2"
category: Hry
image: 
  path: "/img/2015-04-20-cod2-bindy-scripty-prikazy/screenshot_2015-04-08.jpg"
  alt: COD2 Console
---

V Call of Duty 2 leze využít mnoha příkazů sctiptů a podobných nastavení z configu, ale také přímo ze hry. Tyto příkazy vám mohou zvelebit váš nick name barvami, spustit nahrávání záznamu ze zápasu, nastavení předkonfigurovaného bindu a mnoho dalšího. Právě na tyto příkazy a další drobné nastavení se podíváme v tomto článku.

### Konzole

Konzole se zapíná pomocí klávesy `~` která se nachází pod klávesou Escape. Do této konzole se vypisuje veškeré dění ve hře a také se do ní vkládají příkazy. Pro úplný výpis konzole slouží zkratka `shift + ~`.

### Bindy

Bind je způsob mapování libovolného příkazu k libovolné klávese. Tedy například:
```console
/bind p name say Hello world!
``` 
Vypíše vždy po stisknutí klávesy `p` do chatu: *Hallo world!* <br> 
Takto se dá mapovat jakýkoliv příkaz, na jakoukoliv klávesu. Syntaxe je vždy 
`/bind "klávesa" "příkaz" "parametr"`

### Barevný nickname

Hra disponuje možností obarvit si jméno (nickname), které bude mít barvy jaké deklarujeme v tabulce výpisu score (scoreboard) či v chatu. Barvy mají v nicku určitou syntaxi a tou je, že před číslo, které určuje barvu vložíte znak `^`stříšky - jednoduše např. pomocí klávesové zkratky `alt + 94` v případě, že máte klávesnici přepnutou na českou znakovou sadu. __Příklad:__
```console
f^1$^7.max^9X^7x ^9RattenZone
```

![Nick](/img/2015-04-20-cod2-bindy-scripty-prikazy/17541545.jpg)

Takže pokud si potřebujete tento postup zrychleně vyzkoušet přímo ze hry zapněte konzoli a napište příkaz:
```console
name ^1Jmeno
```
Ve scoreboardu by se měl objevit nápis "Jméno" a být celý červeně.

#### Seznam barev:

  | kód | barva | poznámka |
  | :-- | :---- | :------ |
  | `^^0` | černá | u černé barvy musíte použít 2x stříšku ^ | 
  | `^1` | červená | |
  | `^2` | zelená | |
  | `^3` | žlutá | |
  | `^4` | modrá | |
  | `^5` | světle modrá | |
  | `^6` | fialová | |
  | `^7` | bílá | |
  | `^8` | matně zelená | když hrajete za Američany (i Němce) | 
  |    | růžová | když hrajete za Rusy (i Němce) |  
  |    | modrofialová |když hrajete za Brity (i Němce) | 
  | `^9` | šedá | |

#### Dvojité použití

Duplicitním použitím docílíte toho, že váš nick bude barevný i ve výpisu chatu a tabulce kde se zobrazuje kdo koho zabil. Problémem je, že v některých částech hry bude syntaxe celého příkazu viditelná, tedy bude vidět i stříška s jedničkou.
```console
max^11Xx
```

### Voice messages

Dalšími bezesporu rychlými příkazy, kterými lze vyjádřit velmi rychle a efektivně většinu příkazů vašim spoluhráčům jsou hlasové příkazy. Řadí se do několika kategorií a lze ve vyvolat defaultně klávesou `v` a vybírat čísly. nebudete se tedy muset zdržovat zdlouhavým vypisováním do chatu. Po zadání příkazu se ozve ve hře to co jste chtěli říci, souběžně se to vypíše do chatu a vaše ikona začne blikat na minimapě. Příkladem může být voice *"Enemy spotted!*, kdy spoluhráč nejenom ví, že jste zahlédl nepřítele, ale ví i přibližně kde.

#### Význam jednotlivých klávesových kombinací:

##### Pohyb (Move)

| Klávesy | Hláška | Význam |
| :-- | :---- | :------ |
| `v+1+1` | Follow me! | Za mnou! |
| `v+1+2` | Move in! | Pohyb! |
| `v+1+3` | Fall back! | Zpátky! |
| `v+1+4` | Suppressing fire! | Krycí palba! |
| `v+1+5` | Squad, attack left flank! | Útok na levé křídlo! |       
| `v+1+6` | Squad, attack right flank! | Útok na pravé křídlo! |         
| `v+1+7` | Squad, hold this position! | Držte pozice! |
| `v+1+8` | Squad, regroup! | Přeskupit se! |

##### Hlášky (Statements)

| Klávesy | Hláška | Význam |
| :-- | :---- | :------ |
| `v+2+1` | Enemy spotted! | Vidím nepřítele! |
| `v+2+2` | Enemy down! |  Nepřítel mrtev! |
| `v+2+3` | I’m in position. | Jsem na místě! |
| `v+2+4` | Area secure! | Prostor zabezpečen! |
| `v+2+5` | Grenade! | Granát! |
| `v+2+6` | Sniper! | Sniper! |
| `v+2+7` | Need reinforcements! | Potřebuji posily! | 
| `v+2+8` | Hold your fire! | Nestřílet! |

##### Odpovědi (Responses)

| Klávesy | Hláška | Význam |
| :-- | :---- | :------ |
| `v+3+1` | Yes sir! | Ano! |
| `v+3+2` | No sir! | Ne! |
| `v+3+3` | On my way. | Za mnou. |
| `v+3+4` | Sorry! | Promiň! |
| `v+3+5` | Great shot! | Skvělý zásah! |
| `v+3+6` | Took long enough! |  Trvá vám to moc dlouho! |
| `v+3+7` | Are you crazy? | Jsi normální? |

### Příkazy

Když spustíte konzoli musíte vymazat znak středníku a vždy vložit lomítko před zadávaný příkaz, pak můžete vkládat mnoho příkazů neboli `cvars`. 
U příkazu se vždy zobrazí nápověda pro jeho případné parametry.

#### Nejpoužívanější příkazy

| cvar | funkce | poznámka |
| :-- | :---- | :------ |
| `/kill` | Zabít se | |
| `/screenshotJPEG` | Vyfotí konzoli a obrázek uloží do složky s hrou | v případě použití bindu vyfotí danou scénu |
| `/connect 192.168.0.1` | připojení k dané IP drese | serveru |
| `/reconnect` | znovupřipojení | na poslední připojený server |
| `/disconnect` | odpojí se ze serveru | do menu hry |
| `/bind` | mapování příkazu na klávesu | přímo z konzole |
| `/name jmeno` | změni nickname | |
| `/record nazev` | začne nahrávat demo ze zápasu | uloží jej do složky s hrou |
| `/stoprecord` |  zastaví nahrávání | |
| `/demo název` | přehraje záznam | musí být ve složce "demos" |
| `/pb_plist` | seznam hráčů podle PunkBusteru | |
| `/pb_kick 1` | vyhození hráče č. 1 dle seznamu "plist" | je nutné mít oprávnění | 

#### Nastavení zobrazení 

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `cg_blood` | zapnutí/vypnutí krve | |
| `cg_brass` | zapnutí/vypnutí munice | |
| `cg_centerPrintY` | umístění zpráv v prostřed obazovky | osa Y |
| `cg_chatHeight` | zobrazovaný počet řádků chatu | `0` = vypnuto |
| `cg_chatTime` | doba zobrazení zpráv chatu | |
| `cg_connectionIconSize` | velikost ikony připojení | |
| `cg_crosshairAlpha` | průhlednost zaměřovače | `0,5` = 50% |
| `cg_crosshairAlphaMin` | minimální průhlednost zaměřovače | |
| `cg_crosshairDynamic` | nastavení pohyblivého zaměřovače | #zakázáno |
| `cg_crosshairEnemyColor` | zčervenání zaměřovače na nepříteli | |
| `cg_cursorHints` | zobrazení/skrytí ikony u interaktivních předmětů | |
| `cg_descriptiveText` | zobrazení/skrytí počtu zabitých nepřátel | |
| `cg_drawBreathHint` | zobrazení/skrytí nápovědy *„Press shift to steady“* | |
| `cg_drawCrosshair` | zobrazení/skrytí zaměřovače | |
| `cg_drawCrosshairNames` | zobrazení/skrytí jména spoluhráče nad zaměřovačem | |
| `cg_drawFPS` | zobrazení/skrytí počítadla FPS | |
| `cg_drawLagometer` | zobrazení/skrytí diagnostiky sítě | |
| `cg_drawMantleHint` | zobrazení/skrytí ikony *„Press space to jump“* | |
| `cg_drawSnapshot ` | zobrazení/skrytí počítadla snapshotů | |
| `cg_drawTurretCrosshair` | | ? |
| `cg_gameBoldMessageWidth` | velikost zvýrazněného textu | |
| `cg_gameMessageWidth` | | ? |
| `cg_headIconMinScreenRadius` | velikost týmové ikony | `0` = vypnuto |
| `cg_hintFadeTime` | | ? |
| `cg_hudChatPosition` | umístění chatu na obrazovce | osa XY |
| `cg_hudCompassMaxRange` | | ? |
| `cg_hudCompassMinRadius` | | ? |
| `cg_hudCompassMinRange` | | ? |
| `cg_hudCompassSize` | | ? |
| `cg_hudCompassSoundPingFadeTime` | | ? |
| `cg_hudCompassSpringyPointers` | | ? |
| `cg_hudDamageIconHeight` | | ? | 
| `cg_hudDamageIconOffset` | | ? |
| `cg_hudDamageIconTime` | | ? |
| `cg_hudDamageIconWidth` | | ? |
| `cg_hudGrenadeIconHeight` | | ? |
| `cg_hudGrenadeIconOffset` | | ? |
| `cg_hudGrenadeIconWidth` | | ? |
| `cg_hudGrenadePointerHeight` | | ? |
| `cg_hudGrenadePointerPivot` | | ? |
| `cg_hudGrenadePointerWidth` | | ? |
| `cg_hudObjectiveMaxRange` | | ? |
| `cg_hudObjectiveMinAlpha` | | ? |
| `cg_hudObjectiveMinHeight` | | ? |
| `cg_hudProneY` | | ? |
| `cg_hudSayPosition` | | ? |
| `cg_hudStanceHintPrints` | zobrazení/skrytí nápovědy pro skrčení a lehnutí | |
| `cg_marks` | zapne/vypne některé detaily(poškození zdi, po výbuchu atd.) | |
| `cg_marksLimit` | maximum zobrazených marks pokud `cg_marks` = `1` | |
| `cg_noTaunt` | eliminace odezvy reproduktorů | asi |
| `cg_predictItems` | určuje, zda hra považuje předmět za sebraný v daném čase | `1` klient, `0` server |
| `cg_scoreboardBannerHeight` | | ? |
| `cg_scoreboardItemHeight` | | ? |
| `cg_scoreboardScrollStep` | | ? |
| `cg_scriptIconSize` | velikost teamové ikony | |
| `cg_subtitleCharHeight` | | ? |
| `cg_subtitleMinTime` | | ? |
| `cg_subtitlePosX` | pozice titulků | osa x |
| `cg_subtitlePosY` | pozice titulků | osa y |
| `cg_subtitles` | vypne/zapne titulky | |
| `cg_subtitleWidthStandard` | | ? |
| `cg_subtitleWidthWidescreen` | | ? |
| `cg_teamChatsOnly` | vypnutí globálního chatu, pouze teamový | |
| `cg_viewsize` | nastavení zobrazení / obrazu v % | >100 = blackbars |
| `cg_voiceIconSize` | velikost voice ikony | |
| `cg_voiceSpriteTime` | doba zobrazení ikonky voice chatu | |
| `cg_weaponCycleDelay` | zpoždění ke kolečku myši | udává počet řádků |
| `cg_youInKillCamSize` | | ? | 

### Scripty

Scriptování je zjednodušeně spouštění různých sekvencí příkazů pomocí buďto klávesou (bindem) nebo načtením konfiguračního souboru.
