---
layout: post
title: Avast FREE Anti-Virus
tags:
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Avast Anti-Virus je velmi populární řešení anti-viru zdarma od české společnosti. Pokud chce někdo ode mě doporučení na dobré anti-virové řešení v češtině a zdarma, tak ho taktéž doporučuji. Má to však několik zádrhelů, které se budu snažit postupně vysvětlit.

Jako základní anti-virové řešení se hodí **pro jednotlivce a domácnosti**. Pokud jste podnik s více stanicemi, serverem a komplikovanější síťovou infrastrukturou, tak bych doporučil spíše placené řešení, ale nikoliv od Avastu (např. [ESET](http://www.eset.com/cz/)).

Nespornou výhodou tohoto řešení je nejenom to, že je zdarma. Avast podporuje všechny operační systémy od Windows XP s nainstalovaným posledním Service Packem a je kompletně v češtině.

[button style=“btn-default btn-lg btn-block“ icon=“fa fa-windows“ align=“left“ iconcolor=“#0087ff“ type=“link“ target=“true“ title=“Stáhnout Avast“ link=“http://www.avast.com/get/T0r9Dn2n“ linkrel=““]

&nbsp;

#### Pokud instalujete Avast měli by jste si dát pozor hned na několik věcí:

1. Pokud instalujete Avast, ujistěte se, že na vašem počítači není již nainstalován jiný antivirus. Pokud ano, tak jej odinstalujte!
2. Neinstalujte nic navíc.  
Při prvním spuštění instalátoru FREE verze vám Avast nabídne (v dolní části okna) volitelnou instalaci Google Chrome, DropBoxu či Google Toolbaru.  
Tyto volby zrušte, protože tyto programy nechcete nebo už je máte.
3. Neinstalujte nástroje, které nebudete využívat  
V instalátoru nedávejte „Nainstalovat“, ale „ **Přizpůsobit** „. A ponechte pouze první 3 součásti systému. Zbytek jsou pouze doplňkové nástroje, které ve většině případů nefungují vůbec dobře nebo mají lepší alternativy.  
[![avast](http://www.maxxx.cz/wp-content/uploads/2016/02/avast-300x209.png)](http://www.maxxx.cz/wp-content/uploads/2016/02/avast.png)Pokud již máte nainstalováno (nebo jste jen omylem klikli na „Nainstalovat“), tak tuto úpravu provedete skrze – Start – Ovládací panely – Programy a funkce – Avast Free Antivirus – (odinstalovat) – Změnit.
4. Po instalaci či změně vždy proveďte restart počítače.

#### Po instalaci by jste měli věnovat chvilku prvotnímu nastavení:

1. Klikněte v horní části okna na „ **Registrovat** “ a vyplňte libovolnou emailovou adresu. Tímto si zajistíte licenci FREE antiviru na 1. rok zdarma.
2. Přejděte do **Nastavení&nbsp;** (ozubené kolo vpravo nahoře) – zde zapněte Tichý/herní režim (aby vás Avast neobtěžoval reklamami) a vypněte funkci vkládání podpisu do emailů (protože je to [pouze reklama](https://365tipu.wordpress.com/2016/01/11/tip376-mohu-verit-napisu-tento-email-byl-odeslan-z-pocitace-bez-viru-chraneneho-programem-xy/)).  
[![nastavení](http://www.maxxx.cz/wp-content/uploads/2016/02/nastavení-300x242.jpg)](http://www.maxxx.cz/wp-content/uploads/2016/02/nastavení.jpg)

#### Řešení problémů:

Nyní máte správně nainstalováno i nastaveno, ale dodatečně by vás mohlo potkat několik problémů – některé z nich se pokusím vyřešit:

1. **Nejde nahrávat soubory** na internet ( **Google Play Music chyba 16** )  
Je způsobeno scanováním protokolu HTTPS, které provádí webový štít. Tato funkce se dá vypnout skrze Nastavení – Aktivní ochrana – Webový štít (upravit) – zrušit zaškrtnutí u „Povolit testování HTTPS“
2. **Problémy s Windows 10** (mizející ikony a nefunkční nabídka start/zvuk) popř. **nefunkční VirtualBox**.  
Řešením je přejít do Nastavení – Řešení problémů – zrušit zaškrtnutí u“Povolit hardwarovou virtualizaci“
3. A neměl bych zapomenout, že hromadu jiných problémů řeší **pravidelná aktualizace**. Kterou ručně vyvoláte skrze  
Neastavení – Aktualizace – sekce Program – Aktualizovat.

#### Důležité upozornění:

Za žádných okolností **nepoužívejte** „bezpečný prohlížeč“ SafeZone od Avastu, protože se jedná pouze o upravené [Chromium](https://www.chromium.org/) (fork Chrome), které má několik závažných [bezpečnostních děr](https://code.google.com/p/google-security-research/issues/detail?id=679).

Po aktualizaci na nejnovější verzi (2015) Avast FREE automaticky doinstaluje prohlížeč SafeZone a komponentu Hesla, takže Ovládací panely – Programy a Funkce a Změnit.  
Odstranit obě výše zmíněné komponenty, protože hlavně prohlížeč SafeZone trpí [neustálými problémy](https://forum.avast.com/index.php?topic=183940.0).

Pokud máte nějaké další dotazy či problémy, napište mi o nich do komentářů.

<!--kg-card-end: html-->