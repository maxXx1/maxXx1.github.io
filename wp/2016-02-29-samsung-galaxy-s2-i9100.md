---
title: "Samsung Galaxy SII  - instalace CM 12.1"
date: "2016-02-29"
categories: 
  - "nezarazene"
tags: 
  - "cyanogenmod"
  - "kernel"
  - "nezarazene"
  - "recovery"
  - "samsung"
coverImage: "cyanogenmod-nexus-5-boot-screen-aa-1-1024x643-1.jpg"
---

Dneska se podíváme na Samsung Galaxy SII ([i9100](http://www.samsung.com/cz/support/model/GT-I9100LKAXEZ)). Ukážu vám jak na něj nainstalovat [Cyanogenmod](http://www.cyanogenmod.org/). Návod se budu snažit napsat tak, aby byl univerzální pro nahrání jakékoliv ROM či kernelu za použití flashovacího nástroje Odin.

**Kernel:** Je jich mnoho, ale já zvolil kernel TRIM (od [Lanchon](https://www.androidfilehost.com/?w=profile&uid=23578570567714207)a) protože mi přišlo, že právě tento kernel využívá maximálního potenciálu zařízení a navíc jsem ho našel v obrazu flashovatelném programem ODIN.

**ROM:** Zde padla volba na Cyanogenmod 12.1, který ve svém posledním snapshotu obsahuje nejméně [známých chyb](https://wiki.cyanogenmod.org/w/Known_Issues_page_for_i9100#CyanogenMod_12.1) (jen jednu) pro toto zařízení a navíc lze do návodu zahrnout jeden mezikrok navíc (neresetování zařízení pro přímou instalaci gapps).

**Gapps:** Můžete použít libovolné, ale já jich zkoušel více a např. ty přímo určené pro CM 12.1 mi nefungovaly.

### Co budeme potřebovat:

1. Flashovací program [ODIN](https://drive.google.com/open?id=0B3aDgwyDZ8Obdy1KUUJNdlhjejg) (já použil v1.85)
2. Samsung [USB ovladač](http://androidhost.org/XIVsA)e.
3. Kernel vč. recovery ([kernel-Lanchon-TRIM-FreezeFix-TWRP-20160111-cm-12.1-i9100-for-ODIN](https://drive.google.com/open?id=0B3aDgwyDZ8Oba2tVQ2t5QkpOSEE))
4. ROM ([cm-12.1-20151116-SNAPSHOT-YOG7DAO1JN-i9100.zip](http://download.cyanogenmod.org/get/jenkins/135113/cm-12.1-20151116-SNAPSHOT-YOG7DAO1JN-i9100.zip))
5. Gapps ([gapps-L-4-21-15.zip](http://downloadandroidrom.com/file/gapps/5.1/gapps-L-4-21-15.zip))

**Speciální bootovací metody:**

- **Recovery:** Volume Up (zvýšení hlasitosti), Home (tlačítko pod displayem) a Power (tlačítko na zapnutí)
- **Download:** Volume Down (snížení hlasitosti), Home (tlačítko pod displayem) a Power (tlačítko na zapnutí)

Pro vstup do daného módu bootování musíte tlačítka dohromady podržet při zapnutí telefonu alespoň po dobu 10s.

### Příprava:

- ODIN si rozbalte do libovolné složky.
- Nainstalujte USB ovladače.
- Kernel ponechte v archívu .tar a dále ho nerozbalujte!
- Zip archívy s ROM a Gapps přetáhněte na SDkartu (nerozbalujte je!)
- SDkartu vložte do telefonu.

### Postup:

1. Nabootojte do **Download Mode** (vol- + home + power) a potvrďte vstup **volume+**
2. Po zobrazení nápisu „Downloading… Do not turn off target!!“ **připojte telefon** k počítači pomocí USB kabelu.
3. **Spusťte ODIN** (jako správce).
4. **Zrušte** označení u kolonky "Auto-reboot".
5. Klikněte na "**PDA**" ("**AP**") a vyhledejte cestu k vašemu kernelu (formát .tar)
6. Klikněte na "**Start**" a vyčkejte na dokončení procesu.
7. Až program napíše, že vše je úspěšně dokončeno, tak **odpojte telefon** od PC a **vytáhněte baterii** čímž telefon vypnete.
8. Vraťte zpět baterii a kombinací  vol+ + home + power **vejděte do recovery**.
9. Zde zvolte "**wipe**" - zvolte vše kromě SDkarty.
10. Poté "**Install**" a vyberte v našem případě "cm-12.1-20151116...zip"
11. Po dokončení **nerestartujte zařízení**, ale vraťte se o krok zpět a stejným způsobem skrze "Install" flashněte i Gapps-L-4-21-15.zip.\[notification type="alert-info" close="false" \]Tento mezikrok je velmi důležitý, protože pokud necháte telefon nabootovat do systému, tak se vaše recovery aktualizuje na Cyanogen Recovery skrz které mi nešly flashnout gapps!\[/notification\]
12. poté zvolte již "**reboot**" a je hotovo.

Pro jistotu si můžete celý postup sjet i na videu

https://www.youtube.com/watch?v=YL8H70Es4wg

Návod jsem psal po paměti, tak doufám, že nic nechybí. Samozřejmě [ROM](http://forum.xda-developers.com/galaxy-s2/orig-development/13-05-14-index-roms-t1531244), [Kernel](http://forum.xda-developers.com/galaxy-s2/development-derivatives/convert-kernel-zip-to-tar-t2994381#4) i Recovery ([CWM](http://forum.xda-developers.com/showthread.php?t=2015369)/[TWRP](http://forum.xda-developers.com/showthread.php?t=1622917)) můžete zvolit libovolné. Na toto zařízení je jich dostupných obrovské množství na [XDA Fóru](http://forum.xda-developers.com/galaxy-s2).
