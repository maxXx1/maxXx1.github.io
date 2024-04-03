---
layout: post
title: 'Counter Strike: GO chybí zaměřovač!'
tags:
- config
- steam
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Je pravda, že této hře by prospěl mód ala Call of Duty, tedy bez zaměřovače, ale co když se to náhodou opravdu stane? Nedávno se mi podařilo zapnout Counter Strike: Global Offensive s tím, že jsem ve hře neviděl zaměřovač ani popisy spoluhráčů. Ze začátku jsem si to vysvětloval jako mód serveru. Sice trochu úchylný, protože tak se přeci hrát nedá, ale možné to je. Poté co jsem si uvědomil, že ostatní střílejí o dost přesněji než já jsem začal pátrat.

<!--more-->

Ano, vy už možná víte. Chybějící zaměřovač je chyba ve hře. Je způsobena neúplným načtením souboru „config.cfg“, který má za úkol si pamatovat vaše nastavení hry. Resp. jeho část která udává nastavení zaměřovače, který jde směnit (typ) přebarvit, zvětšit i zmenšit. K tomu slouží tyto parametry.

> crosshair „1“  
> cl\_crosshairscale „1200“  
> cl\_crosshairalpha „255“  
> cl\_crosshairusealpha „0“  
> cl\_scalecrosshair „1“

Protože nepomohlo ani prosté restartování hry/steamu, tak jsem přistoupil k řešení nejdrastičtějšímu.

1. Klik na hru druhým tlačítkem – zvolit „Vlastnosti“
2. Záložka „Místní soubory“ a „Procházet místní soubory“
3. Najít soubor „config.cfg“ v umístění „…csgocfg“
4. A smazat ho!

Po spuštění hry se vytvoří nový a i když nastavení konfigurace hra zapomene, tak zaměřovač je zpět.

Tato chyba se bez zásahu do konfiguračního soboru (například laděním detailů a samotného zaměřovače) stává velmi zřídka, ale stává se. Pokud už jsme tedy u zaměřovačů a vy jste si právě smazali ten váš vyladěný (šlak aby mě trefil), tak si zpravte chuť na [redditu](http://www.reddit.com/r/GlobalOffensive/comments/1ugdm1/post_your_crosshair_configs_with_screenshots/), kde najdete nepřeberné množství různých nastavení zaměřovače. Nebo vyzkoušejte tento jednoduchý [konfigurátor](http://www.krisskarbo.com/csgocrosshair/#alpha=200/color=5/color_b=50/color_r=50/color_g=250/dot=0/gap=0/size=5/style=2/usealpha=1/thickness=0.5/outline=0/outline_draw=0). Pokud máte nějaké opravdu zajímavé nastavení zaměřovače, tak ho neváhejte zanechat zde v komentáři.

Děkuji! 🙂
<!--kg-card-end: html-->