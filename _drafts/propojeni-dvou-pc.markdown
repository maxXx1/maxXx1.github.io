---
layout: post
title: Propojení dvou PC
tags:
- hash-wordpress
- hash-import-2023-08-28-13-25
---

V dnešní době je již nepřeberné množství možností jak přenést data ze dvou PC. Pokud se kvantum dat pohybuje v řádech GB je skutečně rychlejší přenášet přes flash disk či kopírovat z HDD na HDD. I když nejlevnější možnost propojení dvou PC je pomocí kříženého LAN kabelu, který doma má téměř každý.

<!--more-->

Ať už kvůli přesunu dat, či v rámci domácí LAN párty ve dvou můžete využít tuto nejjednodušší možnost propojení dvou PC. Nové síťové karty již nevyžadují křížený kabel. Můžete tedy klidně použít kabel kterým jste připojení k routeru (domácímu internetu).

Takže co potřebujeme a jak budeme postupovat?

**1.** Síťový kabel s konektory RJ-45 (takové ty průhledné kostky, jako u telefonního kabelu, ale o něco větší)

**2.** Tento kabel připojíme do funkční a správně nainstalované síťové karty (předpokladem je aby síťová karta byla skutečně správně detekována v systému s aktuálním ovladačem)

**3.** Nyní protože mezi počítači je pouze kabel, nikoliv směřovač (router), musíme na obou PC nastavit TCP/IP protokol.

– Ve Windows: V **Ovládací** ch **Panel** ech v nastavení síťové karty (V různých verzích Windows se cesta k tomuto nastavení různí) musíte nastavit obě PC do stejného IP rozsahu.

 ![](http://www.ktknet.cz/appdata/obrazy00/utp-kabel.png)

**Příklad:**   
_PC1:  
IP: 1.1.1.1  
maska sítě: 255.255.255.0  
brána: 1.1.1.1_

PC2:  
IP: 1.1.1.2  
maska sítě: 255.255.255.0  
brána: 1.1.1.1

**4.** Na prvním či druhém PC si nastavíte jednu sdílenou složku (klik pravým – sdílet složku) pro výměnu dat či pouze otestování komunikace.

**5.** Z druhého PC se následně přes tuto složku k počítači připojíš. Nejjednodušeji (pokud je nastaven stejná pracovní skupina) tak přes ikonu Šíť či Místa v Síti a počítače ve skupině, kde by se Vám měla daná složka zobrazit.

**nebo**

Univerzální způsob: Otevřít tento počítač a do řádky Adresa zadáte adresu toho druhého PC (kterou jste před tím nastavili) ve tvaru \1.1.1.1 (nebo \1.1.1.2).

**6.** Poté co se zobrazí ona sdílená složka můžete vesele začít kopírovat či jinak komunikovat.

Pro každý případ bych však doporučil vypnout firewall, komunikujete pouze mezi dvěma stroji, takže se nemusíte bát nějakého viru či jiného smetí.

**Alternativa:**

Jiná možnost je například pořídit USB 2.0 kabel (rychlost až 480 Mbps) a komunikovat přes tento port, ale to jsem ještě netestoval.&nbsp;V současné době stojí např. u&nbsp;[alza.cz](http://www.alza.cz/premiumcord-easy-transfer-link-pro-spojeni-dvou-pocitacu-usb-2-0-d251641.htm#popis)&nbsp;něco kolem 250 korun.

[![](http://i.alz.cz/ImgW.ashx?fd=f3&cd=FV207i)](http://i.alz.cz/ImgW.ashx?fd=f3&cd=FV207i)
<!--kg-card-end: html-->