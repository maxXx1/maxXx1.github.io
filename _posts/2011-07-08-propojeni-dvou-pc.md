---
title: "Propojení dvou PC"
date: "2011-07-08"
tags: 
category: "Síť"
image: 
  path: /img/2011-08-08-propojeni-dvou-pc/propojeni.jpg
  alt: "PC - PC"
---

V dnešní době je již nepřeberné množství možností jak přenést data ze dvou PC. Pokud se kvantum dat pohybuje v řádech GB je skutečně rychlejší přenášet přes flash disk či kopírovat z HDD na HDD. I když nejlevnější možnost propojení dvou PC je pomocí kříženého LAN kabelu, který doma má téměř každý.

Ať už kvůli přesunu dat, či v rámci domácí LAN párty ve dvou můžete využít tuto nejjednodušší možnost propojení dvou PC. Nové síťové karty již nevyžadují křížený kabel. Můžete tedy klidně použít kabel kterým jste připojení k routeru (domácímu internetu).

__Takže co potřebujeme a jak budeme postupovat?__
1. Síťový kabel s konektory RJ-45 (takové ty průhledné kostky, jako u telefonního kabelu, ale o něco větší)
2. Tento kabel připojíme do funkční a správně nainstalované síťové karty (předpokladem je aby síťová karta byla skutečně správně detekována v systému s aktuálním ovladačem)
3. Nyní protože mezi počítači je pouze kabel, nikoliv směřovač (router), musíme na obou PC nastavit TCP/IP protokol.
- Ve Windows: V __Ovládacích Panelech__ v nastavení síťové karty (V různých verzích Windows se cesta k tomuto nastavení různí) musíte nastavit obě PC do stejného IP rozsahu.

![schema](/img/2011-08-08-propojeni-dvou-pc/schema.gif)

__Příklad:__

```
PC1:
IP: 192.168.0.10
maska sítě: 255.255.255.0
brána: 192.168.0.20
```

```
PC2:
IP: 192.168.0.20
maska sítě: 255.255.255.0
brána: 192.168.0.10
```

- Na prvním či druhém PC si nastavíte jednu sdílenou složku (klik pravým - sdílet složku) pro výměnu dat či pouze otestování komunikace.
- Z druhého PC se následně přes tuto složku k počítači připojíš. Nejjednodušeji (pokud je nastaven stejná pracovní skupina) tak přes ikonu Šíť či Místa v Síti a počítače ve skupině, kde by se Vám měla daná složka zobrazit.
nebo
 - Univerzální způsob: Otevřít tento počítač a do řádky Adresa zadáte adresu toho druhého PC (kterou jste před tím nastavili) ve tvaru `\\192.168.0.10` (nebo `\\192.168.0.20`).
- Poté co se zobrazí ona sdílená složka můžete vesele začít kopírovat či jinak komunikovat.

Pro každý případ bych však doporučil vypnout firewall, komunikujete pouze mezi dvěma stroji, takže se nemusíte bát nějakého viru či jiného smetí.