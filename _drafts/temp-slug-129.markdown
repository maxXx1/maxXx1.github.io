---
layout: post
title: Hass.io
tags:
- nezarazene
- hash-wordpress
- hash-import-2023-08-28-13-25
---

- Rassbery Pi 4
- Napájecí zdroj 5V 3A (microUDB) nesmíte jít níž než 2.5A
  - Běžné nabíječky mají tak 2.1A
- SDkarta 32GB a Aplikační třída 2

Stáhnout OS [https://www.home-assistant.io/hassio/installation/](https://www.home-assistant.io/hassio/installation/)

Stáhnout Flash program https://www.balena.io/etcher/

Připojíme dáme 🍺 a přes ip adresu dokončíme instalaci

Pokud podporuje router mDNS tak http://hassio:8123/ (Problem was that multicast packets wasn’t forwarded to the KVM Guest)

&nbsp;

Instalace addonů: Supervissor – Add-on Store:

- File editor&nbsp;(configurator) – http://192.168.20.93:8123/hassio/addon/core\_configurator/info
- Samba share – http://192.168.20.93:8123/hassio/addon/core\_samba/inf
- SSH (???)

&nbsp;

Zálohy – supervisor – snapshots

&nbsp;

&nbsp;

&nbsp;

<!--kg-card-end: html-->