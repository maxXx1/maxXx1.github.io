---
title: "Windows XP mode"
date: "2020-09-29"
category: "Windows" 
tags: 
  - "Windows-10"
  - "Windows-XP"
image: 
  path: /img/page/Windows-XP.png
  alt: Windows XP
---

Součástí Windows 10 Pro (narozdíl od Windows 7 Pro) není nativní Windows XP mód. Ale s pomocí Hyper-V není problém si ho vytvořit a plně přizpůsobit.

> Je třeba platná licence Windows XP Pro!
{: .prompt-info }

Nevýhodou oproti nativnímu řešení XP móde na Windows 7 Pro je, že do prostředí Hyper-V se nepřenese licence na hostovaný systém, tudíž bude ve lhůtě 30ti dnů nuceni vložit licenci na Windows XP Pro a systém aktivovat.

## Instalace Hyper-V

![HyperV](/img/2020-09-29-windows-xp-mode/hyper-v1.png)
_Win 10 Pro Hyper-V_

Podporu virtuálního prostředí spustíme v Ovládacích panelech, záložce "Programy a funkce" nalevo klikneme na "Zapnout nebo vypnout funkce systému Windows" a přidáme funkci __Hyper-V__. Bude následovat restart.

Alternativně lze instalaci provést i z prostředí PowerShellu příkazem:

```powershell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
```

## Stažení a úprava VHD

Stáhněte oficiální Windows XP mode (pro Windows 7) přímo ze stránek MS. Níže přikládám odkaz na jeho českou jazykovou mutaci.

[Windows XP Mode](https://www.microsoft.com/cs-cz/download/details.aspx?id=8002)

K dispozici jsou 32 bitové verze systému v klasickém a "N" provedení (bez integrovaného přehrávače WMP). Velikost cca 446 MB.

![vXP](/img/2020-09-29-windows-xp-mode/vXP1.png)
_Stažení_

U staženého instalátoru skrze "Vlastnosti" odblokujte soubor

![vXP2](/img/2020-09-29-windows-xp-mode/vXP2.png)
_Odblokování_

Následně soubor otevřete např. pomocí programu [7-Zip](https://www.7-zip.org/) a extrahujte z něj soubor `XMP` ze složky `sources`.

![vXP3](/img/2020-09-29-windows-xp-mode/vXP3.png)
_Instalátor_

Extrahovaný soubor `XMP` otevřeme stejným způsobem a z jeho útrob extrahujeme soubor virtuálního disku (`VirtualXPVHD`).

![vXP3](/img/2020-09-29-windows-xp-mode/vXP4.png)
_VHD_

Soubor `VirtualXPVHD` opatříme příponou `.vhd` čímž z něj uděláme funkční virtuální disk, který si ihned můžeme dvoj klikem připojit a prohlédnout.

Disk se nám připojí jako další disková jednotka v "Tento počítač". Disk není blokován proti zápisu, tudíž já si do něj např. ihned nakopíroval složku s instalačkami programů, se kterými budu chtít v rámci virtuálního prostředí pracovat.

![vXP5](/img/2020-09-29-windows-xp-mode/vXP5.png)
_Obsah disku_

Po dobu provozu virtuálního stroje, ale disk připojený k hostitelskému počítači být nemůže, takže jej nezapomeňte po provedení změn opět **odpojit**.

## Tvorba virtuálního stroje

Dále si vytvoříme virtuální stroj ve kterém využijeme tento stažený a upravený virtuální disk. Dejte start napište "Hyper-V" a měl by se vám nabídnout "**Správce technologie Hyper-V**". V něm zvolíme možnost "Nová" a následně virtuální počítač.

![Hyper-V2](/img/2020-09-29-windows-xp-mode/hyper-v2.png)
_Hyper-V_

1. Zvolíme jeho název
2. Zvolíme "1. generaci" virtuálního stroje (protože Windows XP neběží na UEFI)
3. Nastavení paměti doporučuji udělat napevno. V mém případě tedy 2GB a bez dynamicky alokované paměti
4. Konfiguraci sítě můžete v tomto kroku ponechat na "nepřipojeno"
5. Ve volbě virtuálního disku máme možnost "**Použít existující virtuální disk**" pomocí které přiřadíme tomuto stroji náš vyextrahovaný `VirtualXPVHD.vhd`
6. Dále už dáme jen dokončit, ale námi vytvořený virtuální počítač zatím nespouštíme.

V prostředí správce Hyper-V klikneme na námi vytvořený virtuální počítač a dáme "**Nastavení**" v okně nastavení zvolíme "**Přidat Hardware**" a zvolíme "**Starší síťový adaptér**" a "**Přidat**".

![oldEth](/img/2020-09-29-windows-xp-mode/image-1.png)
_Přidat síťový adaptér_

Tento síťový adaptér nyní pomocí přepínače nasměrujeme na vaši síťovou kartu, popř. wifi adaptér.

![oldEth2](/img/2020-09-29-windows-xp-mode/image-2.png)
_Virtuální switch_

Tímto by mělo být nastavení virtuálního stroje hotové a vy můžete spouštět.

## Windows XP

V prostředí virtuálního stroje jen po prvním spuštění klasicky dokončíme nastavení instalace.

Dále si můžeme zkontrolovat přístupnost námi vytvořené složky přímo v systému a začít normálně pracovat.

![XPm](/img/2020-09-29-windows-xp-mode/image-3.png)
_Windows XP_

## Testovaný SW pro Windows XP

V prostředí Windows XP SP3 se v našem případě dají provozovat pouze 32 bitové aplikace pro architekturu x86. Takže si níže odložím výpis mnou testovaných verzí:

- **Internetový prohlížeč**: [Internet Explorer 8](https://www.microsoft.com/cs-cz/download/details.aspx?id=40390) / [Mozilla Firefox 52.9.0 ESR](https://ftp.mozilla.org/pub/firefox/releases/52.9.0esr/win32/cs/) / [Supermium](https://win32subsystem.live/supermium/)
- **Kancelářský balík:** MS Office 2007 / [LibreOffice 5.4.7.2](https://downloadarchive.documentfoundation.org/libreoffice/old/5.4.7.2/win/x86/)
- **Práce s archívy:** [7-Zip 23.01](https://www.7-zip.org/download.html)
- **Audio/video:** Windows Media Player 11 / [VLC 3.0.11](https://download.videolan.org/pub/videolan/vlc/last/win32/)
- **PDF prohlížeč:** [Acrobat Reader 11](https://get.adobe.com/cz/reader/otherversions/) / [Foxit Reader 6.23.815](https://cdn01.foxitsoftware.com/pub/foxit/reader/desktop/win/6.x/6.2/enu/FoxitReader623.815_enu_Setup.exe)
- **Anti-virus:** [ADWcleaner 7.4.2](https://downloads.malwarebytes.com/file/adwcleaner-legacy)
- **ADblock pro Firefox:** [uBlock Legacy 1.14.4.22](https://github.com/gorhill/uBlock-for-firefox-legacy/releases/tag/firefox-legacy-1.16.4.22)
- **Práce s oddíly** [AOMEI Partition Asisstant 10.2.0](https://www2.aomeisoftware.com/download/pa/full/10.2.0/PAssist_Setup.exe)
- **File Manager** [Total Commander 11.03](https://totalcommander.ch/1103/tcmd1103x32.exe) / [WinSCP 6.1.2](https://sourceforge.net/projects/winscp/files/WinSCP/6.1.2/)
- A další na... [MSFN.org](https://msfn.org/board/topic/176299-latest-version-of-software-running-on-xp/) a [XPforums.com](https://www.xpforums.com/)

## Nezbytné aktualizace

- [Service pack 3](https://www.microsoft.com/cs-cz/download/details.aspx?id=55460) (v našem případě není třeba)
- Všechny aktualizace po SP3 až do ukončení podpory
    - [Roll-UP update](https://uloz.to/file/ReHrMuKZw/windows-xp-post-sp3-cz-roll-up-update-exe) pro českou verzi
    - [Roll-UP update](https://uloz.to/file/BffgxgPbD/windows-xp-post-sp3-en-roll-up-update-exe) pro anglickou verzi
- [Windows Media Player 11](https://www.download.windowsupdate.com/msdownload/update/v3-19990518/cabpool/windows6.0-kb941651-x86_cf2d8dd55a356b9d27b75ead67ff45cf3d2d9a14.msu)
- Internet Explorer 8 ([v češtině](https://download.microsoft.com/download/7/F/2/7F2D755E-1568-482A-AC6B-2602B50FB88E/IE8-WindowsXP-x86-CSY.exe) / [v angličtině](https://download.microsoft.com/download/C/C/0/CC0BD555-33DD-411E-936B-73AC6F95AE11/IE8-WindowsXP-x86-ENU.exe))
- [DirectX installer](https://www.microsoft.com/cs-cz/download/details.aspx?id=35) v 9.29.1974
- [POSReady 2009](https://www.catalog.update.microsoft.com/ScopedViewInline.aspx?updateid=6f4e581a-5f28-44a1-b3a5-c6c50951556f)
- Všechny ostatní důležité updaty lze stáhnout i jednotlivě z [Windows Update Catalogu](https://www.catalog.update.microsoft.com/)
