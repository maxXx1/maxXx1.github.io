---
layout: post
title: Project /e/ Android bez Google
tags:
- nezarazene
- samsung
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Za tu dobu co dělám servis telefonů se kolem mě nashromáždilo obrovské množství starších telefonů, které tak nějak již nenacházejí uplatnění, zejména kvůli slabšímu výkonu (CPU a RAM), neaktualizovanému systému a malému úložišti (ROM).

Hledal jsem proto alternativu k běžnému Androidu u něhož jsou problémem zejména bobtnající služby samotného Google (Google Play Services), které každá instalace androidu vyžaduje aktuální (cca 300MB), pro běh svých služeb a vestavěných aplikací. Narazil jsem na fork Andoidu s názvem [Project /e/](https://e.foundation/). Tento projekt je založen na [Lineage OS](https://lineageos.org/), který nabízí čistý android, zejména pro novější zařízení. Oproti tomu je project /e/ ucelenější a chybějící aplikace google nahrazuje z větší části aplikacemi Android Open Source Project (na kterém staví i Lineage OS). Chybějící API služeb google simuluje [microG](https://microg.org/) (které aplikacím postaveným na google službách poskytne dané API bez toho, aby se něco odesílalo do Google) a obchod s aplikacemi Google Play nahradil vlastní obchod postavený na F-Droidu, který obsahuje open-source aplikace a [cleanAPK](https://info.cleanapk.org/), který nabízí i aplikace proprietární. Není tedy problém doinstalovat populární aplikace jako WhatsApp, Facebook, Instagram, Firefox, Telegram. Bohužel pro aplikace lokální (aplikace bank atd.) budete muset využít instalace skrze .apk a sami si pohlídat, jestli jsou dané apk čisté. Vše se tedy obejde bez Google a důrazem na zachování soukromí.

<figure class="aligncenter size-large"><img decoding="async" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/01/products-get-things-done.png" alt="" class="wp-image-3990"></figure>

e.foundation dokonce nabízí vlastní řešení cloudových služeb (postavených na [nextcloudu](https://nextcloud.com/)), ve kterých vám bezplatně nabídne 5GB prostoru zdarma. Pro užívání systému to ale není nutné. Vestavěný launcher je velmi inspirovaný vzhledem iOS – tedy jeden grid pro aplikace, žádné menu na více prokliků. Používání systému je tedy uživatelsky velmi příjemné a přehledné.

**Instalce**

- Najdete si vámi požadovaný [model telefonu](https://doc.e.foundation/devices/) (v mém případě Samsung Galaxy [S4 Mini](https://doc.e.foundation/devices/serranoltexx/)&nbsp;)
- A postupujete dle [oficiální dokumentace](https://doc.e.foundation/devices/serranoltexx/install)

Můžete tak velmi jednoduše doslova vdechnout nový život vašim starým zařízením, protože sestavení, které si do telefonu nahrajete bude obsahovat nejnovější bezpečnostní aktualizace a to i na X let starém telefonu. Můžete tedy čerpat s z věcí inovativních, což je zejména energetická úspornost, na které Google u Androidu opravdu zapracoval, tak z věcí, které dnes již na trhu nenaleznete a to je zejména vyměnitelná baterie (která je u starších modelů běžná) a snadná opravitelnost (většinou není nic lepené, ale hezky na šroubkách).

<figure class="wp-block-image size-large"><img decoding="async" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/01/EK1YJ9DW4AAzKdD-1024x512.jpg" alt="" class="wp-image-3992"></figure>

Project /e/ v současné době oficiálně podporuje téměř 90 zejména starších zařízení a další přibývají.

<!--kg-card-end: html-->