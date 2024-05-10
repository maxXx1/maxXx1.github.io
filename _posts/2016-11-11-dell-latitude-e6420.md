---
title: "Dell Latitude E6420"
date: "2016-11-11"
tags: 
    - "Dell"
    - "Windows-7"
    - "Windows-10"
category: "Hardware"
image: 
  path: "/img/2016-11-11-dell-latitude-e6420/E6420.jpeg"
  alt: "Dell Latitude E6420"
---

> Rok výroby 2012

## Upgrade z Windows 7 Pro

Pokud provádíte upgrade (což silně nedoporučuji), tak je předně třeba odstranit Dell Data Protection (DDP) – ten je s Windows 10 nekompatibilní.
Při upgrade se také projevuje problém s pohybem kurzoru, který způsobuje problém ovladače touchpadu.

Doporučuji tedy čistou instalaci z EFI média při které sice přijdete o Dell Diagnostic partition, ale předejdete hromadě problémů.

## Instalace Windows 10

1. Vytvořte si USB flash disk s instalací systému pomocí [Media Creation Tool](https://www.microsoft.com/cs-cz/software-download/windows10).
2. Během POSTu (logo Dell) stiskněte F12 – vyberte UEFI USB médium
3. Pokud se vás instalace dotáže na aktivační klíč, použijte klíč Windows 7 Pro, z COA štítku, který bývá umístěn pod baterií.
4. Během instalace se na pokyn instalátoru připojte k WiFi.
5. Po dokončení instalace spusťte aktualizace systému, po jejich nainstalování restartujte.

## Instalace ovladačů

Systém po prvním restartu aktivuje všechny ovladače stažené skrze Windows Update

 - Intel(R) HD Graphics 3000
 - NVIDIA NVS 4200M
 - Dell Touchpad
 - HDA CX11270 Soft Modem
 - Intel(R) 82579LM Gigabit Network Connection

Těchto pět by mělo zůstat neidentifikovaných:

```
Broadcom USH
HardwareID
USB\VID_0A5C&PID_5801&REV_0101&MI_03
USB\VID_0A5C&PID_5801&MI_03
```

```
Broadcom USH w/swipe sensor
HardwareID
USB\VID_0A5C&PID_5801&REV_0101&MI_00
USB\VID_0A5C&PID_5801&MI_00
```

```
Mass Storage
HardwareID
PCI\VEN_1217&DEV_8331&SUBSYS_04941028&REV_05
PCI\VEN_1217&DEV_8331&SUBSYS_04941028
PCI\VEN_1217&DEV_8331&CC_018000
PCI\VEN_1217&DEV_8331&CC_0180
```

```
PCI Serial Port
HardwareID
PCI\VEN_8086&DEV_1C3D&SUBSYS_04941028&REV_04
PCI\VEN_8086&DEV_1C3D&SUBSYS_04941028
PCI\VEN_8086&DEV_1C3D&CC_070002
PCI\VEN_8086&DEV_1C3D&CC_070
```

```
Unknown Device
HardwareID
ACPI\VEN_SMO&DEV_8800
ACPI\SMO8800
*SMO8800
``` 

Identifikoval jsem je pomocí [Window 8 cab file](https://www.dell.com/support/home/cs-cz/drivers/DriversDetails?driverId=JN1VC&amp;fileId=3366980793&amp;osCode=W864&amp;productCode=latitude-e6520&amp;languageCode=EN&amp;categoryId=SM).

## Ovladače pro Windows 10

### BIOS
Aktuální BIOS je velmi důležitý pro kompatibilitu všech ostatních zařízení. <br>
__Datum vydání:__ 16. leden 2016 <br>
__Verze:__ A23 <br>

[Zde](https://downloads.dell.com/FOLDER03495087M/1/E6420A23.exe)

### Čtečka otisků prstů (Firmware)
__Název:__ Dell ControlVault Firmware Update <br>
Pro korektní fungování na Windows 10 je nutno provést aktualizace firmware. <br>
__Datum vydání:__ 16. říjen 2015 <br>
__Verze:__ 23.7.303.0, A29 <br>

[Zde](https://downloads.dell.com/FOLDER01400283M/27/CV_Setup_TJ9CD_A29_ZPE.exe)

### Čtečka otisků prstů (Ovladač)
__Název:__ Dell ControlVault Driver <br>
Ovladač čtečky otisků prstů. <br>
__Datum vydání:__ 11. prosinec 2013 <br>
__Verze:__ 2.3.309.1625, A11 <br>

[Zde](https://downloads.dell.com/FOLDER01400368M/26/CV_Drv_Setup_RDYG9_A11_64bit_ZPE.exe)

### Čtečka paměťových karet
__Název:__ O2 Micro OZ600xxx Memory Card Reader Driver <br>
Ovladač čtečky paměťových karet. <br>
__Datum vydání:__ 30. prosinec 2015 <br>
__Verze:__ 3.0.7.23, A01 <br>

[Zde](https://downloads.dell.com/FOLDER03490877M/1/DRVR_WIN_R300787.EXE)

### Akcelerometr P11
__Název:__ ST Microelectronics Free Fall Sensor Driver <br>
Ovladač senzoru, který zajišťuje uzamknutí HDD při pádu zařízení. <br>
__Datum vydání:__ 30. prosinec 2015 <br>
__Verze:__ 2.0.10.34, A11 <br>

[Zde](https://downloads.dell.com/FOLDER00860804M/1/Chipset_Driver_RCHTX_WN_2.00.10.34_A11.EXE)

## HW Upgrade

### SSD 
- Pro rychlý start a celkově svižnější chod se obecně doporučuje výměna klasického pevného disku za SSD. 
 - V mém případě padla náhodná volba na business řadu [Samsung 750 EVO](https://www.samsung.com/us/business/computing/solid-state-drives/MZ-750250BW) o kapacitě 250GB. 
 - Ale vyzkoušen mám i [Crucual BX200](https://www.crucial.com/usa/en/ct240bx200ssd1) 240GB, taktéž funkční.

![SSDbench](/img/2016-11-11-dell-latitude-e6420/SSDbech.png)
_Samsung 750 Evo_

### RAM

Dellem doporučované maximum je 2 x 4GB moduly, ale na internetu jsem se dočetl, že není problém osadit i dva 8GB moduly. Mnou vyzkoušené, kompatibilní modely jsou.

- [Hynix 4GB DDR3 - HMT351S6CFR8C](https://www.skhynix.com/eolproducts.view.do?pronm=DDR3+SDRAM&amp;srnm=HMT351S6CFR8C&amp;rk=20&amp;rc=module)
- Samsung 4GB DDR3 - M471B5273DH0-CH9
- [Crucial 4GB DDR3L - CT51264BF160B](https://www.crucial.com/usa/en/ct51264bf160b)
- Samsung 2GB DDR3 - M471B5773DH0-CH9
- [Crucial 2GB DDR3L - CT25664BF160B](https://www.crucial.com/usa/en/ct25664bf160b)

Fungovat by ale měla většina běžně dostupných modulů SO-DIMM DDR3. A měli by běžet v Dual-Channel módu.

### WIFI

Výměna [Broadcom DW 1501](https://www.ebay.com.my/itm/Dell-K5Y6D-WLAN-Mini-PCIexpress-Card-Broadcom-DW-1501-WiFi-802-11b-g-n-0K5Y6D-/261977378089?hash=item3cff118d29) za [Intel Centrino Advanced N 6205](https://www.intel.com/content/www/us/en/wireless-products/centrino-advanced-n-6205.html) bez problémů.

