---
layout: post
title: Aktualizace firmware televize 42LG3000
tags:
- nezarazene
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Stal jsem se majitelem LCD televize LG přesněji typu **42LG3000-ZA** jako televize fungovala opravdu dobře, problém se objevil až ve chvíli, když jsem chtěl přes kabel HDMI-HDMI propojit televizi s počítačem. Po připojení (respektive spárování s počítačem) mi vypadl signál televize (KOAX), proto jsem se uchýlil k aktualizaci firmware. Přes USB rozhraní, které se nachází na zadní straně televize a slouží pro tento účel (možná i jiné servisní úkony), ale film, fotky či jakékoli jiné soubory přes něj nepřehrajete, tento model to neumožňuje (ani žádnou neoficiální cestou/úpravou).

<!--more-->

Postup je velmi jednoduchý a je shodný pro pro více modelů. Nejprve je důležité sehnat si kompatibilní flash disk. Z předešlých zkušeností doporučuji flash disk od firmy Kingston, protože mám ověřeno, že fungují téměř na všem. Je vhodné zvolit spíše starší model s menší kapacitou (pod 4GB), protože nové disky (s větší kapacitou) bývají také opatřeny různými vychytávkami, které by televize nemusela akceptovat.

Poté si zjistíme ze zadní strany televize přesné modelové označení. Viz. foto…

[![](http://2.bp.blogspot.com/-Ljlw5RKsIOE/UioGWtFtx4I/AAAAAAAADQE/L_WtVBSpqCg/s320/2013-09-01+12.39.32.jpg)](http://2.bp.blogspot.com/-Ljlw5RKsIOE/UioGWtFtx4I/AAAAAAAADQE/L_WtVBSpqCg/s1600/2013-09-01+12.39.32.jpg)

1. Na stránkách společnosti LG si najdeme v sekci podpory (support) váš model, poté v záložce „software update“ stáhneme aktuální firmware, který vždy obsahuje všechny předešlé verze.  
(v mém připadě zde:&nbsp;[http://www.lg.com/uk/support-product/lg-42LG3000-ZA.AEK](http://www.lg.com/uk/support-product/lg-42LG3000-ZA.AEK))  
2. Flash disk zformátujeme do souborového systému **FAT** (nikoli FAT32)  
3. Archív (v mém připadě _Software\_File%28Version\_03.55.01%29.zip_) rozbalíme a výsledný .bin soubor přesuneme na flash disk (do rootu)  
4. V televizi položku v „ **MENU – NASTAV. – Akt. Softwaru** “ nastavíme na hodnotu „ **Zap** „. a televizi poté vypneme.  
5. Od televize odpojíme všechny konektory (HDMI, DVI, SCART i anténu), ponecháme pouze napájení.  
6. &nbsp;Vložíme flash disk s nahraným firmware do USB v zadní straně televize.  
7. Televizi zapneme a ta by měla automaticky začít nahrávat aktuální firmware z „flashky“ viz. foto…

[![](http://1.bp.blogspot.com/-IDW2S0vaII0/UioKfuojSmI/AAAAAAAADQQ/Nvf1_5u9HLQ/s320/2013-09-06+18.21.51.jpg)](http://1.bp.blogspot.com/-IDW2S0vaII0/UioKfuojSmI/AAAAAAAADQQ/Nvf1_5u9HLQ/s1600/2013-09-06+18.21.51.jpg)

**Je velmi důležité, aby jste během této operaci televizi nevypínaly, nepřepínaly a ani se nepokoušeli vytáhnout disk. Televizi by jste tímto jednáním mohly „bricknout“ a tím ji nenávratně poškodit!**

8. Po dokončení operace by se měla televize sama restartovat, poté můžete disk vyjmout a zkontrolovat v&nbsp;„ **MENU – NASTAV. – Diagnostika** “ novou verzi vašeho firmware.

Mnou avizovaný problém se updatem firmware vyřešil, pokud by snad někdo řešil stejný problém, tak několik dalších návrhů vznesl i moderátor na fóru&nbsp;[TVFreak](http://www.tvfreak.cz/forum/showthread.php/35708-LG-42LG3000-no-signal-s-HDMI), kterému bych chtěl touto cestou poděkovat.

<!--kg-card-end: html-->