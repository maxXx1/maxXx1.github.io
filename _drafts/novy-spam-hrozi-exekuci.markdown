---
layout: post
title: Nový spam hrozí exekucí
tags:
- hash-wordpress
- hash-import-2023-08-28-13-25
---

V dubnu nás zahltila první vlna zákeřného spamu, který vyzval k úhradě údajných dluhů. Tehdy byl email plný pravopisných chyb a údaje byli velmi zmatené, nová verze však přitvrdila! Je napsána téměř bez chyb a v příloze se opět skrývá virus!<!--more-->

Tyto emaily chodili do našich schránek vždy a nikdy tomu nebude jinak. Problém těch dnešních je v tom, že cílí velmi konkrétně. Jsou lokalizovány do češtiny, obsahují existující názvy bank, čísla účtů i jména osob. V minulých vlnách tohoto spamu se poodhalilo, že jména osob nejsou smyšlená, ale jedná se o nic netušící podnikatele, kterým díky uvedenému kontaktu v emailu stihlo zavolat i desítky vyděšených lidí během jednoho dne.

[![](http://192.168.20.2/wordpress/wp-content/uploads/2014/07/spamíík-1024x576.png)](http://192.168.20.2/wordpress/wp-content/uploads/2014/07/spamíík.png)

Zde si útočník také vypůjčil jména existujících exekučních firem, bank a čísla účtů. Nevím jestli výzva k úhradě vede na existující účet útočníka (zřejmě je to pouze zastírací manévr). Ale co vím určitě je to, že v příloze značené stylem „prikaz\*náhodně vygenerované znaky\*.ZIP se neskrývá faktura či další informace, ale&nbsp;[Win32/TrojanDownloader.Elenoocka](http://www.virusradar.com/en/Win32_TrojanDownloader.Elenoocka.A/description "Virus radar")&nbsp;(dle databáze ESETu). U přílohy se nejedná ani o archív nýbrž spustitelný soubor, který inicilizuje spuštění viru, který se zaměřuje na&nbsp;získávání přístupů do internetového bankovnictví a stahováním další havěti.

Pokud si myslíte, že vás před nechtěným převodem peněz na útočníkův účet ochrání zabezpečení internetového bankovnictví na bázi ověřovacích kódů zaslaných na Váš telefon, tak jste na omylu, protože tyto převody se realizují přes zahraniční platební brány, které toto ověření nevyžadují. A rozhodně se vyvarujte instalace jakýchkoliv jiných než oficiálních mobilních aplikací pro správu internetového bankovnictví.

Velmi známý je případ ženy z&nbsp;Kroměřížska, která nejenom, že otevřela emailovou přílohu, ale také nainstalovala fiktivní mobilní aplikaci. Ignorovala veškeré varovné znaky, jako je například to, že email přišel od společnosti která se nezabývá vymáháním dluhů ani to není banka. Nainstalovala aplikaci, která není od banky a vlastně se tak ani netváří. Tím dala útočníkovi nejenom přístup ke svému internetovému bankovnictví, ale také nástroj pro přesměrování potvrzovacích SMS, tím pádem plný přístup k účtu. Přišla o 400 tisíc korun!

## Co u takových emailů sledovat?

- V první řadě pravopisné chyby – žádná instituce by Vám neposlala email s pravopisnými chybami a strojový překlad lze také velmi často rozeznat na první pohled.
- Hned poté by jste se měli zaměřit na to odkud Vám email přišel. Většinou chodí z ukradených emailových adres. V mém případě velmi nešťastně od firmy zabývající se tvorbou keramiky.
- Za žádných okolností neotevírat spustitelnou ani jakoukoliv jinou podezřelou přílohu.
- Pokud jsou v emailu kontakty, tak dávejte pozor na předčíslí 900 xxx xxx, jedná se o linky se zvýšenou sazbou za minutu hovoru.

## Co dělat když už jsem email otevřel?

- Text takového emailu ještě nikdy nikomu neublížil, takže pokud jste neotevřeli přílohu, tak email s klidným svědomím můžete smazat. (např. klávesovou zkratkou SHIFT + DELete)
- Pokud jste náhodou otevřeli již i přílohu, tak doporučuji provést anti-virový scan pomocí [ESET Online Scanner](http://www.eset.com/cz/domacnosti/produkty/online-scanner/ "ESET online"), ten na předchozí modifikace této nákazy reagoval jako první.

![avast](http://www.maxxx.cz/wp-content/uploads/2014/07/avast1.png)

Vždy je důležité pořádně číst a všímat si detailů! V této chvíli na tuto hrozbu reaguje už i Avast FREE anti-virus, který je ke stažení úplně zdarma.

&nbsp;

<!--kg-card-end: html-->