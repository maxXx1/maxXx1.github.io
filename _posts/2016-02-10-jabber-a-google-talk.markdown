---
layout: post
title: Jabber a Google Talk
date: '2016-02-10 20:11:25'
tags:
- facebook
- gtalk
- hangouts
- jabber
- xmpp
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Dnes mě jeden můj známý upozornil na velmi zajímavou věc. V jeho kontakt listu visím pod dvěma různými adresami pro XMPP protokol. Jedna je správná, tedy mé Jabber ID (JID) a ta druhá byla pozůstatkem Google Talku, který jsem v minulosti s oblibou používal právě kvůli návaznosti na jiné služby skrze XMPP.

Google ukončil podporu GTalku někdy v únoru 2015 a stejně jako Facebook (messenger), který zakládá taktéž na XMPP, uzavřel svůj komunikační protokol pod službou [Hangouts](https://hangouts.google.com/). Jak je tedy možné, že se mi tento tento známý dopsal skrze Jabber na adresu @gmail.com?

Nynější stav je takový že:

1. **Nemůžete** psát pomocí Hangouts z telefonu (Android, iOS) nebo chatu v Gmailu či Inboxu s někým kdo je v&nbsp;XMPP síti. Tyto kontakty již v Hangouts ani neuvidíte.
2. Stále **můžete** přidat vaši&nbsp;@gmail.com&nbsp;adresu do XMPP klienta a používat.  
_Takže nějaká podpora XMPP v novém Hangouts z GTalk zůstala a funguje._
3. Stále **můžete** ve vašem XMPP klientu přidat kohokoliv s adresou @gmail.com a psát si s ním.
4. Dokonce stále **můžete** použít svoji @gmail.com adresu v XMPP klientu a komunikovat s jinými kontakty s adresou @gmail.com.
5. **Nemůžete** skrze XMPP klient uskutečnit hlasový ani video hovor do sítě Hangouts.

Situace by měla být stejná i pro Facebook, který taktéž zakládá na XMPP, ale protokol postupně uzavírá v rámci vlastního ekosystému. (V minulosti měl dokonce i svůj vlastní [klient pro Windows](http://www.maxxx.cz/2013/07/20/facebook-massenger-nefunguje-na-windows-xp/)).

**Funkční nastavení XMPP klienta**

    host: talk.google.com port: 5222 service: gmail.com security: enable TLS, disable SASL

**Facebook**

    host: chat.facebook.com port: 5222 service: chat.facebook.com security: disable TLS, enable SASL userid: nemůžete použít váš email. musíte mít na facebooku loginname a použít ten (facebook.com/loginname).

**Jabber.org**

    host: jabber.org port: 5222 service: jabber.org security: enable TLS, enable SASL

Co se týče **historie** komunikace, tak pokud si píšete z XMPP kilenta do Hangouts, tak se uloží na serveru a bude tedy v rámci Hangouts zpětně dohledatelná odkudkoliv. Synchronizace však chvíli trvá (vaše odpovědi nebudou v Hagouts vidět hned).

Pokud píšete z XMPP klienta (byť z @gmail.com) někomu kdo je v síti XMPP bude vaše konverzace uložená pouze na straně klienta. (Nebude v Hangouts dohledatelná).

Jabber lze stále používat na vlastní doméně v rámci Google Apps, tak zbývá jen doufat, že Google podporu XMPP úplně nezařízne i když v dnešní době klasický „standalone“ XMPP klient používá stále méně lidí a každý větší portál má svou&nbsp;„XMPP“-like IM službu…

Protože k tomu, aby se tak stalo stačí velmi málo. Například použití&nbsp;vlastního SASL mechanizmu pro OAuth autentizaci, tak jak to udělal Microsoft se svým&nbsp;Windows Live Messengerem po koupi Skypu v roce 2011.

<!--kg-card-end: html-->