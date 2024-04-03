---
layout: post
title: AOE II HD má problémy s Win 8
date: '2013-12-31 13:55:00'
tags:
- age-of-empires
- steam
- windows
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Vánoční slevy jsou jistě časem, kdy mnozí z vás (stejně jako já) pokukují po slevách na Steamu, aby nakoupily na rok dopředu herní výbavu na dlouhé večery. Já koupil vysněné AOE II v HD verzi, abych tedy konečně mohl porovnat modifikaci a plnohodnotnou hru.

A hned problém! Začínám si myslet, že udržovat se svým počítačem krok s dobou v podobě koupě Windows 8.1 Pro bylo opravdu špatné rozhodnutí. Ale u nově zakoupené hry, která vyšla až po vydání Windows 8 a je navíc původem z dílny Redmondského giganta bych čekal špičkovou optimalizaci. Studio které si Microsoft zaplatil kvůli předělání hry si asi ukouslo větší sousto než je schopno pojmout. Protože díky komunitní slevě v rámci Steamu si hru za necelých 200 Kč pořídil snad každý fanoušek této herní série. Pokud tedy máte také problémy s hrou tak čtěte dále…

<!--more-->

Hned po nainstalování mě však zarazilo to, že hra má pouze něco málo přes 1,5 GB místo deklarovaných 1724 MB. I po „Ověření integrity mezipaměti hry“ zůstávala velikost stejná.

Po spuštění hra zobrazila Launcher, který zobrazoval feed novinek, avšak pro jejich zobrazení používá java script, takže první co mi launcher nabídl bylo chybové hlášení o scriptu a dotaz, jestli ho má či nemá zobrazovat. To by až tak moc nevadilo, pokud by se však po kliknutí na tlačítko „Play“ něco dělo.  
Hra se však bez dalších diskuzí sama ukončila.

Po několika restartech počítače resp. Steamu jsem vyvolal kýženou aktualizaci, která srovnala velikost hry na 1724 MB, které má mít. Na problému to ovšem nic neřešilo. Launcher fungoval, hra však nikoliv.  
Na toto téma jsem našel mnoho návodů na internetu, které doporučovali různě upravovat komaptibilitu či nastavovat parametry při spuštění hry. Ale vyzkoušením jsem docílil tak maximálně toho, že mi začal havarovat i Steam jako takový.

Jediná věc, která mě napadla selským rozumem a za **fungovala na první pokus** je:  
1. Klik na hru druhým tlačítkem, zvolit „Vlastnosti“  
2. Záložka „Místní soubory“ – „procházet místní soubory“  
3. Smazat (či přejmenovat/přesunout mimo složku s hrou) soubor „Launcher.exe“  
4. Soubor „AoK HD.exe“ přejmenovat na „Launcher.exe“

[![]( __GHOST_URL__ /wp-content/uploads/2013/12/aoe-1024x643.png)]( __GHOST_URL__ /wp-content/uploads/2013/12/aoe.png)

Po naskočení hry se nelekejte obludné notifikace Steam In-game. Je to způsobeno tím, že intro není ve vysokém rozlišení, ale v rozlišení původní hry. Na rozdíl od modifikace The Forgotten Empire (pro původní hru) je ale menu již v širokoúhlém rozlišení, takže pokud přeskočíte intro, tak si této drobné vady na kráse ani nevšimnete.Poté by se, po kliknutí na tlačítko hrát v programu Steam měla spustit hra jako taková, nikoliv její Launcher (který je nedoladěný a vlastně k ničemu). Pokud by vám chyběl odběr novinek z launcheru, tak použijte [officiální twitter](https://twitter.com/AgeOfEmpires) hry.

Co mi ještě trošičku chybí k dokonalosti je čeština, protože hraní s ní by bylo opravdu velmi pohodlné. Ale ta zatím není a nic nenasvědčuje tomu, že by se na ní naši schopní překladatelé chystali. Ale o tom jsem již psal v závěru [původního článku](http://maxxxcomp.blogspot.cz/2013/11/age-of-empires-ii-forgotten-empires.html).

<!--kg-card-end: html-->