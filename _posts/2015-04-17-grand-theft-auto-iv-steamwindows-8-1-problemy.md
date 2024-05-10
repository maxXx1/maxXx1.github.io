---
title: "Grand theft Auto IV - Steam/Windows 8.1/10 problémy"
date: "2015-04-17"
category: "Hry"
tags: 
  - "GTA"
  - "Steam"
  - "Windows-8.1"
  - "Windows-10"
image: 
  path: "/img/2015-04-17-grand-theft-auto-iv-steamwindows-8-1-problemy/gta4com.jpg"
  alt: GTA IV - Complete Edition
---

Vím, že dnes je již doba nakloněna více novému GTA V, avšak pokud by si někdo chtěl připomenout předešlý díl, či čekáte na slevu posledního dílu této slavné série GTA mohl by  vám tento návod pomoci. GTA IV mělo hlavně v distribuci Steamu hodně problémů se spuštěním, na které se jeden po druhém podíváme. Tyto problémy jsou způsobeny hlavně umírající službou GFWL a dalšími přídavky od Microsoftu, kterými je tato hra v rámci exkluzivity MS protkána.

## Problém s Microsoft Visual C++ balíkem

Prvním problémem je který se může projevit zejména na nejnovějších operačních systémech, je problém s instalací balíku Microsoft Visual C++ 2005, který je třeba pro správné fungování SocialClub Launcheru. Na Windows 8.1 64bit může vyhodit chybu již při instalaci. Tuto instalaci provádí Steam automaticky při prvním spuštění hry.

![Visual-C](/img/2015-04-17-grand-theft-auto-iv-steamwindows-8-1-problemy/Visual-C-2005.png)

Pokud se zobrazí výše ukázaná chyba, způsobí to, že se daný balík vůbec nenainstaluje resp. jeho instalace se stornuje a způsobí to chybu `SecuLauncer`, která se projeví po přihlášení do SocialClubu, přes Launcher.

![SecuLauncher](/img/2015-04-17-grand-theft-auto-iv-steamwindows-8-1-problemy/SecuLauncher.png)

Tuto chybu to může vyhodit i když máte již balík nainstalován, ale byl nainstalován např. pro jinou aplikaci (tudíž jiná verze 32/64bit). Nejjednodušší je si toto skutečnost zkontrolovat v

> "Ovládací panely - Programy a funkce"
  
a podívat se zdali se tam nachází položka "Microsoft Visual C++ 2005 Redistributable 32bit" pokud ano, **odinstalujte ji!**

**Řešení:** Stáhněte a ručně nainstalujte __Microsoft Visual C++ 2005 Redistributable Package (x86) SP1__ přímo ze stránek Microsoftu [zde](https://www.microsoft.com/en-us/download/details.aspx?id=5638 "redist").

> Důležité je, aby se skutečně jednalo o verzi x86 (i v případě, že používáte 64bit systém).
{: .prompt-warning }

## Problém s Games For Windows Live

Problém této služby je v tom, že ji Microsoft již před nedávnem [téměř ukončil](https://games.tiscali.cz/tema/s-koncem-games-for-windows-live-je-osud-nekterych-her-nejasny-65139 "ukončení"), s hrou se instaluje starší verze daného programu která je již ukončena nadobro. Proto pro správný běh hry musíte stáhnout polofunkční poslední variantu tohoto troufám si tvrdit balastu. Chyba s GFWL se může projevit na několik úrovních.

- Hra po kliknutí na tlačítko "Play" spadne a nahlásí, že program byl ukončen (Chyba `xlive.dll`)
- Hra se spustí, ale v prostředí hry se nelze přihlásit ke službám GMFL

![gfwl](/img/2015-04-17-grand-theft-auto-iv-steamwindows-8-1-problemy/games_for_windows_live_gfwl.jpg)

**Řešení:** Stáhněte a ručně nainstalujte "Microsoft Games for Windows Marketplace" přímo ze stránek Microsoftu [zde](https://www.xbox.com/en-US/LIVE/PC/DownloadClient "GMFL").

Pokud se vám nedaří přes [Microsoft ID](https://account.live.com/) (Live ID) přihlásit a vrací vám to chybu (_Kód : 80154002_), tak stačí na stránkách [xbox.com/cs-CZ/](https://xbox.com/cs-CZ/) potvrdit svůj email a věk.

## Problém s přihlášením do Social Club

Někdy resp. někomu se stává, že po spuštění hry se nelze přes launcher po vyplnění správných přihlašovacích údajů připojit k Social Clubu. Což neznemožňuje spuštění hry. Hru můžete spustit v režimu Offline a přihlásit se pouze k Microsoft Live. Hra bude fungovat, avšak budete ochuzeni o Multiplayer. pro přihlášení k Social Clubu je zapotřebí mít hru i launcher v aktuální verzi (o což by se měl starat Steam) a potvrzený email k vašemu profilu. Instrukce [zde](https://support.rockstargames.com/hc/en-us/articles/200145226--Updated-1-3-14-Problems-logging-into-Social-Club-to-launch-GTA-IV-for-PC "rock").

![social-club](/img/2015-04-17-grand-theft-auto-iv-steamwindows-8-1-problemy/social-club.png)

**Řešení:** Zkuste se opakovaně přihlašovat, možná se jedná pouze o přetížení serveru.

**Pokud nechcete hrát multiplayer** a tato hláška vás jednoduše obtěžuje, tak můžete přejít do složky s hrou

```
C:\Program Files (x86)\Steam\SteamApps\common\Grand Theft Auto IV\GTAIV
```

- Najděte soubor `paul.dll` a přejmenujte ho např. na `paul.dll.disabled`
- Poté normálně spusťte hru, hláška by se již neměla objevit, ale multiplayer bude nedostupný!

## Social Club vrací pouze Fatal Error

Pokud se launcher Social Clubu vůbec nespustí, je to nejspíše zapříčiněno tím, že je napsán v jazyku .NET a ve vašem počítači vůbec není nainstalováno jeho běhové prostředí. Ve Windows Vista/7 stačilo stáhnout a ručně nainstalovat aktuální balíky .NET Framework přímo ze stránek Microsoftu [zde](https://www.microsoft.com/cs-cz/download/details.aspx?id=17851 "net"). Na Windows 8/8.1/10 je však instalace těchto balíků přímo v systémovém správci součástí systému.

**Řešení:** Přejděte do "Ovládací Panely - Programy a Funkce - Zapnout nebo vypnout funkce systému" (nalevo). Poté co se otevře okno zaklikněte možnosti .NET Framework 3.5 a 4.5

![net](/img/2015-04-17-grand-theft-auto-iv-steamwindows-8-1-problemy/net.png)

## Hra ke spuštění vyžaduje různé .dll (DirectX Error)

Tato chyba také nemá specifickou podobu, avšak ve většině případů se jedná o zastaralý DirectX. Nebo jeho chybnou instalaci v rámci Steamu, při prvním spuštění.

**Řešení:** Stáhněte a ručně nainstalujte "DirectX End-User Runtime" přímo ze stránek Microsoftu [zde](https://www.microsoft.com/cs-cz/download/details.aspx?id=35 "directX").

## Nekonečné načítání

Zaseknutí na obrazovce načítání je způsobeno mnohdy grafickým omezením, které nebere v potaz celkovou grafickou paměť, která je hře k dispozici, ale pouze tu dedikovanou. Tuto hodnotu je vidět ve hře u grafického nastavení...

![video0](/img/2015-04-17-grand-theft-auto-iv-steamwindows-8-1-problemy/video0.jpg)

Pokud potřebujete zjistit kolik máte celkově dostupné grafické paměti tak:

> Klikněte druhým tlačítkem na plochu - Rozlišení obrazovky - Upřesnit nastavení

- Nás zajímá hodnota **Celková dostupná grafická paměť** - v mém případě 4864 MB
- Toto číslo - v mém případě 4864 vydělíme 28 tedy 4864/28=173,7
- Poté ve Steam knihovně klikněte druhým tlačítkem na hru, dejte vlastnosti a Nastavit možnosti spuštění...
- Zde vyplňte příkaz `-availablevidmem xx.x` jen místo xx.x vyplňte vámi vypočítanou hodnotu.
- Pokud nechcete nastavení úplně přepalovat, můžete použít o něco nižší číslo - v mém případě <br> `-availablevidmem 173.0`

![video1](/img/2015-04-17-grand-theft-auto-iv-steamwindows-8-1-problemy/video1.jpg)

## Problémy způsobené lokalizací do češtiny

Několikrát po dobu vývoje lokalizace se objevili problémy spojené s aplikováním češtiny, proto doporučuji stáhnout aktuální češtinu pro **GTA IV (čeština 2.0)** nejlépe [zde](https://www.gta.cz/gta4/download/gta-4-preklady-cz-sk "cz").

A pro datadisk **Episodes from Liberty City** doporučuji aktualizovanou lokalizaci, která lze stáhnout např. [zde](https://www.facebook.com/pages/Episodes-from-Liberty-City-%C4%8Ce%C5%A1tina/358842184148447 "episodescz").

## Možnosti spuštění

I pro tuto hru lze využít tzv. "Launch commands" osobně využívám pro navýšení počtu snímků za sekundu (FPS) pouze tyto:

```
-shadowdensity 0 -viewdistance 10 -texturequality 0 -renderquality 0 -detailquality 10 -nomemrestrict -norestrictions -frameLimit 0"
```

### Steam verze:

1. Klik na hru druhým tlačítkem (v knihovně Steamu)
2. Vlastnosti
3. Možnosti spuštení

### non-Steam verze: 

1. Běžte do složky `C:\Program Files\Steam\SteamApps\common\grand theft auto iv\GTAIV`{: .filepath}
2. Vytvořte zástupce `LaunchGTAIV.exe`
3. K němu následně můžete přidávat launch commands
4. Pro správné spuštění hry, nejprve spusťe `RGSCLauncher.exe` v <br>
`C:\Program Files\Steam\steamapps\common\grand theft auto iv\RGSC`{: .filepath}

### Seznam spoštěcích příkazů

| Tools | Popis | 
| :---: | :--- | 
| `-benchmark` | Spustí benchmark tool a následně ihned hru ukončí |
| `-help` | Vypíše seznam všech launch commands |

| Grafika | Popis | Hodnoty |
| :---: | :--- | :---: |
| `-renderquality` | Nastaví kvalitu renderu | 0 - 4 |
| `-shadowdensity` | Nastaví hustotu stínů | 0 - 16 |
| `-texturequality` | Nastaví kvalitu textur | 0 - 2 |
| `-viewdistance` | Nastaví délku kam dohlédnete | 0 - 99 |
| `-detailquality` | Nastaví kvalitu detailů | 0 - 99 |
| `-novblank` | Zakáže čekání na vblank (Bez Vsync) | |
| `-norestrictions` | Nelimituje nastavení grafiky | |
| `-width` | Nastavuje šířku hlavního okna renderu | def. 800 |
| `-height` | Nastavuje výšku hlavního okna renderu | def. 600 |
| `-safemode` | Spustí grafiku v nejnižším možném nastavení | |
| `-frameLimit` | Omezení snímků na interval obnovovací frekvence | 0 - 1 |
| `-refreshrate` | Nastaví obnovovací frekvenci hlavního okna renderu | 60 - 240 |
| `-fullscreen` | Vynucení fullscreen módu | |
| `-windowed` | Vynucení windowed módu | |
| `-availablevidmem` | Nastaví, kolik fyzické video paměti, je k dispozici | 0.1 - 1 |
| `-percentvidmem` | Nastaví, kolik fyzické video paměti, je k dispozici v procentech | 0 - 99 |
|`-lazydelete`| Drží déle věci ve video paměti (VRAM) | |

| Audio | Popis |
| :---: | :--- | 
| `-fullspecaudio` | Force high-end CPU audio footprint |
| `-minspecaudio` | Force low-end CPU audio footprint |

| System | Popis |
| :---: | :--- | 
| `-noprecache` | Zakáže přednačítání zdrojů |
| `-nomemrestrict` | Zruší restrikce paměti |


## Ověření data vydání

Tento problém se týká pouze krabicových verzí hry, kdy hra při instalaci požaduje ověření data vydání a toto ověření neproběhne korektně. Řešením je přechod k datu kdy byli ještě funkční aktivační servery.

**Pozn.** Tato chyba se objevovala i v době, kdy aktivační servery fungovali korektně, ale datum na koncovém počítači nebylo správně nastavené.

1. Přejděte do Nastavení - Čas a Jazyk - **Datum a Čas**
2. **Vypněte** "Nastavovat čas automaticky"
3. Následně "**Změnit**" datum a čas
4. Zde nastavte rok 2014 nebo nižší a potvrďte
5. Spusťte hru
6. Po úspěšném ověření můžete datum **vrátit** do normálu.

## Další problémy

- Je veřejně známo, že hra vyžaduje aktuální operační systém, tedy v případě Windows Vista Service Pack 2, v případě Windows XP Service Pack 3 a v případě Windows 7 Service Pack 1.
- Je velmi důležité, aby jste měli nainstalovány aktuální grafické ovladače ze stránek výrobce vaší grafické karty ([nVidia](https://www.nvidia.com/Download/index.aspx?lang=en-us "nvida") / [ATi](https://support.amd.com/en-us/download "ati")), tím předejdete chybám jako jsou rozbité textury atd.
- Pokud se někdy stane, že po načtení hry nenačte model hráče (Nico není vidět), tak stačí změnit rozlišení na nějaké jiné a zpět.
- Mnoho dalších problémů, na které jsem osobně nenarazil je vysvětleno [zde](https://forums.steampowered.com/forums/showthread.php?t=762088 "errors").
