---
title: "Jak převést UEFI zpět na Legasy BIOS (Windows 7,8 a 10)"
date: "2020-10-19"
category: "Windows"
tags: 
  - "Windows-10"
  - "Windows-7"
  - "Windows-8"
image:
  path: "/img/2020-10-19-uefi-na-legasy-bios-na-windows-7-8-a-10/bios-uefi.jpg"
  alt: BIOS vs. UEFI
---

Pokud hledáte způsob, jak převést **UEFI** (Unified Extensible Firmware Interface) na **Legacy BIOS** (Basic Input / Output System) na již nainstalovaném systému **bez ztráty dat**, tak můžete pokračovat podle tohoto návodu. Proces byl sice prováděný na Windows 10, ale lze jej použít pro libovolný systém od Windows 7.

## Zjitění stavu

Klávesovou zkratkou `Win` + `R` otevřete dialogové okno "Spustit" napište `msinfo32` a potvrďte klávesou **Enter** pro zobrazení systémových informací.

![msinfo32](/img/2020-10-19-uefi-na-legasy-bios-na-windows-7-8-a-10/msinfo32.png)

V souhrnu systémových informací vás zajímá řádek **režim systému BIOS** (BIOS Mode), pokud je v něm hodnota UEFI, tak můžete pokračovat v převedení výchozího bootování na Legacy.

![info](/img/2020-10-19-uefi-na-legasy-bios-na-windows-7-8-a-10/Snimek-obrazovky-2020-10-19-133910.png)
_msinfo32_

## Formát diskového oddílu

Další, co je třeba ověřit je, jestli je váš systém nainstalován na oddílu zformátovaném jako GUID Table (**GPT**).

K ověření opět použijeme zkratku `Win` + `R` a do okna "Spustit" napište `diskmgmt.msc` a potvrďte klávesou **Enter** pro zobrazení správy disků.

![diskmgmt](/img/2020-10-19-uefi-na-legasy-bios-na-windows-7-8-a-10/diskmgmt.png)

Ve správě disků klikněte druhým tlačítkem na systémový disk, vyberte **Vlastnosti** a v záložce **Svazky** ověřte, zda styl oddílu je skutečně **GPT**.

![diskpart](/img/2020-10-19-uefi-na-legasy-bios-na-windows-7-8-a-10/diskpart.png)
_diskpart_

## Automatický restart

Proto, aby následující operace proběhly korektně je třeba zabránit automatickému restartovaní, takže opět použijeme zkratku `Win` + `R` a do okna "Spustit" napište `sysdm.cpl` a potvrďte klávesou **Enter** pro zobrazení vlastností systému.

![sysdm](/img/2020-10-19-uefi-na-legasy-bios-na-windows-7-8-a-10/sysdm.png)

Ve vlastnostech systému zvolte záložku **Upřesnit** a v sekci Spouštění a zotavení systému možnost **Nastavení...** Následně v sekci Selhání systému deaktivujte možnost **Automatického restartu**.

![zotaveni](/img/2020-10-19-uefi-na-legasy-bios-na-windows-7-8-a-10/zotaveni.png)

## Diskové oddíly

Stáhněte si program na úpravu diskových oddílů. Já jsem zvolil AOMEI Partition Assistant, protože je ve verzi Professional zdarma [k vyzkoušení](http://www2.aomeisoftware.com/download/pa/PAssist_ProDemo.exe) a to pro náš účel plně postačuje.

- Program spustíme a v hlavním okně u našeho systémového disku vybereme možnost **Convert to MBR Disk**.

![mbr](/img/2020-10-19-uefi-na-legasy-bios-na-windows-7-8-a-10/convert-data-disk-to-mbr.png)
_AOMEI Partition Assistant_

- Následně potvrďte **OK** a nahoře spusťte proces tlačítkem **Apply**. Počítač vás vyzve k restartování systému a při načítání provede převedení diskového oddílu.

## Změna způsobu bootování

Nyní můžete v BIOSu změnit způsob bootování z UEFI na Legacy, uložit a nechat zařízení nabootovat až do systému.

> Je také dobré překontrolovat pořadí bootování tak, aby váš disk byl v seznamu na prvním místě.
{: .prompt-tip }

![legacy](/img/2020-10-19-uefi-na-legasy-bios-na-windows-7-8-a-10/bios-legacy.png)

## Kontrola

- Nyní již stačí jen zkontrolovat, že vaše deska již neoperuje v UEFI módu a to tak, že replikujete postup z prvního kroku - v řádku **režim systému BIOS** by již mělo být "**Starší verze**".

![check](/img/2020-10-19-uefi-na-legasy-bios-na-windows-7-8-a-10/Snimek-obrazovky-2020-10-19-135809.png)
_msinfo32_

Následně je také dobré vrátit zpět nastavení automatického restartování při selhání systému. Toho docílíte replikováním postupu z třetího kroku.

![zotaveni](/img/2020-10-19-uefi-na-legasy-bios-na-windows-7-8-a-10/zotaveni2.png)

To by mělo být vše. :)
