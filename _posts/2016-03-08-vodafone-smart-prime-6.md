---
title: "Vodafone Smart Prime 6 - Unbrick ROOT TWRP"
date: "2016-03-08"
categories: 
  - "Android"
tags: 
  - "Vodafone"
image: 
  path: "/img/2016-03-08-vodafone-smart-prime-6/prime6.jpg"
  alt: "Vodafone Smart Prime 6"
---

Tento telefon sice nemá téměř žádné potencionálně nežádoucí, předinstalované aplikace, ale mnoho lidí se (ať už z jakýchkoliv důvodů) zajímá o postup k získání root oprávnění na tomto zařízení.

Problém je v tom, že po rootu odpadá možnost přijímat OTA aktualizace systému, protože telefon po nich již nenabíhá. Takže v případě, že chcete pouze root, tak se ujistěte, že nebudete dále aktualizovat, pokud nahrajete alternativní zavaděč budete moci dále instalovat skrze něj nejenom aktuální verze, ale i alternativní ROMky.

Kompletní flash oficiálního firmware, např. kvůli zrušení oprávnění root lze provést přes flashovací nástroj sugar a také jsem připojil návod na odblokování telefonu, pokud jste si jej náhodou už znefukčnili.

Pročtěte nejprve návod celý až do konce, aby se nestalo, že se v některém z kroků unáhlíte.

Tyto postupy byly testovány na několika verzích Firmware a posledním dostupném update operačního systému Android z Windows 7 i 10 (64bit).

## Příprava a Root

1. **Povolte "Možnosti pro vývojáře"** Nastavení - Informace o telefonu - _7x klikněte na ikonu_ "číslo sestavení" a poté se objeví "Možnosti pro vývojáře" dole v menu Nastavení.
2. **Povolte v nastavení "Ladění přes USB"** Nastavení - Možnosti pro vývojáře - Ladění přes USB
3. Povolte instalaci aplikací z **neznámých zdrojů** Nastavení - Zabezpečení - Neznámé zdroje aplikací
4. Nyní **vypněte telefon**
5. **Nabootujte do recovery** Stisk a podržet tlačítko power + volume up
6. **Vyberte jazyk** (Angličtina)
7. Poté "**Write Protect Switch**"
8. A **"Set write protect off"** (čímž vypnete ochranu proti přepsání)
9. Zobrazí se zpráva _"write protect is off after reboot"_
10. Nakonec zvolte **"cancel"** a **"reboot system now"**
11. Připojte se na WIFI a nainstalujte aplikaci **[KingRoot](https://kingroot.net/?myLocale=en_US)** (pro Android)
12.  V aplikaci klikněte na [modré tlačítko](https://kingroot.net/tutorials) a počkejte dokud nebude progress bar na 100%.
    - Pokud se telefon zasekne, tak podržte tlačítko power dokud se telefon nerestuje (nevypne) a postup opakujte.
13. Hotovo! Nyní můžete ověřit, jestli je vaše zařízení rootnuto pomocí [root check tool](https://play.google.com/store/apps/details?id=com.rootcheck.tool).

## Přehození z KingRoot na SuperSU

1. Stáhněte si [script](https://mega.nz/#!q04XWa4A!kNB_DZsqTJjbmEiRE_f9axypQBDrtcQ16UKi8TToND8).
2. **Rozbalte a nainstalujte** do mobilu
3. Nyní v nabídce původního KingRootu zvolte "**Full unroot**"
4. Vypněte telefon
5. Nabootoujte do recovery (**Volume UP + Power**)
6. V recovery vypněte "**WRITE PROTECT SWITCH**" a restartujte telefon
7. Nyní **zapněte KingRoot**, který jste nainstalovali z archívu a udělejte root
8. Restartujte telefon
9. Nyní spusťte aplikaci **SuperSume PRO** a klikněte na **modré tlačítko**
10. **Potvrďte přístup k root** od KingRootu a posléze již pro SuperSU
11. SuperSU by se měl nyní automaticky spustit s požadavkem, že **SU binary** potřebuje aktualizovat.
12. Zvolte **UPDATE** a možnost **NORMAL**
13. Nyní by po restartu telefonu měl být místo KingRootu nově SuperSU

> Pokud budete provádět update firmware (Androidu) na vyšší verzi, tak před tím musíte telefon unrootnout, znovu povolit "write protect" a přehrát soubor build.prop (nemodifikovanou verzí)! Jinak hrozí, že vám po update telefon naběhne pouze do fastbootu.
{: .prompt-danger }

## Instalace TWRP (alternativní recovery)

1. Stáhněte [TWRP 3.0.0-0](https://mega.nz/#!XpJwRSwL!47Z72snWrWy88IE6BkVjCabQn4596cvaK6QzN431yLU) a skrze USB ho nahrajte do **vnitřního úložiště**
2. Stáhněte a **nainstalujte** aplikaci [Flashify](https://play.google.com/store/apps/details?id=com.cgollner.flashify)
3. Spusťte Flashify a **povolte ROOT** přístup
4. Klikněte na "**Recovery image**" a potom "**Choose a file**"
5. Vyberte **.IMG** soubor TWRP 3.0.0-0
6. Klikněte na "**Yup!**" a počkejte, než se recovery flashne
7. Po dokončení zvolte "**reboot**"
8. Mobil se resetuje přímo do **TWRP recovery**

> V TWRP můžete nahrávat custom ROMs, resetovat telefon do továrního nastavení či celý smazat, ale hlavně provést zálohu vaší stávající ROM pro případné pozdější obnovení!
{: .prompt-info }

## Xposed Framework

- V TWRP lze jednoduše flashnout i **aktuální** [Xposed Framework](https://forum.xda-developers.com/showthread.php?t=3034811)
- Následně pak stačí nainstalovat [Installer](https://mega.nz/#!G85CEbZa!u_A-qutEaw7Sdz6jIKUS1pa_OH-s_bJwlnc3To5skhI) **přímo v androidu**

## Unbrick po OTA update

1. Stáhněte [archív s nástroji](https://mega.nz/#!D9ZFiRTL!hB9OfqHX0cde4WgTzDlyg-6kO_HFfeonPUV_mEIrFBM) a firmwarem zde
2. **Rozbalte archív** např. do `C:\Program Files (x86)\SUGAR QCT_SP\`{: .filepath}
3. **Nainstalujte ovaladač** (jako správce) z `C:\Program Files (x86)\SUGAR QCT_SP\usb_driver\installdriver\DriverInstaller.exe`{: .filepath}
4. Restartujte telefon do recovery (**vol up + power button**)

> Pokud se nedaří dostat telefon do diagnostického režimu, tak zkuste "download mode" - `volume up` + `volume down` + `power button` a následně `volume up`
{: .prompt-tip }

5. Nyní dejte **power down** z menu (kompletni vypnuti telefonu) a **zapojte USB kabel**
6. Nyní by se měl telefon detekovat v OS takto: 
![obrayovka](/img/2016-03-08-vodafone-smart-prime-6/Snimek_obrazovky.png)
7. **Spusťte sugar** (jako správce) `C:\Program Files (x86)\SUGAR QCT_SP\tool\SUGAR QCT_SP.exe`{: .filepath}
8. Odklikněte "**press OK**" přihlášení v sugaru (Vyhodí chybu, že nelze připojit, ale program jako takový naběhne)
9. Nyní pokud v programu vidíte váš telefon, tak **vyberte model "VF-895N"**
10.  Klikněte na **upgrade** a potvrďte flash Pokud program detekuje root, tak neklikejte na "**get status**", protože by vám to telefon přepnulo zpět do normálního režimu (a museli by jste znovu do recovery).
11. Pokud je vše v pořádku, tak by se měl automaticky spustit flash, který trvá cca. 8 - 10 minut, takže **buďte trpěliví**.
12. Hotovo! Můžete utřít pot z čela.

Zdroj: [AndroidForum](https://androidforum.cz/), [XDA Fórum](https://www.xda-developers.com/)
