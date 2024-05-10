---
title: "Call of Duty 2 - Config a nastavení"
date: "2015-01-24"
category: "Hry"
tags: 
  - "COD2"
image: 
  path: "/img/2015-01-24-call-of-duty-2-config-a-nastaveni/cod2.jpg"
  alt: Call of Duty 2 MP
---

Když hra nejde tak jak má, nebo máte pocit, že váš protivník vidí vice nebo lépe než vy, tak je na vinně nastavení hry. Toto nastavení je více, než několik kolonek v menu. Toto nastavení vám umožní přizpůsobit si hru přesně podle sebe a mít tak obrovský náskok před svými oponenty. Nebo jen optimalizovat hru, aby byla opravdu plynulá. Pokud tedy chcete hrát jako profesionál, věnujte několik minut detailnímu nastavení vaší hry. Tento článek vám pomůže osvojit si nejdůležitější příkazy a nastavení.

## Config - konfigurační soubor

Příkazů a možností na stavení je ve hře mnoho, hra si bere nastavení z konfiguračního souboru, který je umístěn ve výchozím stavu v

```
C:\Program Files (x86)\Activision\Call of Duty 2\Main\players\*nick*
```

Přičemž o složku výše (složka "players") je textový soubor "active" ve kterém je název uživatele jehož nastavení je ve hře momentálně aktivní (v případě, že na jedné hře hraje více uživatelů s různým nastavením, či máte více konfiguračních souborů např. hraní/natáčení videa).

V případě, že hrajete na serverech s uzavřeným klientem, či vlastním nastavením ze strany serveru (modifikované servery), tak se může konfigurační nastavené pro tyto servery nacházet v jiné složce (ve složce s modifikací k daným serverům). To se projevuje rozdílným nastavením hry na daných serverech a na serverech které si sami založíte či pokud se připojíte k tzv. pure (čistému) serveru. Krásný příklad je např. náš český [GamePark.cz](https://www.gamepark.cz/hra/call-of-duty-2 "GP"), který si ukládá svůj vlastní konfigurační soubor, který zlehka upraví (proto vaše speciální úpravy musíte do tohoto souboru vložit extra). Nachází se ve složce:

```
C:\Program Files (x86)\Activision\Call of Duty 2\mappack\players\*nick*
```

Takže pokud chcete upravit základní ale i pokročilé nastavení hry (to nastavení které nelze z menu hry ovlivnit), tak doporučuji editovat přímo tyto soubory např. pomocí programu [PSPad](https://www.pspad.com/cz/download.php "pspad").

Konfigurační soubor není nic jiného než textový soubor s příponou .cfg, který je rozdělen na 2 části, v první se nachází "bindy" což jsou zjednodušeně příkazy na mapování kláves k určité funkci a "seta" příkazy, které nastavují jiné hodnoty v nastavení. V syntaxi:

> bind *klávesa* "*funkce*" (Příklad: `bind A "+moveleft"` - po stisknutí klávesy "A" pohyb vlevo) seta *název_funkce* "*hodnota*" (Příklad: `seta sensitivity "3.87"` - nastaví citlivost myši na hodnotu 3.87)

## Ingame nastavení

Co se týče nastavení ve hře, tak je nutno poznamenat, že všechny hodnoty z konfiguračního souboru lze měnit/přidávat (zadáním toho konkrétního příkazu) či mazat (např. příkazem unbind) přímo z prostředí hry pomocí konzole. Proto nejdůležitější ingame nastavení pro nás bude povolení  konzole. Která se aktivuje standardně skrz klávesu `~` pod klávesou "Escape".

![moznosti hry](/img/2015-01-24-call-of-duty-2-config-a-nastaveni/moznosti-hry.png) 
_Volby -> Možnosti hry_

Z dalšího ingame nastavení by jsme se mohli podívat na nastavení grafiky i když i to je upravitelné přes config a nyní (v roce 2014) již grafické nastavení až tak moc výkon hry jako takové neovlivní. Ale několik málo zásad by se zmínit dalo.

- **Rozlišení obrazu:** Pro zvýšení výkonu je vhodné nastavit nižší optimálně by, ale mělo být stejné jako rozlišení OS <br>
- **Obnovovací frekvence:** Standardně 60Hz - jinak maximum, které zvládne váš monitor <br>
- **Poměr stran:** Standard - jiné nastavení na mém monitoru způsobuje rozmazání některých textů <br> 
- **Filtrování textur:** Bilinearní  má nejmenší nároky na výkon <br>
- **Vyhlazování hran:** Vypnuto - není třeba a má velké nároky na výkon <br> 
- **Použití vykreslovací metody:** DirectX 7 - méně nepotřebných detailů (lepší viditelnost) <br>
- **Synchronizace každého snímku:** NE - snižuje input lag <br> 
- **Optimalizace pro SLI:** NE - pokud nemáte v PC více než jednu grafickou kartu od Nvidia <br>

![Rozdíl v nastavení DirectX](/img/2015-01-24-call-of-duty-2-config-a-nastaveni/COD2_7.jpg) 
_Rozdíl v nastavení DirectX_

**Jemnější okraje kouře:** Vypnout - má 3 hodnoty avšak jejich vliv na hru je sporadický, proto doporučuji vypnout pro snížení nároků na hru a také proto, že ve hře více hráčů chcete přes kouř spíše vidět, než užívat si jeho kvalit.

![COD2_8](/img/2015-01-24-call-of-duty-2-config-a-nastaveni/COD2_8.jpg)

Nastavení textur v dnešní době již nemá téměř žádný vliv na výkon hry, ale obecně platí: 
- **Kvalita textur:** Vyšší 
- **Rozlišení textur:** Pokud možno vyšší 
- **Normální rozložení mapy:** Nižší 
- **Zrcadlové rozložení mapy:** Nižší

![grafika](/img/2015-01-24-call-of-duty-2-config-a-nastaveni/grafika.png)

Nyní tedy můžeme přistoupit k nastavení skrze konzoli či konfigurační soubor. V případě zadávaní do konzole před příkaz přidejte znak lomeno `/`. V případě úpravy konfiguračního souboru pamatujte na to, že hodnota musí být v uvozovkách.

## Natavení zobrazení informací

- **`cg_drawfps 1`** - Zobrazí FPS počítadlo (hodnota `1` - jednoduché počítadlo, `2` - složitější, `3` - časové) Toto je velmi důležité hlavně z toho důvodu, aby bylo zjevné jestli jestli vaše nastavení má nějaký efekt.

- **`cg_drawlagometer 1`** - Tento příkaz zobrazí v pravém dolním rohu obrazovky čtverec ve kterém jsou vykresleny momentální stavy sítě (ping a lagy) v grafické podobě. Lagometer je rozdělen na dvě poloviny - Horní ukazuje synchronizaci vykreslování vašich obrázků s "gameworld updates" přijatých ze serveru.

Pokud si chcete přizpůsobit i nastavení HUD a nebo třeba velikost radaru, tak použijte příkazy vypsané [zde](https://maxxx.cz/posts/cod2-bindy-scripty-prikazy/#nastaven%C3%AD-hud "příkazy").

## Nastavení ovládání

**`cl_mouseAccel 0`** - nastavením hodnoty od 0 do 100 udáte úroveň akcelerace myši - hodnoty `[0 - 100]`

## Natavení pro zvýšení výkonu (CVAR)

- **`cg_blood 0`** - Vypne zobrazování krve 
- **`cg_brass 0`** - Vypnutí odlétávajících nábojnic 
- **`cg_marks 0`** - Vypnutí detailů jako např. díry po kulkách, očouzení od granátů atd. 
  - `cg_markslimit` - Pokud necháte zapnuté `cg_marks`, můžete detaily pouze snížit `[0-1024]` 
- **`r_aaalpha 0`** - Druh anti-aliasingu, hodnoty `[0,1,2]` 
- **`r_aasamples 1`** - Určuje úroveň anti-aliasingu, hodnoty `[1-4]` 
- **`r_anisotropy 2`** - Úroveň anizotropního filtrování - pro multiplayer nevhodné, hodnoty `[2-4]` 
- **`r_autopriority 0`** - Při minimalizování hry se nezmění priorita procesu hry na nízkou (nastavte hodnotu 1 pokud máte slabší PC) 
- **`r_dlightLimit 0`** - Max počet dynamických světel 
- **`r_drawdecals 0`** - Vypnutí detailů, podobné jako `cg_marks` 
- **`r_drawsun 0`** - Vypnutí slunce 
- **`r_fog 0`** - Vypne mlhu 
- **`r\glow 0`** - Vypnutí mraků a odlesků 
- **`r_gpusync 0`** - Synchronizace CPU a GPU. V případě že pozorujete podivné klouzání myši (něco mezi akcelerací a "olejem", zvyšte číslo. Max a default je `3`)
- **`r_forcelod 4`** - Nastavení detailů hlavně lístků a větviček `[0-max, 4-min]`
- **`r_fullbright 1`** - Vypnutí stínů 
- **`r_lodbias 0`** - Úroveň detailů. Snižováním zvýšíte detaily (například vojáky). `0-min, -1000-max` 
- **`r_lodscale 4`** - Vzdálené stromy a keře budou méně vykreslovány 
- **`r_multigpu 1`** - Pokud pozorujete např sekání myši, zkuste vypnout. Ale bez tohoto cvaru nebude fungovat `r_gpusync` 
- **`r_polygonOffsetBias -16`** - Množství textur 
- **`r_polygonOffsetScale -4`** - Množství textur 
- **`r_skincache 0`** - V případě, že máte dostatek RAM, nastavte na `1`, což zvýší plynulost hry díky před-načítání. 
- **`r_skipbackend 1`** - Odstraní některé polygony. V případě že je obrazovka pouze černá, zkuste vypnout 
- **`r_sunflare_max_size 0`** - Vypne oslnění sluncem 
- **`r_swapInterval 1`** - Synchronizace FPS s frekvenecí monitoru
- **`r_textureMode 0`** - Druh filtru textur 
- **`r_zfeather 0`** - (soften smoke edges v option) - Vypnutí komplikované metody realistického vykreslování kouře 
- **`sys_SSE 1`** - povolí rozšířené SSL funkce u procesorů které je podporují

Samozřejmě různě po internetu naleznete příkazů více avšak některé nemají žádný efekt na nastavení hry, některé fungují pouze ve spojení s modifikovanými servery a jiné jsou dokonce brány jako cheat. Z toho důvodu jsem se omezil jen na ty příkazy, které mají největší vliv na výkon a vzhled hry.

### Nastavení textur (nutno nastavovat znovu při načtení mapy)

Toto nastavení velmi ovlivňuje vzhled hry, avšak na výkon v dnešní době již nemá téměř vůbec vliv.

- **`r_picmip_manual 1`** - Toto je to stejné jako nastavení kvality textur ve hře, ujistěte se, že máte nastaveno na hodnotu `1` 
- **`r_picmip 3`** - kvalita mipmap textur (`r_applypicmips`) 
- **`r_picmip_bump 3`** - kvalita bump textur (`r_applypicmips`) 
- **`r_picmip_spec 3`** - obecně menší kvalita light map textur (`r_applypicmips`)

 - **`r_applypicmips`** - Tento příkaz nastaví změnu picmips bez nutnosti `vid_restart`. Toto lze uplatnit po každém načtení mapy. Ale musí se tak činit ve spojení s výše uvedenými příkazy. A jelikož je velmi tristní vypisovat všechny tyto příkazy po každém načtení mapy, tak si toto nastavení můžeme vložit do speciálního configu, který budeme načítat stisknutím klávesové zkratky (bindu).

###  Nastavení využití operační paměti

- **`com_hunkMegs [80 - 512]`**  - Udává paměť v MB, kterou si má hra rezervovat pro ukládání informací, mělo by to zvýšit rychlost načítání map a slouží také k lepšímu využití operační paměti. Doporučuje se 1/3 nebo 1/2 celkové RAM. Tedy např.  pro celkovou velikost RAM 1536 MB si nastavte `com_hunkMegs "384"`

### Nastavení odezvy (ping)

- **`rate 25000`** - Tento příkaz má největší vliv na váš ping a packetloss. Hodnota rate se počítá v BPS (bytes per second) a označuje počet dat přenesených od vás na server. Vždy záleží na rychlosti vašeho připojení - čím rychlejší, tím větší hodnotu můžete nastavit, default je `5000`.
- **`snaps 40`** - Ovlivňuje kolik "gameworld updates" budete od serveru přijímat. Nastavení je závislé na nastavení `sv_fps` na serveru. 
- **`cl_maxpackets 100`** - Omezuje počet packetů poslaných od vás na server. Pokud máte pomalejší upload mělo by vám pomoci pohrát si s tímto nastavením. Nízká hodnota způsobí, že budou pohyby vaší postavy ve hře trhané, naopak vyšší hodnoty zajistí plynulý chod hry. 
- **`cl_timenudge 0`** - Při nastavení timenudge na zápornou hodnotu by mělo zmírnit váš ping (co se týče "pocitu" ze hry). Tuto hodnotu je doporučeno na `0` až `-30`, což je takévětšinou povolené maximum v online ligách. Jestliže ovšem váš ping překračuje hodnotu 100, můžete na publicu používat `cl_timenudge` vyšší, ale ne větší než je váš ping (např. pro ping 100 zkuste použít `cl_timenudge -100`). 

> Na LAN akcích je nastavení `cl_timenudge` na jinou hodnotu než 0 považováno za cheat!
{: .prompt-danger }

- **`cl_packetdup 1`** - Určuje jestli bude a v jakém množství duplikován každý odeslaný packet. Nastavení na `1` je doporučováno pokud máte ve hře problémy s packetloss, což poznáte na Lagomeru červenými čárami a ve hře tak, že se se starceným packetem stratí třeba informace o tom, že jste vystřelili. `0` - packet bude poslán jednou `1` - packet bude poslán 2x (default) Maximální hodnota je `5`. 
- **`g_antilag 1`** - kompenzace pingu

### Ostatní

- **`exec`** _`název_configu.cfg`_ - se používá pro načtení jiného než standardního configu přímo z prostředí console 
- **`r_gamma [0.5 - 3.0]`**  - nastavení jasu
- **`_r_fullscreen 0`** - přepne z režimu celé obrazovky do zobrazení v okně

A mnoho dalšího lze upravit pomocí příkazů [zde](https://maxxx.cz/posts/cod2-bindy-scripty-prikazy/#p%C5%99%C3%ADkazy "příkazy").

## Již hotový config

![pam](/img/2015-01-24-call-of-duty-2-config-a-nastaveni/cod_pam-mode.jpg)
_PAM Mode_

Samozřejmě lze na internetu sehnat mnoho již hotových configů. Ať už pro zvýšení výkonu hry (FPS configy), nebo configy slavných hráčů. Pokud tedy nechcete upravovat config dle vlastních preferencí, můžete se podívat na [configs.eu](https://www.configs.eu/games/callofduty2/ "configs eu") nebo [gamingcfg.com](https://www.gamingcfg.com/game/cod2 "gamingcfg").

eSuba COD2 configy (BLX, Luboshmir, LuckeEEEr, NiO, Nodlle, Plague, Street) - ke stažení [zde](https://1drv.ms/1JAlirR "esuba cfg")
