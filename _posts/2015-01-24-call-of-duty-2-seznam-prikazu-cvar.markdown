---
layout: post
title: Call of Duty 2 - Seznam příkazů (cvar)
date: '2015-01-24 21:35:12'
tags:
- hash-wordpress
- hash-import-2023-08-28-13-25
---

### Nastavení zobrazení a umístění různých informací

_ **cg\_blood** _ – vypnutí/zapnutí krve  
_ **cg\_brass** _ – vypnutí/zapnutí zobrazení nábojů  
_ **cg\_centerPrintY** _ – poloha zpráv zobrazujících se uprostřed obrazovky  
_ **cg\_chatHeight** _ – maximálně na kolik řádků bude chat,při nule se nezobrazuje  
_ **cg\_chatTime** _ – doba zobrazení zprávy v chatu  
_ **cg\_connectionIconSize** _ – velikost ikony připojení (nevim jiste, ale asi ty když vam vypadne net při hrani)  
_ **cg\_crosshairAlpha** _ – průhlednost zaměřovače (např. 0,5=50%)  
_ **cg\_crosshairAlphaMin** _ – minimální průhlednost zaměřovače  
_ **cg\_crosshairDynamic** _ – nastavení pohyblivého zaměřovače (ve hře nemá nastavení tohoto cvaru efekt)  
_ **cg\_crosshairEnemyColor** _ – při zaměření nepřátele zaměřovač zčervená  
_ **cg\_cursorHints** _ – zobrazení/skrytí ikony u interaktivních předmětů (např. zbraně)  
_ **cg\_descriptiveText** _ – zobrazení/skrytí kolik jste zabili nepřátel  
_ **cg\_drawBreathHint** _ – zobrazení/skrytí nápovědy „Press shift to steady“  
_ **cg\_drawCrosshair** _ – zobrazení/skrytí zaměřovače  
_ **cg\_drawCrosshairNames** _ – zobrazení/skrytí jména spoluhráče nad zaměřovačem  
_ **cg\_drawFPS** _ – zobrazení fps a dalších zajímavostí  
_ **cg\_drawLagometer** _ – zobrazí/skryje lagometer  
_ **cg\_drawMantleHint** _ – zobrazení/skrytí ikony „Press space to jump“  
_ **cg\_drawSnapshot** _ – zobrazení skrytí snapshot count  
_cg\_drawTurretCrosshair – ?_  
_ **cg\_gameBoldMessageWidth** _ – velikost textu ve hře (např. když někoho zabijete)  
_cg\_gameMessageWidth – ?_  
_ **cg\_headIconMinScreenRadius** _ – velikost týmové ikonky (při nule nemizí)  
_cg\_hintFadeTime – ?_  
_ **cg\_hudChatPosition** _ – umístění chatu na obrazovce (x y)  
_cg\_hudCompassMaxRange – ?_  
_cg\_hudCompassMinRadius – ?_  
_cg\_hudCompassMinRange – ?_  
_cg\_hudCompassSize – ?_  
_cg\_hudCompassSoundPingFadeTime – ?_  
_cg\_hudCompassSpringyPointers – ?_  
_cg\_hudDamageIconHeight – ?_  
_cg\_hudDamageIconOffset – ?_  
_cg\_hudDamageIconTime – ?_  
_cg\_hudDamageIconWidth – ?_  
_cg\_hudGrenadeIconHeight – ?_  
_cg\_hudGrenadeIconOffset – ?_  
_cg\_hudGrenadeIconWidth – ?_  
_cg\_hudGrenadePointerHeight – ?_  
_cg\_hudGrenadePointerPivot – ?_  
_cg\_hudGrenadePointerWidth – ?_  
_cg\_hudObjectiveMaxRange – ?_  
_cg\_hudObjectiveMinAlpha – ?_  
_cg\_hudObjectiveMinHeight – ?_  
_cg\_hudProneY – ?_  
_cg\_hudSayPosition – ?_  
_ **cg\_hudStanceHintPrints** _ – zobrazení/skrytí nápovědy pro skrčení a lehnutí  
_ **cg\_marks** _ – zapne/vypne některé detaily(např. kulky ve zdi,poškození po výbuchu atd.)  
_ **cg\_marksLimit** _ – maximum zobrazených marks pokud máte cg\_marks nastaveno na 1  
_ **cg\_noTaunt** _ – asi nastaveni aby jste se neslyšeli v reproduktorech když používáte mikrofon  
_ **cg\_predictItems** _ – určuje, zda hra považuje předmět (zbraň) za sebraný v daném čase, což může určit dle&nbsp;klienta(1) nebo serveru(0).  
Doporučuji nastavit na 0, aby vám nebyl&nbsp;milně indikován předmět, který jste na serveru ještě vlastně nesebrali.  
_cg\_scoreboardBannerHeight – ?_  
_cg\_scoreboardItemHeight – ?_  
_cg\_scoreboardScrollStep – ?_  
_ **cg\_scriptIconSize** _ – velikost teamové ikonky  
_cg\_subtitleCharHeight_ – ?  
_cg\_subtitleMinTime_ – ?  
_ **cg\_subtitlePosX** _ – pozice titulků x  
_ **cg\_subtitlePosY** _ – pozice titulků y  
_ **cg\_subtitles** _ – vypne/zapne titulky  
_cg\_subtitleWidthStandard_ – ?  
_cg\_subtitleWidthWidescreen_ – ?  
_ **cg\_teamChatsOnly** _ – pouze teamový chat  
_ **cg\_viewsize** _ – nastavení zobrazení v % (při menším než 100 je okolo černý rámeček)  
_ **cg\_voiceIconSize** _ – nejspíše velikost ikonky při voice chatu  
_ **cg\_voiceSpriteTime** _ – délka zobrazení ikonky voice chatu nad hlavou hráče  
_ **cg\_weaponCycleDelay** _ – přidává zpoždění ke kolečku myši, abyste nepřetáčeli přes zbraně příliš rychle  
Nezrychluje změnu zbraně, jen udává počet otočení kolečka potřebné k přehození zbraně.  
_cg\_youInKillCamSize_ – ?

### Síťové nastavení (většina)

_ **cl\_allowDownload** _ – automatické stahování map  
_cl\_anonymous_ – ?  
_ **cl\_freelook** _ – zapne freelook  
_ **cl\_maxpackets** _ – Omezuje počet packetů poslaných od vás na server. Pokud máte pomalejší upload mělo by vám&nbsp;pomoci pohrát si s tímto nastavením.  
Nízká hodnota způsobí, že budou pohyby vaší postavy&nbsp;ve hře trhané, naopak vyšší hodnoty zajistí plynulý chod hry.  
_ **cl\_maxPing** _ – maximální&nbsp;akceptovatelný ping (??)  
_ **cl\_packetdup** _ – duplikování packetů  
_ **cl\_punkbuster** _ – povolení/zakázání anti-cheatu (PunkBusteru)  
_ **cl\_voice** _ – povolení/zakázání voice chatu ve hře  
_ **cl\_wwwDownload** _ – povoleni stahování z www stranek (jen na některých serverech)  
_ **snaps –&nbsp;** _Ovlivňuje kolik „gameworld updates“ budete od serveru přijímat. Nastavení je závislé na nastavení „sv\_fps“ na serveru.  
_ **rate** _ –&nbsp;počet dat přenesených od vás na server

### Nastavení konzole

_ **con\_inputBoxColor** _ – barva konzole (místo do kterého se vepisují příkazy)  
_ **con\_inputHintBoxColor** _ – barva nápovědy (zobrazené možnosti, když píšete příkaz)  
_ **con\_minicon** _ – zobrazení informací vlevo dole (kdo koho zabil)  
_ **con\_miniconlines** _ – počet řádků infa vlevo dole  
_ **con\_minicontime** _ –&nbsp;čas za který zmizí řádek v infu vlevo dole  
_ **con\_outputBarColor** _ –&nbsp;v&nbsp;rozšířeném zobrazení konzole (shift+;) barva posuvníku  
_ **con\_outputSliderColor** _ – barva písma v rozšířeném zobrazení  
_ **con\_outputWindowColor** _ –&nbsp;barva pozadí rozšířeného&nbsp;zobrazení  
_ **con\_restricted** _ –&nbsp;aktivace všech příkazů (aktivuje se hodnotou 0)

### Nastavení HUD

_ **hud\_deathQuoteFadeTime** _ –&nbsp;asi čas infa vlevo dole(nejspíše stejné jako con\_minicontime)  
_ **hud\_enable** _ – zobrazení HUD (všechno v dolní části obrazovky)  
_ **hud\_fade\_ammodisplay** _ – zobrazení nábojů  
_ **hud\_fade\_compass** _ –&nbsp;odebere kompas  
_ **hud\_fade\_healthbar** _ – zobrazeni života (Deaktivace funguje jen na některých serverech)  
_ **hud\_fade\_offhand** _ – počet granátů  
_ **hud\_fade\_stance** _ –&nbsp;čas zobrazení postoje  
_ **hud\_fadeout\_speed** _ –&nbsp;kolonka sprintu (Deaktivace funguje jen na některých serverech)  
_hud\_flash\_period\_offhand_ – ?  
_hud\_flash\_time\_offhand_ – ?  
_hud\_health\_pulserate\_critical_ – ?  
_hud\_health\_pulserate\_injured_ – ?  
_hud\_health\_startpulse\_critical_ – ?  
_hud\_health\_startpulse\_injured_ – ?

### Nastavení lokalizace

_ **loc\_forceEnglish** _ –&nbsp;přeložení hry do ENG (např. pokud mate polskou verzi)  
_ **loc\_language** _ – Vyber jazyka 0-ENG (nebo jazyk vaší verze hry) 1-FR 2-DE 3-IT 4-Spanish

### Nastavení myši

_input\_viewSensitivity – ?  
**cl\_mouseAccel** – akcelerace myši  
**in\_mouse** _ –&nbsp;input mouse – použití myši  
_ **m\_filter** _ – zjemnění myši, u mě nemělo vliv na rychlost  
_ **m\_forward** _ –&nbsp;ryhlost myši nahoru/dolu při invertovaném pohybu  
_ **m\_pitch** _ –&nbsp;rychlost myši nahoru/dolu při normalnim pohybu  
_ **m\_side** _ –&nbsp;rychlost myši do stran při invertovaném pohybu  
_ **m\_yaw** _ –&nbsp;rychlost myši do stran při normalním pohybu  
_ **sensitivity** _ – nastavení citlivosti myši

### Nastavení zvuku

_ **mss\_3d\_provider** _ –&nbsp;poskytovatel 3D zvuku (např EAX)  
_ **mss\_khz** _ –&nbsp;nastavení frekvence zvuku  
_snd\_bits – ?_  
 _snd\_errorOnMissing – ?_  
 _snd\_khz – ?_  
 _snd\_slaveFadeTime – ?_  
 _snd\_stereo – ?_  
 _snd\_touchStreamFilesOnLoad – ?_  
 _snd\_volume – ?_

### Pokročilé nastavení sítě

_ **net\_noipx** _ –&nbsp;zapnuti/vypnuti pouziti IPX  
_ **net\_noudp** _ –&nbsp;zapnuti/vypnuti použití UDP  
_ **net\_socksEnabled** _ –&nbsp;zapnutí/vypnutí požití socks  
_ **net\_socksPassword** _ –&nbsp;nastavení hesla pro socks  
_ **net\_socksPort** _ –&nbsp;port pro socks  
_ **net\_socksServer** _ –&nbsp;socks server  
_ **net\_socksUsername** _ –&nbsp;přihlašovací jméno pro socks

### Grafické nastavení

_ **r\_aaAlpha** _ –&nbsp;druh anti-Alisingu  
_ **r\_aaSamples** _ –&nbsp;určuje úroveň anti-aliasingu  
_ **r\_anisotropy** _ –&nbsp;úroveň anizotropního filtrování  
_ **r\_aspectRatio** _ – poměr stran obrazu  
_ **r\_autopriority** _ –&nbsp;při minimalizaci hry se automaticky nastaví priorita na nízkou  
_r\_depthPrepassModels_ – ?  
_ **r\_displayRefresh** _ –&nbsp;obnovovací frekvence monitoru  
_ **r\_distortion** _ –&nbsp;nejspíše&nbsp;zpětná vazba po výbuchu granátu atd.  
_ **r\_dlightLimit** _ –&nbsp;maximální počet vyobrazených dynamických světel  
_ **r\_drawSun** _ –&nbsp;zobrazení&nbsp;slunce  
_ **r\_fullscreen** _ –&nbsp;režim celé obrazovky  
_ **r\_gamma** _ – nastavení jasu  
_ **r\_glow** _ –&nbsp;nastavení odlesků&nbsp;(jen u DirectX 9)  
_ **r\_ignorehwgamma** _ – ignorovat hardwarové nastavení gammy  
_ **r\_inGameVideo** _ –&nbsp;zobrazovat videa ve hře  
_ **r\_lodScale** _ –&nbsp;rychlost obnovování efektů  
_ **r\_mode** _ –&nbsp;rozlišení monitoru  
_ **r\_monitor** _ –&nbsp;identifikace monitoru v případě, že jich máte více (??)  
_ **r\_overbrightBits** _ –&nbsp;světlost mapy  
_ **r\_picmip** _ –&nbsp;kvalita textur (vyšší hodnota = menší kvalita!)  
_ **r\_picmip\_bump** _ –&nbsp;kvalita bump textur (vyšší hodnota = menší kvalita!)  
_ **r\_picmip\_manual** _ –&nbsp;manuální nastavení kvality textur (pokud date „0“ tak se ostatní změny „picmip“ neprojeví)  
_ **r\_picmip\_spec** _ –&nbsp;kvalita minimap&nbsp;textur (vyšší hodnota = menší kvalita!)  
_ **r\_polygonOffsetBias** _ – množství textur (při 16 žádné)  
_ **r\_polygonOffsetScale** _ – množství textur (při 4 žádné)  
_ **r\_portalBevels** _ – helps cull geometry by portals that are acute when projected onto screen (??)  
_ **r\_railCoreWidth** _ –&nbsp;nejspíše&nbsp;tloušťka dráhy kulky  
_ **r\_rendererPreference** _ –&nbsp;použití DirectX 7 nebo 9  
_ **r\_swapInterval** _ –&nbsp;synchronizace FSB s frekvencí monitoru.  
_ **r\_textureMode** _ –&nbsp;druh filtru textur  
_ **r\_zFeather** _ –&nbsp;jedná se o komplikovanou metodu pro generování realistického kouře a&nbsp;efektů počasí.  
_ **sc\_enable** _ –&nbsp;dynamické stíny (jen DirectX 9)

### Ostatní nastavení

_ **name** _ –&nbsp;jméno hráče (nick)  
_ **cl\_yawspeed** _ – rychlost pohybu při zaměřování na klávesnici (horizontálně)  
_ **cl\_pitchspeed** _ – rychlost pohybu při zaměřování na klávesnici (vertikálně)  
_ **g\_allowvote** _ –&nbsp;povolení hlasování  
_g\_useGear_ – ?  
_ **com\_hunkMegs** _ – udává paměť v MB, kterou si má hra rezervovat pro ukládání informací.  
Mělo by to zvýšit&nbsp;rychlost načítání map. Doporučuji 1/3 nebo 1/2 celkové RAM.  
_ **com\_introPlayed** _ – povoleni přehrávaní intra-význam to ma asi jen v singlplayeru  
_ **com\_maxfps** _ –&nbsp;uzamkne počet snímků za sekundu na hodnotě, kterou nastavíte  
_ **com\_recommendedSet** _ – doporučené nastavení

### Singleplayer

_ **ai\_corpseCount** _ – počet mrtvol (pouze Single Player)  
_ **fx\_sort** _ –&nbsp;vypnutí určitých efektů hry – multiplayeru musí být nastaveno na hodnotu &nbsp;1 jinak je to bráno jako cheat

### Nastavení na straně serveru

**_sv\_framerate\_smoothing 1_** – pro vynucení plynulého framerate (uplatní se pouze pokud zakládáte server)  
_ **sv\_allowDownload** _ – povolit stahování  
sv\_floodProtect  
_ **sv\_hostname** _ – nastavení jména serveru  
sv\_maxclients  
sv\_maxPing  
sv\_maxRate  
sv\_minPing  
**_sv\_punkbuster_** – zapnutí/vypnutí anti-cheat ochrany  
sv\_reconnectlimit  
**_sv\_voice_** – povolení voice chatu  
sv\_wwwBaseURL  
sv\_wwwDlDisconnected  
sv\_wwwDownload

### Informace o hardware

sys\_configSum  
sys\_cpuGHz  
sys\_gpu „NVIDIA GeForce FX 5200“  
sys\_sysMB

### Nastavení UI

ui\_bigFont  
ui\_browserFriendlyfire  
ui\_browserKillcam  
ui\_browserMod  
ui\_browserShowDedicated  
ui\_browserShowEmpty  
ui\_browserShowFull  
ui\_browserShowNoPassword  
ui\_browserShowPassword  
ui\_browserShowPunkBuster  
ui\_browserShowPure  
ui\_currentMap  
ui\_currentNetMap  
ui\_dedicated  
ui\_extraBigFont  
ui\_gametype  
ui\_joinGametype  
ui\_netGametype  
ui\_netGametypeName  
ui\_netSource  
ui\_serverStatusTimeOut  
ui\_smallFont

### Nastavení videa

vid\_xpos  
vid\_ypos

### Nastavení mikrofonu

winvoice\_mic\_mute  
winvoice\_mic\_reclevel  
winvoice\_mic\_scaler  
winvoice\_save\_voice

<!--kg-card-end: html-->