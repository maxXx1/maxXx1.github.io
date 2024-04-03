---
layout: post
title: Výpadek Google v Česku a na Slovensku
date: '2016-11-23 16:16:40'
tags:
- dns
- google
- vypadek
- hash-wordpress
- hash-import-2023-08-28-13-25
---

> _„Komplikace, které včera postihly některé naše služby na území České a Slovenské republiky, trvaly přibližně dvě hodiny, zhruba od 19:30. Kolem čtvrt na deset naši inženýři problémy, které vznikly v důsledku údržby části sítě, úspěšně odstranili a naše služby jsou opět plně funkční. Omlouváme se všem za vzniklé potíže.“_
> 
> <cite>#<a rel="noreferrer noopener" href="http://googlepresscz.blogspot.cz/2016/11/sluzby-google-jsou-opet-plne-funkcni.html" target="_blank">zdroj</a></cite>

Na Darknetu v privátním darkroomu se píše o tom, že **útok** byl veden na celkem 3 bezpečnostní zero-day chyby v síťových prvcích CISCO, využití ARP cache zranitelnosti sítě Level3 na hardwarových prvcích staršího data. Severovýchod USA, backbone na Frankfurt, bývalá infrastruktura KPNQwest. Nejvíce výpadek postihl ČR a Slovensko, v USA potom Maryland a New York. Společným jmenovatelem jsou starší CISCO směrovače původního KPNQwest. A těch je v ČR a na SK požehnaně. Nejvíce to odnesly DNS brány Google, které jedou na L3.

Technický ředitel národního propojovacího uzlu [NIX.CZ](https://www.nix.cz/cs) Adam Golecký řekl, že hackerský útok je velmi nepravděpodobný. K tomuto názoru se přikláním i já. Už jen proto, že se k danému útoku přihlásilo hned několik hackerských skupin v čele s [#phantomsquad](https://twitter.com/PhantomNations), kteří své vyjádření pod náporem výsměchu uživatelů smazali (tak jak to mají ve zvyku). Klasickým DDOS útokem by mělo být nemožné zatížit tak velké servery až na úroveň kolapsu.

> _„S potěšením potvrzujeme, že komplikace byly vyřešeny. Příčina byla technického rázu, její detaily nyní prošetřujeme.“_
> 
> <cite>#<a rel="noreferrer noopener" href="http://googlepresscz.blogspot.cz/2016/11/vyjadreni-google-cr-ke-komplikacim-s.html" target="_blank">zdroj</a></cite>

Web pěkně zdegeneroval a stal se docela silně závislým na jednom hráči. Je to smutné. Naprosto vzdálené původním myšlenkám svobodné sítě. 🙁

<figure class="wp-block-embed is-type-rich is-provider-twitter wp-block-embed-twitter"><div class="wp-block-embed__wrapper">
<blockquote class="twitter-tweet" data-width="550">
<p lang="cs" dir="ltr">Podle naseho odhadu vypadku Google v CR zmizelo z CZ internetu cca 500 – 600 Gbps trafficu, tj. obsahu, ktery nyni k uzivatelum neproudi.</p>— Zdenek Cendra (@zdendac) <a href="https://twitter.com/zdendac/status/801145416590983173?ref_src=twsrc%5Etfw">November 22, 2016</a>
</blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</div></figure>

Nefunkční captcha od Google &nbsp;znemožnila odesílání formulářů na webech české státní správy&nbsp;a přístup k údajům z EET.

V důsledku výpadku nefungovala ani služba [@cloudflare](https://twitter.com/Cloudflare), která tím vyblokovala přístup k hromadě důležitých webů, které využívají jejích služeb právě kvůli ochraně proti takovýmto útokům.

Velmi pomalu se načítali i ostatní, méně důležité weby. Hlavně proto, že využívají [Google fonty](https://fonts.google.com/) či načítají hromadu informací o uživatelích do&nbsp;[Google Analytics](https://www.google.com/analytics/).  
Děje se tak proto, že stránka se bude snažit natáhnout jejich JavaScripty (fonty, apod.), a do timeoutu pokusu o jejich načtení se nemusí celá správně načíst a indikovat kódu, že je připravena.  
Tento problém by vůbec nenastal, kdyby dané weby tento vzdálený obsah cachovali, ale tím by přišli o určitou část sběru informací o uživatelích.

Krásně se projevilo také to, jak někteří naši ISP kradou DNS dotazy tím, že mají&nbsp;nastavené přesměrování všeho na portu 53 z vnitřní sítě na Google DNS, což se ukázalo při výpadku DNS resolveru. Absolutně nechápu jak může komerční firma použít veřejné DNS servery – šmírování je přednější než svoboda uživatelů.

I ten kdo si uměl sjednat nápravu volbou odlišného DNS byl bez šance, protože resolver ISP dotazy forwardoval právě na Google.

<figure class="wp-block-embed is-type-rich is-provider-twitter wp-block-embed-twitter"><div class="wp-block-embed__wrapper">
<blockquote class="twitter-tweet" data-width="550">
<p lang="en" dir="ltr">No, that's not a mushroom cloud. That's the area where <a href="https://twitter.com/Google?ref_src=twsrc%5Etfw">@google</a> services are currently <a href="https://twitter.com/hashtag/offline?src=hash&amp;ref_src=twsrc%5Etfw">#offline</a> &amp; unavailable. <a href="https://twitter.com/hashtag/GoogleDown?src=hash&amp;ref_src=twsrc%5Etfw">#GoogleDown</a> <a href="https://twitter.com/hashtag/LifeWithoutGoogle?src=hash&amp;ref_src=twsrc%5Etfw">#LifeWithoutGoogle</a> <a href="https://t.co/vKg2A7tAAq">pic.twitter.com/vKg2A7tAAq</a></p>— Lukas Jack Jaro (@ __SubZero__ ) <a href="https://twitter.com/ __SubZero__ /status/801143685471752192?ref_src=twsrc%5Etfw">November 22, 2016</a>
</blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</div></figure>

Protože se výpadek týkal **prý** výhradně evropského regionu, pomoci mohlo třeba přemostění spojení skrze VPN, ale tu nám v rámci plánované cenzury internetu (kvůli [zákonu o hazardu](http://www.lidovky.cz/snemovna-schvalila-novy-zakon-o-hazardu-odpurci-mluvi-o-cenzure-internetu-1u5-/zpravy-domov.aspx?c=A160413_114344_ln_domov_mct) z dílny ministerstva financí) také brzy zakážou.

Uživatelům tedy nezbylo nic jiného než zkusit si „vyseznamovat“ co se vlastně stalo. Seznam ale tak velký a hlavně nečekaný nárust popularity jednoduše neustál.

<figure class="wp-block-embed is-type-rich is-provider-twitter wp-block-embed-twitter"><div class="wp-block-embed__wrapper">
<blockquote class="twitter-tweet" data-width="550">
<p lang="pl" dir="ltr">A je to… <a href="https://twitter.com/hashtag/GoogleDown?src=hash&amp;ref_src=twsrc%5Etfw">#GoogleDown</a> <a href="https://twitter.com/hashtag/SeznamDown?src=hash&amp;ref_src=twsrc%5Etfw">#SeznamDown</a> <a href="https://t.co/Cjmz5jf0wq">pic.twitter.com/Cjmz5jf0wq</a></p>— Michal Ischia (@ischiam) <a href="https://twitter.com/ischiam/status/801151565021253632?ref_src=twsrc%5Etfw">November 22, 2016</a>
</blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</div></figure>

Ten kdo měl napevno nastavené Google DNS nefungoval vůbec, ten kdo měl DNS od dobrého ISP fungoval bez google služeb, ten kdo měl velkého poskytovatele internetu (T-Mobile, O2 i UPC opravili chybu v routingu ručně) po chvíli také fungoval, a ten kdo navíc jako primární email a vyhledávač používá něco jiného než Seznam a Google (např. [duckduckgo.com](https://duckduckgo.com/)) + má prohlížeč vybaven blokovačem reklam (aby odfiltroval Google [AdSense](https://www.google.com/adsense/start/#?modal_active=none)) problém ani nezaznamenal.

Je pravda, že k YouTube jste se nedostali až do cca desáté hodiny, telefony s androidem hlásily problém s Google Play Services (vykřičník u wifi signálu) a můj [Chromecast](https://www.google.com/intl/en_us/chromecast/) byl úplně mrtvý… to ale nejsou služby životně důležité. 🙂

<!--kg-card-end: html-->