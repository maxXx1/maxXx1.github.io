---
title: "Call of Duty 2 bez podpory PunkBusteru"
date: "2013-11-01"
tags: 
  - "COD2"
category: Hry
image: 
  path: /img/2013-10-20-call-of-duty-2-na-windows-8-1/pb.jpeg
  alt: PunkBuster
---

Byla zrušena podpora PunkBuster pro hry Call of Duty, Call of Duty: United Offeinsive a Call of Duty 2. Tato **anti-cheat ochrana** byla do 8 let starého Call of Duty 2 implementována v rámci opravného patche verze 1.3 a podporovala hru až do března tohoto roku. Na herní servery zrušení podpory do června nemělo po funkční stránce žádný vliv, v polovině června byl však vypnut i master server a herní servery tedy od června nelze provozovat s podporou PunkBusteru.

Systém PunkBuster zajišťoval nejenom anti-cheat ochranu a správu blacklistů, ale také ověřoval unikátní ID hráče, tzv. GUID který byl nejenom ověřením identity hráče, ale také kontrolou jeho legální kopie hry. Proslýchá se, že společnost provozující tuto službu ji již od roku 2009 nijak zásadně nevylepšila pro hru Call of Duty 2 a jeho předcházející dva díly. Avšak ukončení podpory je velkým problémem např. pro jeden z největších portálů [clanbase.com](https://clanbase.ggl.com/news.php) pořádající stále jako jeden z mála online ligové zápasy. _Na konkurenčním [ESL.eu](https://www.esl.eu/eu/cod2/news/213387/) byl poslední zápas odehrán 23.1.2013 a poté byli všechny žebříčky uzavřeny._

Lidé po celém světě se tedy nyní mohou na neošetřených serverech setkávat problémy jejichž **řešením je pouze vypnutí ochrany** v menu hry. Problémy byly ve většině případů způsobeny chybějícím GUIDem, který vypisoval u všech hráčů připojených k serveru hodnotu 0. Hra proto vyhodnotila jejich jejich online CD klíče jako duplicitní. V červnu tohoto roku kontaktovalo vedení COD2 sekce portálu [clanbase.com](https://clanbase.com/) vydavatele hry společnost [Activision](https://www.activision.com/), aby sjednalo nápravu. Jak to dopadlo ale nevím... Řešením problému s kickováním (vyhazováním) hráčů pro poskytovatele herních serverů bylo vypnutí `pbbans` a nastavení rcon příkazu 
```console
pb_sv_guiderelax 7
``` 
Avšak již nevím jak dalekosáhlé důsledky toto **komunitní řešení** mělo. Pravdou však zůstává, že hra se na oficiálních [stránkách podpory](https://www.evenbalance.com/index.php?page=support.php) PunkBusteru již neobjevila ~~a ligové zápasy na [clanbase.com](https://clanbase.com/) se i nadále hrají.~~
