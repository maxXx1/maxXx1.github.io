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

#### Nastavení rozhraní 

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

#### Grafické nastavení

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `r_aaAlpha` | druh anti-aliasingu | |
| `r_aaSamples` | úroveň anti-aliasingu | |
| `r_anisotropy` | úroveň anizotropního filtrování | |
| `r_aspectRatio` | poměr stran obrazu | |
| `r_autopriority` | nízká priorita procesu na pozadí | |
| `r_depthPrepassModels` | | ? |
| `r_displayRefresh` | obnovovací frekvence monitoru | |
| `r_distortion` | zpětná vazba po výbuchu | ? |
| `r_dlightLimit` | maximální počet dynamických světel | |
| `r_drawSun` | zobrazení slunce | |
| `r_fullscreen` | režim celé obrazovky | |
| `r_gamma` | nastavení jasu | |
| `r_glow` | nastavení odlesků | jen Dx9 |
| `r_ignorehwgamma` | ignorovat hardwarové nastavení gammy | |
| `r_inGameVideo` | zobrazovat videa ve hře | |
| `r_lodScale` | rychlost obnovování efektů | |
| `r_mode` | rozlišení monitoru | |
| `r_monitor` | identifikace monitoru v případě | více než 1 |
| `r_overbrightBits` | světlost mapy | |
| `r_picmip` | kvalita textur | hodnota > kvalita |
| `r_picmip_bump` | kvalita bump textur | hodnota > kvalita! |
| `r_picmip_manual` | manuální nastavení kvality textur | `0` = `picmip` se neprojeví |
| `r_picmip_spec` | kvalita minimap textur | hodnota > kvalita |
| `r_polygonOffsetBias` | množství textur | `16` = žádné |
| `r_polygonOffsetScale` | množství textur | `4` = žádné |
| `r_portalBevels` | helps cull geometry by portals that are acute when projected onto screen | ? |
| `r_railCoreWidth` | | ? |
| `r_rendererPreference` | verze DirectX | `7` / `9` |
| `r_swapInterval` | synchronizace FSB s frekvencí monitoru | |
| `r_textureMode` | druh filtru textur | |
| `r_zFeather` | metoda generování realistického kouře a efektů počasí | |
| `sc_enable` | dynamické stíny | jen Dx 9 |

#### Nastavení HUD

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `hud_deathQuoteFadeTime` | čas {vlevo dole} | obdoba `con_minicontime` |
| `hud_enable` | zobrazení HUD (dolní část) | |
| `hud_fade_ammodisplay` | zobrazení nábojů | |
| `hud_fade_compass` | zobrazení kompasu | |
| `hud_fade_healthbar` | health bar | server-side |
| `hud_fade_offhand` | počet granátů | |
| `hud_fade_stance` | čas zobrazení postoje | |
| `hud_fadeout_speed` | sprint bar | server-side |
| `hud_flash_period_offhand` | | ? |
| `hud_flash_time_offhand` | | ? |
| `hud_health_pulserate_critical` | | ? |
| `hud_health_pulserate_injured` | | ? |
| `hud_health_startpulse_critical` | | ?
| `hud_health_startpulse_injured` | | ? |

#### Nastavení myši

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `input_viewSensitivity` | | ? |
| `cl_mouseAccel` | akcelerace | |
| `in_mouse` | input mouse | |
| `m_filter` | zvýšení přesnosti ukazatele | |
| `m_forward` | ryhlost nahoru/dolu při invertovaném pohybu | |
| `m_pitch` | rychlost nahoru/dolu při normalnim pohybu | |
| `m_side` | rychlost do stran při invertovaném pohybu | |
| `m_yaw` | rychlost do stran při normalním pohybu | |
| `sensitivity` | citlivost | {hodnota} |

#### Nastavení zvuku

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `mss_3d_provider` | codec 3D zvuku | např. EAX |
| `mss_khz` | nastavení frekvence | |
| `snd_bits` | datový tok | ? |
| `snd_errorOnMissing` | | ? |
| `snd_khz` | | ? |
| `snd_slaveFadeTime` | | ? |
| `snd_stereo` | | ? |
| `snd_touchStreamFilesOnLoad` | | ? |
| `snd_volume` | hlasitost | ? |

#### Síťové nastavení

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `cl_allowDownload` | automatické stahování map | |
| `cl_anonymous` | | ? |
| `cl_freelook` | zapne freelook | |
| `cl_maxpackets` | maximální počet packetů client / server | |
| `cl_maxPing` | maximální akceptovatelný ping | ? |
| `cl_packetdup` | duplikování packetů | |
| `cl_punkbuster` | povolení/zakázání anti-cheatu | PunkBuster |
| `cl_voice` | povolení/zakázání voice chatu | |
| `cl_wwwDownload` | povoleni stahování z FTP | |
| `snaps` | frekvence „gameworld updates“ od serveru | hodnota `sv_fps` (server) |
| `rate` | frekvence přenesených dat client / server | |

#### Pokročilé síťové nastavení

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `net_noipx` | zapnuti/vypnuti protokolu IPX | |
| `net_noudp` | zapnuti/vypnuti protokolu UDP | |
| `net_socksEnabled` | zapnutí/vypnutí požití socks | |
| `net_socksPassword` | nastavení hesla pro socks | |
| `net_socksPort` | port pro socks | |
| `net_socksServer` | socks server | |
| `net_socksUsername` | přihlašovací jméno pro socks | |

#### Nastavení lokalizace

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `loc_forceEnglish` | vynucení ENG (pokud je nativní verze jiná) | |
| `loc_language` | výběr jazyka | `0` ENG/nativní `1` FR `2` DE `3` IT `4` SP |

>Pro Steam verzi je nadřazené nastavení lokalizace ve Steam klientu!
{: .prompt-info }

#### Nastavení konzole

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `con_inputBoxColor` | barva konzole | |
| `con_inputHintBoxColor` | barva nápovědy | |
| `con_minicon` | zobrazení informací {vlevo dole} | |
| `con_miniconlines` | počet řádků infa {vlevo dole} | |
| `con_minicontime` | čas zobrazení infa {vlevo dole} | |
| `con_outputBarColor` | barva posuvníku v rozšířeném zobrazení | |
| `con_outputSliderColor` | barva písma v rozšířeném zobrazení | |
| `con_outputWindowColor` | barva pozadí rozšířeného zobrazení | |
| `con_restricted` | aktivace všech příkazů | `0` |

#### Ostatní nastavení 

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `name` | jméno hráče (nick) | |
| `cl_yawspeed` | rychlost pohybu při zaměřování na klávesnici | horizontálně |
| `cl_pitchspeed` | rychlost pohybu při zaměřování na klávesnici | vertikálně|
| `g_allowvote` | povolení hlasování | |
| `g_useGear` | | ? |
| `com_hunkMegs` | rezervace paměti RAM | v MB |
| `com_introPlayed` | povoleni přehrávaní intra | |
| `com_maxfps` | uzamkne počet snímků za sekundu (FPS) | |
| `com_recommendedSet` |  doporučené nastavení | |

> Rezervovatelná paměť pro ukládání informací, udávaná v MB pomocí příkazu `com_hunkMegs` 
se doporučuje nastavit na 1/3 až 1/2 celkové paměti RAM, což by mělo výrazně zvýšit rychlost načítání map.
{: .prompt-tip }

#### Singleplayer

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `ai_corpseCount` | počet mrtvol (počítačem řízených nepřátel) | |
| `fx_sort` | vypnutí určitých efektů hry | 1 |

> V multiplayeru musí být `fx_sort` nastaveno na hodnotu `1`, jinak je to bráno jako cheat.
{: .prompt-warning }

#### Nastavení na straně serveru

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| sv_framerate_smoothing | vynucení plynulého framerate | 1 |
| sv_allowDownload | povolit stahování | |
| sv_floodProtect | | ? |
| sv_hostname | nastavení jména serveru | |
| sv_maxclients | maximální počet klientů | |
| sv_maxPing | maximální akceptovatelná odezva | |
| sv_maxRate | maximální přenosová rychlost | |
| sv_minPing | minimální akceptovatelná odezva | |
| sv_punkbuster | zapnutí/vypnutí anti-cheat ochrany | |
| sv_reconnectlimit | | ? |
| sv_voice | povolení voice chatu | |
| sv_wwwBaseURL | URL adresa serveru | |
| sv_wwwDlDisconnected | | ? |
| sv_wwwDownload | adresa FTP serveru | | 

#### Informace o hardware

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `sys_configSum` | | ? |
| `sys_cpuGHz` | frekvence procesoru | v GHz |
| `sys_gpu` | typ grafické karty | "název" |
| `sys_sysMB` | množství operační paměti | v MB |

#### Nastavení UI

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `ui_bigFont` | | |
| `ui_browserFriendlyfire` | | |
| `ui_browserKillcam` | | |
| `ui_browserMod` | | |
| `ui_browserShowDedicated` | | |
| `ui_browserShowEmpty` | | |
| `ui_browserShowFull` | | |
| `ui_browserShowNoPassword` | | |
| `ui_browserShowPassword` | | |
| `ui_browserShowPunkBuster` | | |
| `ui_browserShowPure` | | |
| `ui_currentMap` | | |
| `ui_currentNetMap` | | |
| `ui_dedicated` | | |
| `ui_extraBigFont` | | |
| `ui_gametype` | | |
| `ui_joinGametype` | | |
| `ui_netGametype` | | |
| `ui_netGametypeName` | | |
| `ui_netSource` | | |
| `ui_serverStatusTimeOut` | | |
| `ui_smallFont` | | |

#### Nastavení videa

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `vid_xpos` | | |
| `vid_ypos` | | |

#### Nastavení mikrofonu

| cvar | funkce | parametr |
| :-- | :---- | :------ |
| `winvoice_mic_mute` | | |
| `winvoice_mic_reclevel` | | |
| `winvoice_mic_scaler` | | |
| `winvoice_save_voice` | | |

### Scripty

Scriptování je zjednodušeně spouštění různých sekvencí příkazů pomocí buďto klávesou (bindem) nebo načtením konfiguračního souboru.
