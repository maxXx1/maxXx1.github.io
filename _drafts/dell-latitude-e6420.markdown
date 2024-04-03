---
layout: post
title: Dell Latitude E6420
tags:
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Rok výroby 2012

&nbsp;

### Upgrade z Windows 7 Pro

Pokud provádíte upgrade (což silně nedoporučuji), tak je předně třeba odstranit&nbsp;Dell Data Protection (DDP) – ten je s Windows 10 nekompatibilní. Při upgrade se také projevuje problém s pohybem kurzoru, který způsobuje problém ovladače touchpadu.

Doporučuji tedy čistou instalaci z EFI média při které sice přijdete o&nbsp;Dell Diagnostic partition, ale předejdete hromadě problémů.

### Instalace Windows 10

1. Vytvořte si USB flash disk s instalací systému pomocí [Media Creation Tool](https://www.microsoft.com/cs-cz/software-download/windows10).
2. Během POSTu (logo Dell) stiskněte F12 – vyberte UEFI USB médium
3. Pokud se vás instalace dotáže na aktivační klíč, použijte klíč Windows 7 Pro, z COA štítku, který bývá umístěn pod baterií.
4. Během instalace se na pokyn instalátoru připojte k WiFi.
5. Po dokončení instalace spusťte aktualizace systému, po jejich nainstalování restartujte.

### Instalace ovladačů

Systém po prvním restartu aktivuje všechny ovladače stažené skrze Windows Update

- Intel(R) HD Graphics 3000
- NVIDIA NVS 4200M
- Dell Touchpad
- HDA CX11270 Soft Modem
- Intel(R) 82579LM Gigabit Network Connection

Těchto pět by mělo zůstat neidentifikovaných:

[well type=“well-sm“]

1. Broadcom USH  
HardwareID  
USB\VID\_0A5C&PID\_5801&REV\_0101&MI\_03  
USB\VID\_0A5C&PID\_5801&MI\_03
2. Broadcom USH w/swipe sensor  
HardwareID  
USB\VID\_0A5C&PID\_5801&REV\_0101&MI\_00  
USB\VID\_0A5C&PID\_5801&MI\_00
3. Mass Storage  
HardwareID  
PCI\VEN\_1217&DEV\_8331&SUBSYS\_04941028&REV\_05  
PCI\VEN\_1217&DEV\_8331&SUBSYS\_04941028  
PCI\VEN\_1217&DEV\_8331&CC\_018000  
PCI\VEN\_1217&DEV\_8331&CC\_0180
4. PCI Serial Port  
HardwareID  
PCI\VEN\_8086&DEV\_1C3D&SUBSYS\_04941028&REV\_04  
PCI\VEN\_8086&DEV\_1C3D&SUBSYS\_04941028  
PCI\VEN\_8086&DEV\_1C3D&CC\_070002  
PCI\VEN\_8086&DEV\_1C3D&CC\_070
5. Unknown Device  
HardwareID  
ACPI\VEN\_SMO&DEV\_8800  
ACPI\SMO8800  
\*SMO8800

[/well]

Identifikoval jsem je pomocí [Window 8 cab file](http://www.dell.com/support/home/us/en/19/Drivers/DriversDetails?driverId=JN1VC&amp;fileId=3366980793&amp;osCode=W864&amp;productCode=latitude-e6520&amp;languageCode=EN&amp;categoryId=SM).

### Windows 10 Driver (Ovladače pro Windows 10)

[toggles class=“Drivers“]  
[toggle title=“BIOS“ class=“in“] **Info:** Aktuální BIOS je velmi důležitý pro kompatibilitu všech ostatních zařízení.  
**Datum vydání:** 16. leden 2016  
**Verze:** A23

[button style=“btn-default btn-xs“ icon=“glyphicon glyphicon-download-alt“ align=“left“ iconcolor=“#0fa5d9″ type=“link“ target=“false“ title=“Download“ link=“http://downloads.dell.com/FOLDER03495087M/1/E6420A23.exe“ linkrel=““]&nbsp;[button style=“btn-default btn-xs“ icon=“fa fa-info-circle“ align=“left“ iconcolor=“#0fa5d9″ type=“link“ target=“true“ title=“Info“ link=“http://www.dell.com/support/home/us/en/04/Drivers/DriversDetails?driverId=KVY0T“ linkrel=““][/toggle]  
[toggle title=“Čtečka otisků prstů (Firmware)“] **Název:&nbsp;Dell ControlVault Firmware Update**  
**Info:** &nbsp;Pro korektní fungování na Windows 10 je nutno provést aktualizace firmware.  
**Datum vydání:** 16. říjen&nbsp;2015  
**Verze:** 23.7.303.0, A29

[button style=“btn-default btn-xs“ icon=“glyphicon glyphicon-download-alt“ align=“left“ iconcolor=“#0fa5d9″ type=“link“ target=“false“ title=“Download“ link=“http://downloads.dell.com/FOLDER01400283M/27/CV\_Setup\_TJ9CD\_A29\_ZPE.exe“ linkrel=““]&nbsp;[button style=“btn-default btn-xs“ icon=“fa fa-info-circle“ align=“left“ iconcolor=“#0fa5d9″ type=“link“ target=“true“ title=“Info“ link=“http://www.dell.com/support/home/us/en/04/Drivers/DriversDetails?driverId=TJ9CD“ linkrel=““][/toggle]  
[toggle title=“Čtečka otisků prstů (Ovladač)“]

**Název: Dell ControlVault Driver**  
**Info:&nbsp;** Ovladač čtečky otisků prstů.  
**Datum vydání:** &nbsp;11. prosinec 2013  
**Verze:** 2.3.309.1625, A11

[button style=“btn-default btn-xs“ icon=“glyphicon glyphicon-download-alt“ align=“left“ iconcolor=“#0fa5d9″ type=“link“ target=“false“ title=“Download“ link=“http://downloads.dell.com/FOLDER01400368M/26/CV\_Drv\_Setup\_RDYG9\_A11\_64bit\_ZPE.exe“ linkrel=““]&nbsp;[button style=“btn-default btn-xs“ icon=“fa fa-info-circle“ align=“left“ iconcolor=“#0fa5d9″ type=“link“ target=“true“ title=“Info“ link=“http://www.dell.com/support/home/us/en/19/Drivers/DriversDetails?driverId=RDYG9″ linkrel=““]

[/toggle]  
[toggle title=“Čtečka paměťových karet“]

**Název: O2 Micro OZ600xxx Memory Card Reader Driver**  
**Info:&nbsp;** Ovladač čtečky paměťových karet.  
**Datum vydání:** &nbsp;30. prosinec 2015  
**Verze:** 3.0.7.23, A01

[button style=“btn-default btn-xs“ icon=“glyphicon glyphicon-download-alt“ align=“left“ iconcolor=“#0fa5d9″ type=“link“ target=“false“ title=“Download“ link=“http://downloads.dell.com/FOLDER03490877M/1/DRVR\_WIN\_R300787.EXE“ linkrel=““]&nbsp;[button style=“btn-default btn-xs“ icon=“fa fa-info-circle“ align=“left“ iconcolor=“#0fa5d9″ type=“link“ target=“true“ title=“Info“ link=“http://www.dell.com/support/home/cz/cs/czdhs1/Drivers/DriversDetails?driverId=KC9W0″ linkrel=““]

[/toggle]  
[toggle title=“Akcelerometr P11″]

**Název: ST Microelectronics Free Fall Sensor Driver**  
**Info:&nbsp;** Ovladač senzoru, který zajišťuje uzamknutí HDD při pádu zařízení.  
**Datum vydání:** &nbsp;30. prosinec 2015  
**Verze:** 2.0.10.34, A11

[button style=“btn-default btn-xs“ icon=“glyphicon glyphicon-download-alt“ align=“left“ iconcolor=“#0fa5d9″ type=“link“ target=“false“ title=“Download“ link=“http://downloads.dell.com/FOLDER00860804M/1/Chipset\_Driver\_RCHTX\_WN\_2.00.10.34\_A11.EXE“ linkrel=““]&nbsp;[button style=“btn-default btn-xs“ icon=“fa fa-info-circle“ align=“left“ iconcolor=“#0fa5d9″ type=“link“ target=“true“ title=“Info“ link=“http://www.dell.com/support/home/cz/cs/czdhs1/Drivers/DriversDetails?driverId=RCHTX“ linkrel=““]

[/toggle]  
[/toggles]

### HW Upgrade

[tabs class=“yourcustomclass“]  
[tab title=“SSD“ active=“active“]

Pro rychlý start a celkově svižnější chod se obecně doporučuje výměna klasického pevného disku za SSD. V mém případě padla náhodná volba na business řadu&nbsp;[Samsung 750 EVO](http://www.samsung.com/us/business/computing/solid-state-drives/MZ-750250BW) o kapacitě 250GB. Ale vyzkoušen mám i [Crucual BX200 240GB](http://www.crucial.com/usa/en/ct240bx200ssd1), taktéž funkční.

<figure id="attachment_2317" aria-describedby="caption-attachment-2317" style="width: 402px" class="wp-caption aligncenter"><img decoding="async" loading="lazy" class="size-full wp-image-2317" src="https://www.maxxx.cz/wp-content/uploads/2016/09/SSDbech.png" alt="Test rychlosti EVO 750" width="402" height="367"><figcaption id="caption-attachment-2317" class="wp-caption-text">Test rychlosti EVO 750</figcaption></figure>

[/tab]  
[tab title=“RAM“]Dellem doporučované maximum je 2 x 4GB moduly, ale na internetu jsem se dočetl, že není problém osadit i dva 8GB moduly. Mnou vyzkoušené, kompatibilní modely jsou.

- [Hynix 4GB DDR3 –&nbsp;HMT351S6CFR8C](https://www.skhynix.com/eolproducts.view.do?pronm=DDR3+SDRAM&srnm=HMT351S6CFR8C&rk=20&rc=module)
- Samsung 4GB DDR3 –&nbsp;M471B5273DH0-CH9
- [Crucial 4GB DDR3L –&nbsp;CT51264BF160B  
](http://www.crucial.com/usa/en/ct51264bf160b)
- Samsung 2GB DDR3 – M471B5773DH0-CH9
- [Crucial 2GB DDR3L –&nbsp;CT25664BF160B](http://www.crucial.com/usa/en/ct25664bf160b)

Fungovat by ale měla většina běžně dostupných modulů SO-DIMM DDR3. A měli by běžet v Dual-Channel módu.

[/tab]  
[tab title=“WiFi“]Výměna [Broadcom DW 1501](http://www.ebay.com.my/itm/Dell-K5Y6D-WLAN-Mini-PCIexpress-Card-Broadcom-DW-1501-WiFi-802-11b-g-n-0K5Y6D-/261977378089?hash=item3cff118d29)&nbsp;za [Intel Centrino Advanced N 6205](http://www.intel.com/content/www/us/en/wireless-products/centrino-advanced-n-6205.html)[/tab]  
[tab title=“Tab number 4″]Tab 4 Content Goes Here.[/tab]  
[/tabs]

<!--kg-card-end: html-->