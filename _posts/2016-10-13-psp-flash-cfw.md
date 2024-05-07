---
title: "PlayStation Portable - Flash CFW"
date: "2016-10-13"
category: "Hardware"
tags: 
  - "psp"
image: 
  path: "/img/2016-10-13-psp-flash-cfw/playstation-portable.jpg"
  alt: "Playstation Portable"
---

Obecně tyto věci odsuzuji, ale pokud máte doma stále funkční PlayStation Portable, na kterém pouze odešla mechanika, tak co dělat. Jediný způsob jak si na něm zahrát je skrze vnitřní paměť. Oprava mechaniky je ve většině případů nerentabilní. UMD disky nelze nahradit jinak. Tyto disky se ani nikdy prázdné neprodávali.

## Požadavky

- Nainstalovaný OFW 6.61
    - Pokud máte nižší verzi FW -  [stáhněte upgrade](https://www.playstation.com/en-us/support/system-updates/psp/)
    - Stažený EBOOT.PBP zkopírujete do PSP/GAME/UPDATE/, zajeďte do Game a spusťte aktualizaci
- Nabitá baterie alespoň na 78%
- [Y miniUSB](https://www.heureka.cz/?h%5Bfraze%5D=Kabel+Y+USB+2x+A+mini+B) kabel
- SD kartu s redukcí nebo přímo [Memory Stick Pro Duo](https://pametove-karty-ms-pro-duo.heureka.cz/)

> Verzi FW zjistíte skrze menu Settings -> System Settings -> System Information -> System Version
{: .prompt-tip }

## Postup

1. Připojte PSP k počítači skrze miniUSB
2. V konzoli - Settings - USB Connection potvrďte připojení k PC
3. Stáhněte archiv [661_PRO-C2_14-02-2015](https://1drv.ms/u/s!AmaMNBEz9Mw0gbw8_o8RnzzxNfT2CA)
4. Archiv rozbalte a složky `FastRecovery` a `PROUPDATE` zkopírujte do `PSP/GAME/`
5. V konzoli - Zajeďte do Game a PRO Update spusťte
6. V konzoli - Potvrďte instalaci  stiskem `X` 
![flash](/img/2016-10-13-psp-flash-cfw/IMG_20161013_151927.jpg) 
7. V konzoli - Po oznámení "Completed." potvrďte restart stiskem **X**
8. Po restartu konzole můžete správnost instalace ověřit v Settings - System Settings - System Information

**Fast Recovery** je prakticky to stejné jako ProUpdate s tím rozdílem, že následující start CFW (po restartu, vypnutí, vyndání baterie...) dokáže provést rychleji.

Pozn. Po flashnutí FW zmáčkněte **SELECT** a ve **VSH Menu** u řádku **UMD ISO MODE** nastavte **M33 driver** nebo **Inferno**
![flash2](/img/2016-10-13-psp-flash-cfw/IMG_20161013_152756.jpg)

## Instalace a spuštění her

- Hry musí být ve formátu **ISO/CSO**
- Musí být nakopírovaný do složky **ISO** (nutno vytvořit) v paměti zařízení
- hra by se vám pak měla objevit v menu PSP pod Game->Memory Stick 

Další užitečné věci ke stažení pro PSP naleznete na [QuickJump](https://dl.qj.net/psp.html).