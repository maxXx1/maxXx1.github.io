---
layout: post
title: Grand theft Auto IV - Steam/Windows 8.1/10 problémy
tags:
- gta
- steam
- windows
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Vím, že dnes je již doba nakloněna více novému GTA V, avšak pokud by si někdo chtěl připomenout předešlý díl, či čekáte na slevu posledního dílu této slavné série GTA mohl by &nbsp;vám&nbsp;tento návod pomoci. GTA IV mělo hlavně v distribuci Steamu hodně problémů se spuštěním, na které se jeden po druhém podíváme. Tyto problémy jsou způsobeny hlavně umírající službou GFWL a dalšími přídavky od Microsoftu, kterými je tato hra v rámci exkluzivity MS protkána.

<!--more-->

### Problém s&nbsp;Microsoft Visual C++ balíkem

Prvním problémem je který se může projevit zejména na nejnovějších operačních systémech, je problém s instalací balíku Microsoft Visual C++ 2005, který je třeba pro správné fungování SocialClub Launcheru. Na Windows 8.1 64bit může vyhodit chybu již při instalaci. Tuto instalaci provádí Steam automaticky při prvním spuštění hry.

![]( __GHOST_URL__ /wp-content/uploads/2015/04/Visual-C-2005.png)

Pokud se zobrazí výše ukázaná chyba, způsobí to, že se daný balík vůbec nenainstaluje resp. jeho instalace se stornuje a způsobí to chybu „SecuLauncer“, která se projeví po přihlášení do SocialClubu, přes Launcher.

![]( __GHOST_URL__ /wp-content/uploads/2015/04/SecuLauncher.png)

Tuto chybu to může vyhodit i když máte již balík nainstalován, ale byl nainstalován např. pro jinou aplikaci (tudíž jiná verze 32/64bit). Nejjednodušší je si toto skutečnost zkontrolovat v

    
    "Ovládací panely -&nbsp;Programy a funkce"

a podívat se zdali se tam nachází položka „Microsoft Visual C++ 2005 Redistributable 32bit“ pokud ano, **odinstalujte ji!**

**Řešení:&nbsp;** Stáhněte a ručně nainstalujte „Microsoft Visual C++ 2005 Redistributable Package (x86) SP1“ přímo ze stránek Microsoftu [zde](http://www.microsoft.com/en-us/download/details.aspx?id=5638 "redist").

Poznámka: Důležité je, aby se skutečně jednalo o verzi x86 (i v případě, že používáte 64bit systém).

### Problém s Games For Windows Live

Problém této služby je v tom, že ji Microsoft již před nedávnem [téměř ukončil](http://games.tiscali.cz/tema/s-koncem-games-for-windows-live-je-osud-nekterych-her-nejasny-65139 "ukončení"), s hrou se instaluje starší verze daného programu která je již ukončena nadobro. Proto pro správný běh hry musíte stáhnout polofunkční poslední variantu tohoto troufám si tvrdit balastu. Chyba s GFWL se může projevit na několik úrovních.

- Hra po kliknutí na tlačítko „Play“ spadne a nahlásí, že program byl ukončen (Chyba xlive.dll)
- Hra se spustí, ale v prostředí hry se nelze přihlásit ke službám GMFL

![]( __GHOST_URL__ /wp-content/uploads/2015/04/20130816_games_for_windows_live_gfwl.jpg)

**Řešení:** &nbsp;Stáhněte a ručně nainstalujte „Microsoft Games for Windows Marketplace“ přímo ze stránek Microsoftu [zde](http://www.xbox.com/en-US/LIVE/PC/DownloadClient "GMFL").

Pokud se vám nedaří přes [Microsoft ID](http://outlook.cz) (Live ID) přihlásit a vrací vám to chybu (Kód : 80154002), tak stačí na stránkách&nbsp;[xbox.com/cs-CZ/](http://xbox.com/cs-CZ/)&nbsp;potvrdit svůj email a věk.

### Problém s přihlášením do Social Club

Někdy resp. někomu se stává, že po spuštění hry se nelze přes launcher po vyplnění správných přihlašovacích údajů připojit k Social Clubu. Což neznemožňuje spuštění hry. Hru můžete spustit v režimu Offline a přihlásit se pouze k Microsoft Live. Hra bude fungovat, avšak budete ochuzeni o Multiplayer. pro přihlášení k Social Clubu je zapotřebí mít hru i launcher v aktuální verzi (o což by se měl starat Steam) a potvrzený email k vašemu profilu. Instrukce [zde](https://support.rockstargames.com/hc/en-us/articles/200145226--Updated-1-3-14-Problems-logging-into-Social-Club-to-launch-GTA-IV-for-PC "rock").

![]( __GHOST_URL__ /wp-content/uploads/2015/04/social-club-300x291.png)

**Řešení:&nbsp;** Zkuste se opakovaně přihlašovat, možná se jedná pouze o přetížení serveru.

**Pokud nechcete hrát multiplayer** a tato hláška vás jednoduše obtěžuje, tak můžete přejít do složky s hrou

    
    C:\Program Files (x86)\Steam\SteamApps\common\Grand Theft Auto IV\GTAIV

- Najděte soubor&nbsp;„paul.dll“ a přejmenujte ho např. na „paul.dll.disabled“
- Poté normálně spusťte hru, hláška by se již neměla objevit, ale multiplayer bude nedostupný!

### Social Club vrací pouze Fatal Error

Pokud se launcher Social Clubu vůbec nespustí, je to nejspíše zapříčiněno tím, že je napsán v jazyku .NET a ve vašem počítači vůbec není nainstalováno jeho běhové prostředí.  
Ve Windows Vista/7 stačilo stáhnout a ručně nainstalovat aktuální balíky&nbsp;.NET Framework přímo ze stránek Microsoftu [zde](http://www.microsoft.com/cs-cz/download/details.aspx?id=17851 "net"). Na Windows 8/8.1/10 je však instalace těchto balíků přímo v systémovém správci součástí systému.

**Řešení:** &nbsp;Přejděte do „Ovládací Panely – Programy a Funkce – Zapnout nebo vypnout funkce systému“ (nalevo). Poté co se otevře okno zaklikněte možnosti .NET Framework 3.5 a 4.5

[![]( __GHOST_URL__ /wp-content/uploads/2015/04/net-300x263.png)]( __GHOST_URL__ /wp-content/uploads/2015/04/net.png)

### Hra ke spuštění vyžaduje různé .dll (DirectX Error)

Tato chyba také nemá specifickou podobu, avšak ve většině případů se jedná o zastaralý DirectX. Nebo jeho chybnou instalaci v rámci Steamu, při prvním spuštění.

**Řešení:&nbsp;** Stáhněte a ručně nainstalujte „DirectX End-User Runtime“ přímo ze stránek Microsoftu [zde](https://www.microsoft.com/cs-cz/download/details.aspx?id=35 "directX").

### Nekonečné načítání

Zaseknutí na obrazovce načítání je způsobeno mnohdy grafickým omezením, které nebere v potaz celkovou grafickou paměť, která je hře k dispozici, ale pouze tu dedikovanou. Tuto hodnotu je vidět ve hře u grafického nastavení…

![]( __GHOST_URL__ /wp-content/uploads/2015/04/video0.jpg)

Pokud potřebujete zjistit kolik máte celkově dostupné grafické paměti tak:

> Klikněte druhým tlačítkem na plochu – Rozlišení obrazovky – Upřesnit nastavení

- Nás zajímá hodnota **Celková dostupná grafická paměť&nbsp;** – v mém případě 4864 MB
- Toto číslo – v mém případě 4864 vydělíme 28 tedy 4864/28=173,7
- Poté ve Steam knihovně klikněte druhým tlačítkem na hru, dejte vlastnosti a Nastavit možnosti spuštění…
- Zde vyplňte příkaz „ **-availablevidmem**  **xx.x** “ jen místo xx.x vyplňte vámi vypočítanou hodnotu.
- Pokud nechcete nastavení úplně přepalovat, můžete použít o něco nižší číslo – v mém případě&nbsp;„ **-availablevidmem** &nbsp; **173.0** „

![]( __GHOST_URL__ /wp-content/uploads/2015/04/video1-300x40.jpg)

### Problémy způsobené lokalizací do češtiny

Několikrát po dobu vývoje lokalizace se objevili problémy spojené s aplikováním češtiny, proto doporučuji stáhnout aktuální češtinu pro **GTA IV (čeština 2.0)** nejlépe [zde](http://www.gta.cz/gta4/download/gta-4-preklady-cz-sk "cz").

A pro datadisk&nbsp; **Episodes from Liberty City** doporučuji aktualizovanou lokalizaci, která lze stáhnout např. [zde](https://www.facebook.com/pages/Episodes-from-Liberty-City-%C4%8Ce%C5%A1tina/358842184148447 "episodescz").

### Možnosti spuštění

I pro tuto hru lze využít tzv. „Launch commands“ osobně využívám pro navýšení počtu snímků za sekundu (FPS) pouze tyto:

> -shadowdensity 0 -viewdistance 10 -texturequality 0 -renderquality 0 -detailquality 10 -nomemrestrict -norestrictions -frameLimit 0"

- Klik na hru druhým tlačítkem (v knihovně Steamu) – vlastnosti – Možnosti spuštění…
- Kompletní seznam příkazů a jejich popis naleznete [zde](http://steamcommunity.com/sharedfiles/filedetails/?id=427001293 "launch settings").

### Ověření data vydání

Tento problém se týká pouze krabicových verzí hry, kdy hra při instalaci požaduje ověření data vydání a toto ověření neproběhne korektně. Řešením je přechod k datu kdy byli ještě funkční aktivační servery.

**Pozn.** Tato chyba se objevovala i v době, kdy aktivační servery fungovali korektně, ale datum na koncovém počítači nebylo správně nastavené.

1. Přejděte do Nastavení – Čas a Jazyk – **Datum a Čas**
2. **Vypněte** „Nastavovat čas automaticky“
3. Následně „ **Změnit** “ datum a čas
4. Zde nastavte rok 2014 nebo nižší a potvrďte
5. Spusťte hru
6. Po úspěšném ověření můžete datum **vrátit** do normálu.

### 

### Další problémy

- Je veřejně známo, že hra vyžaduje aktuální operační systém, tedy v případě Windows Vista Service Pack 2, v případě Windows XP Service Pack 3 a v případě Windows 7 Service Pack 1.
- Je velmi důležité, aby jste měli nainstalovány aktuální grafické ovladače ze stránek výrobce vaší grafické karty ([nVidia](http://www.nvidia.com/Download/index.aspx?lang=en-us "nvida") / [ATi](http://support.amd.com/en-us/download "ati")), tím předejdete chybám jako jsou rozbité textury atd.
- Pokud se někdy stane, že po načtení hry nenačte model hráče (Nico není vidět), tak stačí změnit rozlišení na nějaké jiné a zpět.
- Mnoho dalších problémů, na které jsem osobně nenarazil je vysvětleno [zde](http://forums.steampowered.com/forums/showthread.php?t=762088 "errors").

Pokud jste narazili na další problémy se spuštěním hry, tak neváhejte a zanechte váš dotaz pod tímto článkem v komentářích. Pokusím se Vám pomoci.

<!--kg-card-end: html-->