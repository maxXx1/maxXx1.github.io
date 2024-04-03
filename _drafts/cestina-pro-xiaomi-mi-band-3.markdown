---
layout: post
title: Čeština pro Xiaomi Mi Band 3
tags:
- fw
- miband
- nezarazene
- xiaomi
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Dostal se mi do ruky, resp. na ruku Xiaomi Mi Band 3 – konkrétně základní verze bez NFC, který byl kupován z originální čínské distribuce skrze [GearBest](https://cz.gearbest.com/xiaomi-_gear/), tudíž sice za třetinovou cenu, ale kompletně v čínštině.  
Tyto náramky mají [několik různých HW revizí](https://vk.com/pages?oid=-137602336&p=%D0%92%D0%B8%D0%B4%D1%8B_Mi_Band_3) a určité z nich jsou určeny pouze pro konkrétní trhy. To způsobuje nepříjemnost, že i když čínskou revizi náramku spárujete s aplikací v angličtině nebo češtině, tak náramek si firmware v daném jazyce nestáhne / neaktualizuje. Právě naopak, pokud neoficiální cestou nainstalujete do náramku určeného pro asijský trh češtinu nebo angličtinu – ihned po aktualizaci aplikace / firmwaru náramku se čínský jazyk vrátí zpět. Proto je zapotřebí udělat několik opatření.

### Co budeme potřebovat

- Mobil s Androidem (návod pro iOS [zde](https://geekdoing.com/threads/czech-firmware-2-3-0-6.386/#post-9758))
- Vědět jestli vlastníte Mi Band s NFC či bez
- Vybrat si vhodnou verzi Resources – např. [dle videa](https://www.youtube.com/playlist?list=PL9XdbwYhkTugurq9B3v--TX2Xy1HKler4)
- Mít nabito alespoň na 30% (jak telefon, tak náramek)

### Instalace alternativní aplikace a párování

1. **Nainstalujte oficiální aplikaci** Mi Fit přímo z [Play Store](https://play.google.com/store/apps/details?id=com.xiaomi.hm.health&hl=cs) a náramek spárujte s vaším zařízením.
2. Nechte aby se aktualizovala jak aplikace tak čínský firmware na nejnovější verzi. (v mém případě 2.3.0.2)
3. Následně **zapněte viditelnost náramku** :
  1. Mi Fit aplikace
  2. Profil (vpravo dole)
  3. V sekci „Moje zařízení“ zvolte váš Mi Band 3
  4. Zvolte funkci „Viditelný“
  5. Zapněte „Zjistitelný režim“
4. Na stejné obrazovce dole následně zvolte „ **Zrušit párování** “ (velmi důležité pro předejití poškození náramku při nahrávání fw!)
<figure class="is-layout-flex wp-block-gallery-8 wp-block-gallery columns-2 is-cropped"><ul class="blocks-gallery-grid">
<li class="blocks-gallery-item"><figure><img decoding="async" loading="lazy" width="360" height="640" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/1.jpg" alt="" data-id="4301" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/1.jpg" data-link="https://maxxx.cz/?attachment_id=4301" class="wp-image-4301" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/1.jpg 360w, __GHOST_URL__ /content/images/wordpress/2020/09/1-169x300.jpg 169w" sizes="(max-width: 360px) 100vw, 360px"></figure></li>
<li class="blocks-gallery-item"><figure><img decoding="async" loading="lazy" width="360" height="640" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/2.jpg" alt="" data-id="4302" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/2.jpg" data-link="https://maxxx.cz/?attachment_id=4302" class="wp-image-4302" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/2.jpg 360w, __GHOST_URL__ /content/images/wordpress/2020/09/2-169x300.jpg 169w" sizes="(max-width: 360px) 100vw, 360px"></figure></li>
</ul></figure>
1. Nainstaluj aplikaci **Gadgetbridge** ([GooglePlay](https://play.google.com/store/apps/details?id=ee.aegrel.gadgetbridge&hl=cs) / [F-Droid](https://f-droid.org/packages/nodomain.freeyourgadget.gadgetbridge/) / [APK](https://geekdoing.com/forums/gadgetbridge.11/))
2. Spárujte náramek v aplikaci Gadgedbridge kliknutím na „ **+** „
3. Gadgetbridge by měl náramek najít, pokud jste provedli správně předchozí kroky
4. Nastavení Mi Band v této aplikaci můžete přeskočit, pokud ji nehodláte používat (stačí dát šipku zpět)
5. Na úvodní obrazovce by mělo pod náramkem být napsáno „Připojeno“  
<figure class="is-layout-flex wp-block-gallery-10 wp-block-gallery columns-3 is-cropped"><ul class="blocks-gallery-grid">
<li class="blocks-gallery-item"><figure><img decoding="async" loading="lazy" width="360" height="640" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/3.jpg" alt="" data-id="4303" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/3.jpg" data-link="https://maxxx.cz/?attachment_id=4303" class="wp-image-4303" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/3.jpg 360w, __GHOST_URL__ /content/images/wordpress/2020/09/3-169x300.jpg 169w" sizes="(max-width: 360px) 100vw, 360px"></figure></li>
<li class="blocks-gallery-item"><figure><img decoding="async" loading="lazy" width="360" height="640" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/4.1.jpg" alt="" data-id="4304" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/4.1.jpg" data-link="https://maxxx.cz/?attachment_id=4304" class="wp-image-4304" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/4.1.jpg 360w, __GHOST_URL__ /content/images/wordpress/2020/09/4.1-169x300.jpg 169w" sizes="(max-width: 360px) 100vw, 360px"></figure></li>
<li class="blocks-gallery-item"><figure><img decoding="async" loading="lazy" width="360" height="640" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/5.jpg" alt="" data-id="4305" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/5.jpg" data-link="https://maxxx.cz/?attachment_id=4305" class="wp-image-4305" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/5.jpg 360w, __GHOST_URL__ /content/images/wordpress/2020/09/5-169x300.jpg 169w" sizes="(max-width: 360px) 100vw, 360px"></figure></li>
</ul></figure>
### Instalace českého firmware

- Libovolným způsobem přesuňte soubory do mobilu.
- Já například používám [OneDrive](https://onedrive.live.com?invref=34ccf43311348c66&invscr=90), takže jsem si vše potřebné nahrál do sdílné složky a z mobilu už jen pouze spouště soubory v pořadí 
  - Firmware ([GeekDoing](https://geekdoing.com/threads/czech-firmware-2-3-0-6.386/#post-9679)) – zvolte dle své verze náramku
  - Resources ([Webshare](https://webshare.cz/#/folder/2Xi3ei6377))
  - Font (největší soubor, nahrávání trvá cca 5 minut) – ([GeekDoing](https://geekdoing.com/attachments/wuhan_2-2-0-14_font-zip.3156/?hash=8932b75c2b86733ee351f42e1d7a5c3c)) 
- Po kliknutí na daný soubor pouze zvolíte možnost **Otevřít skrze – Instalátor FW/App** a dáte Instalovat
- Následně můžete na hlavní obrazovce náramek „Odpárovat“ (ikona koše u náramku)
- V menu ukončit aplikaci a odinstalovat (pokud ji nehodláte používat).
<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="360" height="640" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/6.jpg" alt="" class="wp-image-4306" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/6.jpg 360w, __GHOST_URL__ /content/images/wordpress/2020/09/6-169x300.jpg 169w" sizes="(max-width: 360px) 100vw, 360px"></figure>

Nyní by jste měli mít váš náramek v češtině a můžete ho začít využívat ve spojení s některou aplikací.

<figure class="wp-block-embed is-type-video is-provider-youtube wp-block-embed-youtube wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
<iframe loading="lazy" title="android oreo" width="600" height="338" src="https://www.youtube.com/embed/ukHNqzI4AA8?feature=oembed" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div></figure>

Já spároval svůj MiBand3 opět s oficiální aplikací a pokud přijde aktualizace FW, která přehraje náramek zpět na čínštinu, tak provedu opětovný flash.  
Pokud se však tomuto chcete vyhnout, tak nainstalujte upravenou verzi oficiální aplikaci Mi Fit ([GeekDoing](https://geekdoing.com/forums/mi-fit.12/))

<figure class="is-layout-flex wp-block-gallery-12 wp-block-gallery columns-2 is-cropped"><ul class="blocks-gallery-grid">
<li class="blocks-gallery-item"><figure><img decoding="async" loading="lazy" width="527" height="937" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/IMG_20190218_210522.jpg" alt="" data-id="4307" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/IMG_20190218_210522.jpg" data-link="https://maxxx.cz/?attachment_id=4307" class="wp-image-4307" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/IMG_20190218_210522.jpg 527w, __GHOST_URL__ /content/images/wordpress/2020/09/IMG_20190218_210522-169x300.jpg 169w" sizes="(max-width: 527px) 100vw, 527px"></figure></li>
<li class="blocks-gallery-item"><figure><img decoding="async" loading="lazy" width="500" height="888" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/IMG_20190219_083933.jpg" alt="" data-id="4308" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/IMG_20190219_083933.jpg" data-link="https://maxxx.cz/?attachment_id=4308" class="wp-image-4308" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/IMG_20190219_083933.jpg 500w, __GHOST_URL__ /content/images/wordpress/2020/09/IMG_20190219_083933-169x300.jpg 169w" sizes="(max-width: 500px) 100vw, 500px"></figure></li>
</ul></figure>

Zdroj: [GeekDoing.com](https://geekdoing.com/forums/)

<!--kg-card-end: html-->