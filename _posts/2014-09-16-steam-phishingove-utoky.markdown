---
layout: post
title: Steam phishingové útoky
date: '2014-09-16 11:30:39'
tags:
- dota2
- scam
- steam
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Dlouho jsem nic nenapsal, což samozřejmě hodlám napravit. Dnes bohužel s velmi smutnou zprávou. Před několika týdny proběhly komunitou okolo hry Counter Strike: Global Offensive zprávy o četných krádežích účtů na Steamu. Jako vždy jsem si myslel, že se jedná pouze o hrubé porušení zásad bezpečnosti… měl jsem pravdu.

<!--more-->

Nepochybně lze tento útok na uživatele provést několika různými způsoby. Jako např. zavirovanou přílohou emailu, či keylogerem (program zaznamenávající to co na klávesnici píšete). Před takovou formou útoku by měl být na pozoru jak uživatel, tak jeho anti-virové zabezpečení. V čem vám však anti-virus za žádných okolností nepomůže je tzv. Phishing.

Jedná se o velmi jednoduché sociální inženýrství. Zkontaktuje Vás osoba, která vás pod příslibem zisku či jiné věci naláká na svůj web, kde vás donutí odeslat vaše přihlašovací údaje. Např. pomocí přihlášení. Webová prezentace patří danému útočníkovi, který uloží jméno a heslo v nešifrované podobě. Tudíž mu jednoduše řečeno vaše přihlašovací údaje dobrovolně předáte.

V tomto vám nepomůže ani 10 antivirových programů, protože varování steamu po prokliknutí odkazu z chatu je již tak banální, že jej každý ignoruje. Stránka se na pohled tváří jako přesná kopie některé oficiální (věrohodné stránky) a vy se na ní prostě přihlásíte, tak jako by jste to udělali na normální stránce. Z pohledu antivirového zabezpečení se neděje nic neobvyklého.

Dnes nad ránem jsem si sám vyzkoušel jak jednoduché to je. Zkontaktoval mě uživatel&nbsp;[Yggron](http://steamcommunity.com/profiles/76561198154733056 "Yggron")&nbsp;(vypadá to. že má [více variant](http://steamcommunity.com/search/?text=Yggron "more")), který mě velmi slušně, anglicky požádal jestli bych mu nezanechal komentář „+rep“ na jeho profilu na&nbsp;[Dota 2 Lounge](http://dota2lounge.com/ "Dota2")&nbsp;a přislíbil, že mi za tento komentář pošle klíč v hodnotě 1.79 Euro do hry CSGO. Toto není neobvyklé! Uživatelé rádi spamují a nahánějí kladné hodnocení. Co víc já sám hraji CSGO, což je na mém profilu zřetelně viditelné a o Dotu 2 se nezajímám, proto ani nevím jak (a jestli vůbec existují) vypadají stránky Dota2lounge. Hmm klíč by se hodil že…?

Jenže odkaz na jeho profil nevedl na stránky&nbsp;[dota2lounge.com](http://dota2lounge.com/ "pravé")&nbsp;nýbrž na stánky&nbsp;[dota2iounge.com](http://dota2iounge.com/ "falešné")&nbsp;(všimněte si zejména záměny písmena l za i v adrese), tedy podvržené, které vedou kam jinam než do [ruska](http://whois.domaintools.com/dota2iounge.com "doména"). Stránky stejně jako&nbsp;[jeho profil](http://dota2iounge.com/trade=79487367/ "profil")&nbsp;vypadal naprosto identicky, jako v případě originálních stránek, odkazy vedli zpět na steam či na pravé stránky dota2lounge. Útočník cílil pouze na napsání daného komentáře, protože podmínkou komentování je login. Ten již ale nevede na stránky steamu a login se pouze uloží na serveru útočníka a stránka vás dále přesměruje na třeba i pravé stránky s výzvou o znovu zadání jména a hesla po kterém se již korektně přihlásíte. Toto však nemohu potvrdit – tak daleko jsem se nedostal. Ale v této chvíli už je zle, protože vám se může vše jevit tak jak má, avšak útočník již vaše přihlašovací údaje získal.

Nezachrání Vás ani ověřovací kód zaslaný na email, protože ten má platnost omezenou časově. Aby jste měli čas ho použít. A expiruje ve chvíli korektního přihlášení. To se však nestane protože se nepřihlašujete ke službám steamu, ale na stránku útočníka. Tudíž pokud bude útočník dostatečně rychlý (což bude), tak se bez problémů přihlásí.

Pokud (a teď se zamyslete) máte stejné heslo ke steamu jako k vašemu emailu, který útočník zjistí hned po přihlášení. Tak se bez problému přihlásí i na váš email. Dostane tím kontrolu nad ověřovacími kódy. Pohodlně si heslo změní. Počká než vyprší 7mi denní ochranná lhůta a steam účet bez větších problémů vykrade. Např. tak, že za peníze ve steam peněžence nakoupí, itemy protáhne přes několik účtů a daný účet třeba úplně zruší, aby za sebou zametl stopy. (to je popsáno na Redditu jako jeden z mnoha případů napadení).

Takže jsem doufám velmi jednoduše nastínil jak je to jednoduché. Jedná se o klasické sociální inženýrství, žádné hackování! Útočník vás slušně požádá, vy mu „skočíte na špek“. Zacílí na něco v čem si úplně nejste jisti, jako v mém případě – hraji CSGO, on po mě chtěl něco ohledně Doty 2. A výsledek je ten, že i kdyby vám podpora steamu účet vrátila, tak peníze ani předměty už neuvidíte. Peníze budou utraceny a předměty přeprodány na některé z tržnic provozující třetí stranou např. již výše zmíněné&nbsp;[csgolounge.com](http://csgolounge.com/ "csgo").

Proto prosím buďte opatrní (ať nedopadnete jako [mnoho ostatních](http://steamcommunity.com/discussions/forum/1/616187839195982368/ "připad")), dbejte základních zásad bezpečnosti, nastavujte různá středně silná až silná hesla pro své služby a pořádně se dívejte kam je zadáváte. Kdyby jste objevilo více podobných podvodů, neváhejte zanechat vzkaz do komentářů a pomoci tak ostatním.

<!--kg-card-end: html-->