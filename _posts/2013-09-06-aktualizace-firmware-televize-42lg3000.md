---
title: "Aktualizace firmware televize 42LG3000"
date: "2013-07-24"
category: Hardware
tags: 
  - "TV"
image:
  path: /img/2013-09-06-aktualizace-firmware-televize-42lg3000/42LG3000.jpg
  alt: LG 42lg3000  
---

Stal jsem se majitelem LCD televize LG přesněji typu __42LG3000-ZA__ jako televize fungovala opravdu dobře, problém se objevil až ve chvíli, když jsem chtěl přes kabel HDMI-HDMI propojit televizi s počítačem.
 Po připojení (respektive spárování s počítačem) mi vypadl signál televize (KOAX), proto jsem se uchýlil k aktualizaci firmware. 
 Přes USB rozhraní, které se nachází na zadní straně televize a slouží pro tento účel (možná i jiné servisní úkony), ale film, fotky či jakékoli jiné soubory přes něj nepřehrajete, tento model to neumožňuje (ani žádnou neoficiální cestou/úpravou).

 Postup je velmi jednoduchý a je shodný pro pro více modelů. 
 Nejprve je důležité sehnat si kompatibilní flash disk. 
 Z předešlých zkušeností doporučuji flash disk od firmy Kingston, protože mám ověřeno, že fungují téměř na všem. 
 Je vhodné zvolit spíše starší model s menší kapacitou (pod 4GB), protože nové disky (s větší kapacitou) bývají také opatřeny různými vychytávkami, které by televize nemusela akceptovat.
Poté si zjistíme ze zadní strany televize přesné modelové označení. Viz. foto...

![model](/img/2013-09-06-aktualizace-firmware-televize-42lg3000/2013-09-01-12.39.32.jpg)
_Model_

1. Na stránkách společnosti LG si najdeme v sekci podpory (support) váš model, poté v záložce "software update" stáhneme aktuální firmware, který vždy obsahuje všechny předešlé verze - v mém připadě zde: [lg-42LG3000-ZA.AEK](https://www.lg.com/uk/support-product/lg-42LG3000-ZA.AEK) 
2. Flash disk zformátujeme do souborového systému FAT (nikoli FAT32)
3. Archív (v mém připadě `Software_File%28Version_03.55.01%29.zip`) rozbalíme a výsledný `.bin` soubor přesuneme na flash disk (do rootu)
4. V televizi položku v "MENU - NASTAV. - Akt. Softwaru" nastavíme na hodnotu "Zap". a televizi poté vypneme.
5. Od televize odpojíme všechny konektory (HDMI, DVI, SCART i anténu), ponecháme pouze napájení.
6. Vložíme flash disk s nahraným firmware do USB v zadní straně televize.
7. Televizi zapneme a ta by měla automaticky začít nahrávat aktuální firmware z "flashky" viz. foto...

![update](/img/2013-09-06-aktualizace-firmware-televize-42lg3000/2013-09-06-18.21.51.jpg)

> Je velmi důležité, aby jste během této operaci televizi nevypínaly, nepřepínaly a ani se nepokoušeli vytáhnout disk. Televizi by jste tímto jednáním mohly "bricknout" a tím ji nenávratně poškodit!
{: .prompt-danger }

Po dokončení operace by se měla televize sama restartovat, poté můžete disk vyjmout a zkontrolovat v __MENU - NASTAV. - Diagnostika__ novou verzi vašeho firmware.

_Mnou avizovaný problém se updatem firmware vyřešil, pokud by snad někdo řešil stejný problém, tak několik dalších návrhů vznesl i moderátor na fóru [TVFreak](https://www.tvfreak.cz/forum/showthread.php/35708-lg-42lg3000-no-signal-s-hdmi), kterému bych chtěl touto cestou poděkovat._