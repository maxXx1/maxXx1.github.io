---
title: "Windows 11 - instalace bez Microsoft ID"
date: "2024-07-03"
tags: 
  - "Widnows-11"
category: "Windows"
image: 
  path: "img/2024-07-03-windows11-offline-instalace/w11.png"
  alt: "Windows 11"
---

I Windows 11 z oficiálního zdroje, v posledním buildu 23H2 lze stále nainstalovat v režimu offline, bez Micrososft ID a s lokálním uživatelským účtem.
Pojďme se tedy krok po kroku podávat, jak si vytvořit instalační médium a jak při instalaci správně postupovat.

## Vytvoření instalačního média

Jako instalační médium bych v dnešní době již doporučil libovolný, prázdný flash disk, alespoň o velikosti 8GB.
- Přejděte na stránku [Stažení systému Windows11](https://www.microsoft.com/cs-cz/software-download/windows11)
- V sekci __Vytvoření instalačního média pro Windows 11__ si stáhněte nástroj `MediaCreationTool_Win11_xxHx.exe`
- Nástroj spusťe, přijměte licenční podmínky
- Ponechte doporučené nastavení (Čeština, Windows 11)
- Zvolte médium __USB flash disk__
- Vyberte ze seznamu váš flash disk (Obsah tohoto flash disku bude touto operací smazán)
- Vyčkejte až se instační soubory stáhnou a instalční médium se vytvoří

![media-creation-tool](/img/2024-07-03-windows11-offline-instalace/media-creation-tool.png)

## Instalace 

Vložte vaše instalační médium do počítače na který chcete systém instalovat nebo restartujte zařízení na kterém jste médium vytvářeli a pomocí boot menu (F12, F11, Esc) __nabotujte z USB flash disku__.

![krok1](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_01.png)
- Úspěšné spuštění systému z instalčního média poznáte tak, že vás přivítá obrazovka s výběrem jazyka a místního nastavení instalátoru, klikeme na __Další__

![krok2](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_02.png)
- V dalším kroku klineme na __Nainstalovat__

![krok3](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_03.png)
- Na stránce aktivace produktu zadáme licenční klíč a __Další__ nebo zvolíme možnost __Nemám kód Product Key__ 
  - Vložený licenční klíč idetifikuje verzi (Home nebo Pro) a pokračuje v instalaci této verze
  - Pokud zvolíte instalaci bez licenčního klíče, tak budete muset verzi v dlaším kroku zvolit
  - Pokud máte na svém Microsoft účtu licenci Windows 11 či na daném HW již byl W11 v minulosti aktivován, tak můžte vložit klíč pro digitální akivaci a systém se následně aktivuje po připojení k internetu pomocí digiálního otisku.

Windows 11 Pro
 ```
 VK7JG-NPHTM-C97JM-9MPGT-3V66T
 ```
 
Windows 11 Home
 ```
 YTMG3-N6DKC-DKB77-7M9GH-8HVX7
 ```

![krok4](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_04.png)
- Přijeme licenční podmínky (I kdyby v nich byl zkopírovaný celý Mein Kampf)

![krok5](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_05.png)
- Typ instalace zvolíme __Vlastní__

![krok6](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_06.png)
> Vždy je před instalací dobré, od počítače odpojit všechny ostatní disky, krom toho, na který chceme systém instalovat.
> Předejdeme tak tomu, aby se nám spouštěcí oddíl OS nacpal na jiný, než onen systémový disk.
{: .prompt-tip }

- V tomto kroku zvolíme __Nepřidělené místo na jednotce__ na kterou chceme systém instalovat
- Pokud na disku již jsou vytvořeny nějaké oddíly, tak je smažeme
- Oddíly ručně nevytváříme, instalační proces se o to postará sám

![krok7](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_07.png)
- Počkáme až se soubory na disk nakopírují, rozbalí a nainstalují

![krok8](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_08.png)
- Po tomto kroku bude následnovat automatický restart
- Restarovat by nás to mělo do instalátoru, který se již nachází na systémovém disku (nikoliv na flash disku)
- Pokud se znovu načte instalační médium, tak jej z počítače vytáhnětě a proveďte restart manuální

> Zde se již ujistěte, že váš počítač skutečně není připojen k internetu! Není aktivní wifi adaptér ani připojený síťový kabel.
{: .prompt-warning }

Edice Education/Enterprise/IoT Enterprise a LTSC mají stále možnost přeskočit připojení k internetu a založení lokálního účtu. 

![krok9](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_09.png)
- Na úvodní obrazovce instalátoru stiskneme kombinaci kláves `SHIFT` + `F10` čímž vyvoláme Terminál
- Do terminálu vložíme příkaz:

```bat
OOBE\BYPASSNRO
```

Pokud není script[^footnote] již k dispozici, tak jej aktivujeme pomocí registru:

```bat
reg add HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE /v BypassNRO /t REG_DWORD /d 1 /f
shutdown /r /t 0
```

![krok10](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_10.png)
- A potrdíme `Enter`, měl by následovat automatický restart

![krok9](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_09.png)
- Na úvodní obrazovce nyní vybereme zemi (neovlivňuje jazykové nastavení)

![krok11](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_11.png)
- Vybereme rozložení (layout) klávesnice

![krok12](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_12.png)
- Volitelně ještě můžeme přidat další rozložení klávesnice, mezi kterými lze přepínat pomocí zkratky levý `Alt` + `Shift`

![krok13](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_13.png)
- Nyní vás instalátor vyzve k připojení k internetu, pokud byste tak učilili, tak bude vyžadovat online či doménový účet
- My zvolíme možnost __Nemám internet__

![krok14](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_14.png)
- Zde nás bude instlátor upozorňovat na to, že offline instlace je "omezená"
- Vybereme možnost __Pokračovat s omezenou instalací__

![krok15](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_15.png)
- Zadáme své uživatelské jméno popř. název počítače

![krok16](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_16.png)
- Heslo v tomto okamžiku necháme prázdné, lze nastavit kdykoliv později

![krok17-22](/img/2024-07-03-windows11-offline-instalace/HyperV_Windows%2011_17-22.png)
- V dalších zhruba šesti krocích nastavíme úroveň telemetrie
- Já doporučuji všechno nastavit na __Ne__ nebo __Minimální__ toto nastavení lze vždy v budoucnu změnit
- Po tomto kroku by měl následovat automatický restrart do čistě nainstalovaného systému

_Hotovo!_

## Po instalaci

V tomto bodě:
- se již můžeme opět připojit k internetu
- zkontrolovat úspěšnou aktivaci systému
- spustit instalaci aktualizací Windows Update a Microsoft Store (protože mnoho součástí se již aktualizuje skrze Windows Store)
- nainstalovat ovladače vašeho HW __z oficiálních stránek výrobce__

## Vytvoření lokálního uživatele

- Přímo v instalátoru stiskneme kombinaci kláves `SHIFT` + `F10` čímž vyvoláme Terminál
- Do terminálu vložíme příkaz:

```bat
start ms-cxh:localonly
```

- Což vyvolá přímo systémový dialog na tvorbu lokálního uživatele.

![localonly](/img/2024-07-03-windows11-offline-instalace/ocalonly.png)

- Po jeho založení instalátor přeskočí přímo do nově vytvořeného profilu.

- Nebo přímo z příkazového řádku pomocí příkazů:

```bat
net user /add uzivatel heslo
net localgroup /add administrators uzivatel
```

[^footnote]: Tento script (bypassnro.cmd) není od sestavení 26200.5516/26120.3653 k dispozici.
