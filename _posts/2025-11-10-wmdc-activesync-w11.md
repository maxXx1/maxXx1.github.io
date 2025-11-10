---
title: "Windows 11 - ActiveSync a Windows Mobile Device Center"
date: "2025-11-10"
tags: 
  - "Windows-10"
  - "Windows-11"
category: "Windows"
image: 
  path: "/img/2025-11-10-wmdc-activesync-w11/Windows_Mobile_6.0.png"
  alt: "Windows Mobile"
---

U Windows 10 a Windows 11 již v systému úplně chybí centrum synchronizace pro mobilní zařízení. Resp. v Ovládacích panelech se **Centrum Synchronizace** nachází, ale nově připojené zařízení s Windows Mobile se hlásí jako `Generic RNDIS`, tedy chybí ovladač. 

## WMDC ve Windows 11 nebo Windows 10

Tým [JuniperSystems](https://junipersys.com/index.php/support/knowledge-base/support-knowledge-base-topics/desktop-connection-activesync-or-windows-mobile-device-center/wmdc-in-windows-10) se postaral o opravu původního WMDC, u kterého Microsoft ukončil podporu někdy kolem roku 2008.


# Postup instalace

> Ovaladač zeřízení `Generic RNDIS` je již součástí této instalace.
{: .prompt-info }

1. Stáhnout a nainstalovat 64-bit [drvupdate-amd64.exe](https://junipersys.com/data/support/drvupdate-amd64.exe) nebo 32-bit [drvupdate-x86.exe](https://junipersys.com/data/support/drvupdate-x86.exe).
2. Stáhnout a nainstalovat opravný path [WMDC-fixes-for-Win10.msi](https://junipersys.com/data/support/WMDC-fixes-for-Win10.msi) od Juniper Systems.
3. Restartovat počítač.
4. Spustit WMDC.
5. Připojte vaše zařízení pomocí kompatibilního kabelu.

![wmdc](/img/2025-11-10-wmdc-activesync-w11/windows_mobile.png)

## Požadavky

Možná bude třeba ručně povolit a nainstalovat starší verze .NET

![dotNET](/img/2025-11-10-wmdc-activesync-w11/dotNET.png)

## Připojení 

Pokud nechcete telefon znovu nastavovat, tak zvolte možnost "bez nastavení". Já zvolil možnost připojení pomocí USB, nemám ponětí jestli možnosti pomocí Bluetooth nebo IR fungují.

![wdmc-connect](/img/2025-11-10-wmdc-activesync-w11/centrum-zarizeni.jpg)

V této fázi se vám již bude: 
- zařízení zobrazovat v `Ovládací panely\Všechny položky Ovládacích panelů\Centrum synchronizace`
- uložiště v `Tento počítač`
- na jeden klik půjde skrze ActiveSync přtáhnout veškerý zvolený obsah z telefonu/PDA/NDA

## Řešení problémů

Někdy se stává, že služba synchronizace se prostě nespustí, postup na opravu tohoto problému je jednoduchý.

1. Klikněte pravým tlačítkem myši na tlačítko Start, poté klepněte na `Správa počítače`, potom na `Služby a aplikace` a následně na `Služby`.
2. Najděte službu `Připojení zařízení se systémem Windows Mobile 2003`.
3. Klepněte na tuto službu pravým tlačítkem myši a změňte nastavení na „spuštěno“, poté přejděte na záložku „přihlášení“ a zaškrtněte volbu „použít místní účet“ a okénko „povolit využití plochy“.
4. Restartujte počítač.

# Videonávod

{% include embed/youtube.html id='BQG5plsVKkc' %}

**Otestováno na Windows 11 build 24H2**
