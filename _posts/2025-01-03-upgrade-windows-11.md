---
title: "Windows 10 - Upgrade na Windows 11"
date: "2025-01-03"
tags: 
  - "Widnows-11"
  - "Windows-10"
category: "Windows"
image: 
  path: "img/2024-07-03-windows11-offline-instalace/w11.png"
  alt: "Windows 11"
---

## Požadavky

- **Procesor:** Musí se bezpodmínečně jdenat o minimálně 2 jádrový, 64 bitový procesor 
  (protože Windows 11 již nemá 32bit variantu)
  - [Intel podporované procesory](https://learn.microsoft.com/en-us/windows-hardware/design/minimum/supported/windows-11-supported-intel-processors)
  - [AMD podporované procesory](https://learn.microsoft.com/en-us/windows-hardware/design/minimum/supported/windows-11-supported-amd-processors)
  - [ARM podporované procesory](https://learn.microsoft.com/en-us/windows-hardware/design/minimum/supported/windows-11-supported-qualcomm-processors)
- **Graf. karta:** S podporou standardu WDDM 2.0 a kompatibilní s DirectX 12, starší karty mají problém s načtením ovladače při UEFI bootování. 
  - AMD: Radeon série HD 7730/7750/7770 a novější
  - Nvidia: Geforce série 400/500 a novější (s výjimkou Geforce 405)
- **RAM:** Minimum je 4GB
- **Pevný disk:** Minimum 64GB, oddíly musí být ve formátu GPT
- **Zákl. deska:** Bootování pouze v UEFI (s vypnutou emulací legacy BIOSu, tzv. CSM), povinný Secure Boot (Zabezpečené spuštění)
- **Displej:** HD (720p) s úhlopříčkou větší než 9"
- **OS:** Windows 10 verze 2004 nebo novější 

Všechny výše zmíněné požadavky můžete na svém PC zkontrolovat pomocí [přehledné MS ultility](https://aka.ms/GetPCHealthCheckApp).
Dále bych si také na stránkách výrobce notebooku nebo zákl. desky zkontroloval, jestli jsou dostupné oficiální ovladače nebo budete odkázáni na ty, které vám poskytne Widnows Update. 

![check](/img/2025-01-03-upgrade-windows-11/check.png)

## Způsoby upgrade

Pokud je vše v pořádku, tak si můžete vybrat hned z několika způsobů upgrade.

### Windows Update

Doporučený a aktivně nabízený samotným systémem. Manuálně se k němu ve Windows 10 dostanete:

 `Start`  > `Nastavení` (Win + I) > `Aktualizace a zabezpečení`  > `Windows Update`  > `Vyhledat aktualizace`.

### Pomocník s instalací

Malá ultilita přímo od MS, která systém stáhne a provede vás aktualizací přímo z prostředí Windows 10. 
Můžete stahovat vždy aktuální verzi, přímo [na stránkých Microsoftu](https://go.microsoft.com/fwlink/?linkid=2171764).

### Instalační médium (doporučuju)

Instalační médium (DVD/Flash disk) může posloužit pro upgrade. Stačí pouze spustit instalaci skrze `setup.exe`, přímo v prostředí běžícho Windows 10.
Tato forma upgrade je vhodná pro zařízení, které nemají dostatek místa na disku, pro stažení upgrade nebo pro zařízení, které jsou offline.

Vlastní instalační médium si můžete vytvořit pomocí [Media Creation Tool](https://go.microsoft.com/fwlink/?linkid=2171764) přímo ze stránek Microsoftu.
Tato ultilita flashdisk správně naformátuje a kdykoliv v budoucnu z ní budete moct nabootovat pro případnou čistou instalaci nebo opravu OS.

![media-creation-tool](/img/2025-01-03-upgrade-windows-11/media-tool.png)

### Instalční disk 

Na [stejné stránce](https://go.microsoft.com/fwlink/?linkid=2171764) (dole) se nabízí i možnost stažení obrazu instalačíního disku ve formátu *.ISO.
Takový obraz disku můžete uchovat pro pozdější použití, vypálit na DVD nebo např. použít pro tvorbu alternativního instalačního média.

Toto se vám může hodit např. pokud chcete vytvořit bootovací instalační médium z prostředí Linuxu. V tomto případě můžete využít na tvorbu instalčního média např. program [UNetbootin](https://unetbootin.github.io/), který se nachází přímo v repozitáři Ubutnu PPA.

```bash
sudo add-apt-repository ppa:gezakovacs/ppa
sudo apt-get update
sudo apt-get install unetbootin
```

![unetbootin](/img/2025-01-03-upgrade-windows-11/unetbootin.png)

## Nekompatibilní HW 

> U nekompatibilního HW, je velmi pravděpodobné, že nebude prospsána vaše licence OS na desku nebo nebude možné ověřit vaše HWID, takže bych doporučoval mít připraven svůj licenční klíč na Windows 10, kterým lze oaktivovat Windows 11.
{: .prompt-info }

> U starých procesorů bez instrukčního setu SSE4.2, to na verzi W11 24H2 a vzšší fakt nejde, zkoušel jsem to.
{: .prompt-warning }

### Rufus

- Je třeba stáhnout ([oficální](https://www.microsoft.com/cs-cz/software-download/windows11)) .iso soubor Windows 11
- Nástroj [Rufus](https://rufus.ie/cs/) ve verzi 4.6 nebo vyšší
- Následně stačí použít flash disk větší než 8GB, spusit Rufus a zadat mu vytvoření instalačního média z vámi staženého `Win11_xxxx_Czech_x64.iso`
- Všechno nastavení můžete nechat v defaultu a až při stisknutí tlačítka `spustit` vybrat, které restrikce chcete obejít

![rufus](/img/2025-01-03-upgrade-windows-11/rufus2.png) 

- Rufus změní v originálním .iso pouze hodnoty registru (způsob bypassu)
- Teto způsob vám nabídne jak instalaci, tak upgrade zvolené verze (bez licenčního klíče) nebo verze dle zadaného licenčního klíče.

### FlybyScript

Tento nástroj se nejvíce podobá "Pomocníkovi s instalací", tudíž se oproti Rufusu liší v tom, že nemusíte nic stahovat, nastavovat, řešit, přepínat a můžete upgradovat přímo ze svého stávajícího prostředí Windows 10. 
Nástroj je ke stažení na [GitHubu](https://github.com/builtbybel/Flyby11/releases)

- V nástroji jsou zahrnuty všechny známé způsoy obejití restrikcí
- My si vystačíme s tou první (native), která prakticky pouze spouští instalaci naší verze, ale jakoby se instalovala na server. (kde se tak důsledně nekontrolují požadavky).

![flyby](/img/2025-01-03-upgrade-windows-11/flyby11.png)

### Instalace v módu server

Klasickou instalaci upgrade lze spustit v módu server, která tak striktně nekontroluje požadavky na HW. Tato věc je tam zabudovaná zejména kvůli upgradům ve vitruálních strojích.
Stačí spustit s parametrem:

```bat
setup /product server 
```

### Úprava registru

- Otevřete Editor registru (Windows + R -> napište `regedit` a potvrďte)
- Přejděte na klíč `HKEY_LOCAL_MACHINE\SYSTEM\Setup\MoSetup`
- Vytvořte nový 32bitový DWORD s názvem `AllowUpgradesWithUnsupportedTPMOrCPU` 
- Nastavte jeho hodnotu na `1`
- Restartujte počítač a zkuste znovu provést upgrade

nebo přes PowerShell:

```powershell
reg add HKLM\SYSTEM\Setup\MoSetup /f /v AllowUpgradesWithUnsupportedTPMorCPU /d 1 /t reg_dword
```

## Návrat k Windows 10 

Pokud jste Windows 11 nainstalovali na nepodporovaný počítač nebo vám po upgrade na Windows 11 něco důležitého nefunguje, máte **desetidenní lhůtu** na návrat k Windows 10 přes nabídku Obnovení. 

Po uplynutí této lhůty je možná pouze čistá instalace.

`Start`  > `Nastavení` (Win + I) > `Systém`  > `Obnovení`

![rollback](/img/2025-01-03-upgrade-windows-11/rollback.png)

