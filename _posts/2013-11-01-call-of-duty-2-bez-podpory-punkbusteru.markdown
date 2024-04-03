---
layout: post
title: Call of Duty 2 bez podpory PunkBusteru
date: '2013-11-01 21:57:00'
tags:
- cod
- punkbuster
- windows
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Byla zrušena podpora PunkBuster pro hry Call of Duty, Call of Duty: United Offeinsive a Call of Duty 2. Tato **anti-cheat ochrana** byla do 8 let starého Call of Duty 2 implementována v rámci opravného patche verze 1.3 a podporovala hru až do března tohoto roku. Na herní servery zrušení podpory do června nemělo po funkční stránce žádný vliv, v polovině června byl však vypnut i master server a herní servery tedy od června nelze provozovat s podporou PunkBusteru.

<!--more-->

Systém PunkBuster zajišťoval nejenom anti-cheat ochranu a správu blacklistů, ale také ověřoval unikátní ID hráče, tzv. GUID který byl nejenom ověřením identity hráče, ale také kontrolou jeho legální kopie hry.  
Proslýchá se, že společnost provozující tuto službu ji již od roku 2009 nijak zásadně nevylepšila pro hru Call of Duty 2 a jeho předcházející dva díly. Avšak ukončení podpory je velkým problémem např. pro jeden z největších portálů&nbsp;[clanbase.com](http://clanbase.ggl.com/news.php)&nbsp;pořádající stále jako jeden z mála online ligové zápasy.  
_Na konkurenčním [ESL.eu](http://www.esl.eu/eu/cod2/news/213387/) byl poslední zápas odehrán 23.1.2013 a poté byli všechny žebříčky uzavřeny._

Lidé po celém světě se tedy nyní mohou na neošetřených serverech setkávat problémy jejichž **řešením je pouze vypnutí ochrany** v menu hry. Problémy byly ve většině případů způsobeny chybějícím GUIDem, který vypisoval u všech hráčů připojených k serveru hodnotu 0. Hra proto vyhodnotila jejich jejich online CD klíče jako duplicitní.  
V červnu tohoto roku kontaktovalo vedení COD2 sekce portálu [clanbase.com](http://clanbase.com/)&nbsp;vydavatele hry společnost&nbsp;[Activision](http://www.activision.com/), aby sjednalo nápravu. Jak to dopadlo ale nevím…  
Řešením problému s kickováním (vyhazováním) hráčů pro poskytovatele herních serverů bylo vypnutí _„pbbans“_ a nastavení rcon příkazu _„pb\_sv\_guiderelax 7“_.  
Avšak již nevím jak dalekosáhlé důsledky toto **komunitní řešení** mělo.  
Pravdou však zůstává, že hra se na oficiálních [stránkách podpory](http://www.evenbalance.com/index.php?page=support.php) PunkBusteru již neobjevila a ligové zápasy na [clanbase.com](http://clanbase.com/)&nbsp;se i nadále hrají.

![](http://2.bp.blogspot.com/-_1H9CtXYZCU/UnQOWGA0eZI/AAAAAAAAFco/K25RHDuoDD0/s320/punkbuster-y-u-kick-me-out.jpg)

<!--kg-card-end: html-->