---
title: "Windows 10 - Redukce velikosti"
date: "2025-01-09"
tags: 
  - "Windows-10"
category: "Windows"
image: 
  path: "/img/page/Windows_10.jpg"
  alt: "Windows 10"
---

I v dnešní době jsou v oběhu zařízení s velmi malým, nevyměnitelným úložištěm (různé eMMC), slabým procesorem (Atomy, Celerony) a nebo malou integrvavnou operační pamětí. Hromada těchto zařízení šla na trh s Windows 8.1, je plně kompatibilní s Windows 10, ale tento operační systém buď neutáhnou nebo se na ně nevleze.

## Tiny10 v2303

Tým NTDEV se postaral o odlehčenou variantu Windows 10, která staví na Windows 10 LTSC 2021 v nejnovějším sestavení 23H1 (x64/x86).
Tato varianta si klade za cíl být odlehčenou verzí Windows 10 pro počítače nižší třídy, avšak v ní nechybí nic podstatného.

- běží na procesoru x86
- doporučená paměť je 2 GB
- velikost disku 16 GB (po instalaci zabere asi 5 GB)
- možnost aktualizací (Windows Update)
- možnost doinstalovaní funkcí OS `Windows Component Store`
- lze doinstalovat libovolný jazykový balíček (včetně češtiny)
- funkční Windows Defender
- vydálená plocha
- lze upgradovat na Tiny11

{% include embed/youtube.html id='S0sTet7_FyE' %}

Ke stažení na [Archive.org](https://archive.org/details/tiny-10_202301).


# Již nainstalovaný systém

Pokud je již systém nainstalovaný, tak se kombinací následujícíh kroků můžete dostat k úspoře prostoru, která se ale bude lišit v závislosti na verzi operačního systému a konkrétním zařízení. Mě se podařilo **ušetřit 6.5GB** na běžné instalaci Windows 10 Home x64. 

## Compact OS

Compact OS je integrovaný nástroj, který zkomprimuje systémové soubory a aplikace, aby uřetřil místo na disku.
Technicky se jená o náhradu nástroje `WIMBoot`, který je v systému stále přítomný, ale Compact OS je efektnivnější. 

- stačí spustit `cmd` jako správce a napsat příkaz, který ověří, jestli je komprimace možná:

```powershell
Compact.exe /CompactOS:query
```

- pokud ano, tak můžeme přístoupit k samotnému procesu komprimace:

```powershell
Compact.exe /CompactOS:always
```

![compactos](/img/2025-01-09-w10-redukce-velikosti/compactos.png)
_Celý proces může trvat až 20 minut_

- dekomprimaci můžete provést pomocí stejného nástroje s parametrem:

```powershell
Compact.exe /CompactOS:never
```

## Vypnutí hibernace 

> Je možné pouze, pokud je na daném zařízení (ve schématu napájení) Hibernace vůbec dostupná.
{: .prompt-info }

Daší co v systému zabírá místo a časem může "růst" jsiz data hibernace.
Systém dovoluje zmenšit velikost souboru `hiberfil.sys` nebo jej úplně odstranit.

- v `cmd` -> zmenšení o 30% pomocí příkazu:

```powershell
powercfg /h /type reduced
```

- úplné vypnutí hibernace pomocí příkazu:

```powershell
powercfg /h /off
```

- nebo manuální nastavení velikosti příkazem:

```powershell
powercfg /h /size 100
```

## Vzpnutí stránkovacího souboru

Virtuální paměť `pagefile.sys` je zjednodušeně vyhrazené místo na disku, do kterého se ukládají veěci, které se již nevlezou do operační paměti (RAM).
Velikost takto přiděleného souboru lze redukovat, soubor lze přesunout na jiný disk či úplně virtuální paměť (stránkovací soubor) zakázat.
Zakázání virtuální paměti bych doporučoval **pouze v případě, že máte v daném zařízení dostatek paměti operační**. V opačném případě se vaše zařízení velmi zpomalí, protože když operační paměť dojde, tak se bude muset spustit proces čištění a čekat, až se paměť uvolní. 

`Tento počítač` -> `Vlastnosti` -> `Upřesnit nastavení systému Windows` -> `Nastavení` -> `Změnit`

![pagefile](/img/2025-01-09-w10-redukce-velikosti/pagefile.jpg)

## Vyčištění složky WinSxS

Ve Windows se nachází složka `WinSxS`, která slouží jako úložiště komponent pro systém a aktualizace, tato složka taky umí zabírat hromadu místa.

> Manuálním mazáním soborů ze složky WinSxS nebo smazáním složky samotné si můžete způsobit poškození systému nebo procesu aktualizací.
{: .prompt-warning }

- nepotřebné soubory z této složky můžete smazat pomocí nástroje `DISM`:

```powershell
Dism.exe /online /Cleanup-Image /StartComponentCleanup
```

- nebo můžete použít ještě s parametrem `/ResetBase`, který smaže všechny, již použité verze komponent

```powershell
Dism.exe /online /Cleanup-Image /StartComponentCleanup /ResetBase
```

## Zakázání bodů obnovy

Ochrana sysnému je skvělá věc. Vytváří snapshoty systému a vy se díky tomu můžete v případě havárie vracet k automatickým (nebo manuálně tvořeným) bodům obovy. Jenže to zabírá místo. Ochranu systému lze deaktivovat. 

- pomocí Powershellu s oprávněním správce spustíme příkaz:

```powershell
Disable-ComputerRestore -Drive “C:\”
```

![snapshot](/img/2025-01-09-w10-redukce-velikosti/snapshot.png)

- tuto opraci lze vzít zpět příkazem:

```powershell
Enable-ComputerRestore -Drive “C:\”
```

## Čištění dočasných souborů

Windows si v jednom kuse ukládá různé došasné soubory (...tempy, miniatury atd.), které potřebuje pro rychlejší běh, aby je neustále nemusel vytvářet znova. Mezi dočasné systémové soubory lze ale také řadit např. předchozí instalace Windows (pokud je OS po upgrade), obsah koše nebo stažené aktualizace.
Všeho tohohle se můžete zbavit pomocí integrovaného čistícího nástroje, který spustíte příkazem:

```powershell
CLEANMGR /SAGESET:1
```

