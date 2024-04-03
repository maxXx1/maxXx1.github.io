---
layout: post
title: Instalace Chromium OS na net/notebook
tags:
- nezarazene
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Chromium OS je volně šířená varianta komerčního Chrome OS od společnosti Google, který koncem roku 2009 uvolnil zdrojové kódy plánovaného Chrome OS pod svobodnou licencí. Prostředí Chromium dominuje webový prohlížeč a vše důležité odehrává v něm avšak prostředí je dle mého názoru další desktopová distribuce GNU/Linuxu, která z se z pohledu použitých prostředků nápadně podobá Debianu. Je postaven na souborovém systému ext3/ext4, jsou využity klasické unixové démony (např. cron) a grafická knihovna Xlib. Rychlý start zajišťuje [upstart](http://upstart.ubuntu.com/).

<!--more-->

&nbsp;

## Způsob používání…

| |

Jak jsem již výše poznamenal, vše se v systému točí kolem webového prohlížeče a jeho (google) online služeb jako jsou vzdálený disk GoogleDrive (i když ukládat soubory lokálně je povoleno), GoogleDocuments (na této distribuci nenajdete žádný offline kancelářský balík typu LibreOffice), Gmail, Keep, Google Kalendář atd.  
Pro získání nových aplikací a funkcí využíváte „Obchod Chrome“, který obsahuje i aplikace spustitelné lokálně (offline) jako je např. Offline Gmail, poznámkový blok či kalkulačka…  
Systém zvládne jednoduché úkony jako je například změnit hlasitost či jas display nebo připojit USB flash/externí disk a přehrát audio/video (na některém HW bývají problémy). Pro používání systému se ale striktně vyžaduje přihlášení pomocí google accuont (gmail login).  
Verze Chrome OS je dodávána pouze s tzv. Chromebooky na které je optimalizována a nabízí větší kótu pro využití google drive, až 100GB…

## Minimální hardwarové požadavky…

Minimální požadavky na a Váš hardware nejsou úplně striktně vymezeny. Někde jsem se dočetl, že leze systém spustit na 600Mhz procesoru s 256MB paměti RAM. Já však instaloval na netbooku [Acer Aspire ONE ZG5](http://acer.katalognotebooku.cz/notebook/acer-aspire-one-aoa110-ab) verzi s **16GB SSD** diskem na ZIF rozhraní, procesorem **Intel Atom** první generace (bez HT) na **1.6Ghz** a **512MB operační paměti**. Který mi už díky bohu neříká pane.

&nbsp;

<figure id="attachment_597" aria-describedby="caption-attachment-597" style="width: 648px" class="wp-caption aligncenter"><a href="http://www.maxxx.cz/wp-content/uploads/2013/07/2013-02-28-10.53.51.jpg"><img decoding="async" loading="lazy" class="size-large wp-image-597" src="http://www.maxxx.cz/wp-content/uploads/2013/07/2013-02-28-10.53.51-1024x768.jpg" alt="Nabídka aplikací" width="648" height="486"></a><figcaption id="caption-attachment-597" class="wp-caption-text">Nabídka aplikací</figcaption></figure>

**Jak nainstalovat Chromium OS na harddisk…**

- Nejprve je důležité stáhnout Chormium jako takové.Nejlépe ze stránek&nbsp;[ChromeOS.hexxeh.net](http://chromeos.hexxeh.net/). (Vanilla build)

Poté vytvořit USB bootovatelné médium se systémem Chromium. Popíšu postup pro Windows, avšak na stránce je popsán i postup pro Lunux a Mac OSX…

1. Použijte WinRAR či [7ZIP](http://www.7-zip.org/)&nbsp;k rozbalení .img souboru, který jste stáhli v předchozím kroku.
2. Dále použijte např. [Windows Image Writer](https://launchpad.net/win32-image-writer/)&nbsp;k vytvoření bootovatelného flashdisku (doporučuje se minimálně 4GB flash disk).
3. Vyberte .img soubor a zapište ho na daný flash disk, kliknutím na „Write“
4. Nyní máte vytvořen bootovatelný USB disk ze kterého můžete systém zavést (bez instalace) či nainstalovat na libovolné zařízení.
5. Do počítače na který chcete systém instalovat (či jen vyzkoušet) vložte flash disk a restartujte ho.
6. Pomocí funkční klávesy vyvolejte nabídku výběru zařízení ze kterého se má bootovat (např. na ASUS Eee se jedná o klávesu Escape) či v BIOSu (nejčastěji pomocí klávesy „Del“) v záložce BOOT přenastavte pořadí zařízení ze kterých se má bootovat tak aby USB Drive/Key bylo na prvním místě.
7. Po naběhnutí Chromium OS se přihlaste pomocí svého Google Accontu.
8. V prostředí OS stiskněte kombinaci kláves Ctrl + Alt +&nbsp;F2 pro přechod do textového módu
9. Zde se přihlaste pomocí loginu „chronos„ a hesla „facepunch„
10. Dále napište příkaz „crosh“ a podvrďte enterem.
11. Nyní napište příkaz „install„ a potvrďte.
12. Instalace se Vás už jen dotáže, jestli skutečně může začít s instalací a jestli jste srozuměn s tím, že přijdete o svá data na disku, pokud ano, potvrďte klávesou „y„.&nbsp;
13. Možná budete znovu požádáni o zadání hesla („facepunch“)
14. Po dokončení instalace vyjměte USB disk a restartujte počítač.
<figure id="attachment_598" aria-describedby="caption-attachment-598" style="width: 648px" class="wp-caption aligncenter"><a href="http://www.maxxx.cz/wp-content/uploads/2013/07/2013-02-27-20.32.55.jpg"><img decoding="async" loading="lazy" class="size-large wp-image-598" src="http://www.maxxx.cz/wp-content/uploads/2013/07/2013-02-27-20.32.55-1024x768.jpg" alt="Nabídka nastavení" width="648" height="486"></a><figcaption id="caption-attachment-598" class="wp-caption-text">Nabídka nastavení</figcaption></figure>
A nyní můžete začít používat váš instantní spouštěč internetu s názvem Chromium OS. Existuje také speciálně upravená verze tohoto systému pro netbooky Dell, konkrétně modely Mini 9 a 10v, která se dá stáhnout na [stránkách Dell](http://linux.dell.com/files/cto/)&nbsp;a mírně se liší v postupu instalace a UI.

<figure id="attachment_600" aria-describedby="caption-attachment-600" style="width: 300px" class="wp-caption aligncenter"><a href="http://www.maxxx.cz/wp-content/uploads/2013/07/2013-02-28-10.29.56.jpg"><img decoding="async" loading="lazy" class="size-medium wp-image-600" src="http://www.maxxx.cz/wp-content/uploads/2013/07/2013-02-28-10.29.56-300x225.jpg" alt="Plocha" width="300" height="225"></a><figcaption id="caption-attachment-600" class="wp-caption-text">Plocha</figcaption></figure>

## Aktualizace:&nbsp;Acer Aspire One D250

Dostal se mi do ruky větší bráška **ZG5** jde konkrétně o netbook s označením D250 o proti výše zmíněnému modelu disponuje větším&nbsp; **10″ WSVGA LCD LED** displayem a klasickým SATA HDD (s módem AHCI). Tento notebook jsem doplnil o **2GB DRR2 RAM** (Kingston) **&nbsp;** avšak dále vše naznačuje tomu, že CPU, VGA a nejspíše i chipset jsou stejné.

Tento notebook se dělal samozřejmě ve více variantách. Mě se naštěstí dostala do ruky varianta se wifi kartou od výrobce **Atheros** , která dle [oficiálního kompatibility listu](https://sites.google.com/a/chromium.org/dev/chromium-os/getting-dev-hardware/dev-hardware-list)&nbsp;funguje korektně na Chromium OS, varianta s kartou od výrobce Broadcom není podporována.

Spuštění systému a instalace proběhla naprosto identicky jako v případě ZG5 (dle návodu výše). Systém byl opět velmi svižný a vypadal o něco lépe což dokazuje, že vývoj jde zlehka ku předu.

Jediná věc, která se mi moc nezamlouvala bylo ovládání touchpadu, který reagoval velmi pomalu a při prudším pohybu dost agresivně akceleroval. Jinak mohu s klidným svědomím uznat, že i tento netbook je s Chromium OS použitelný!

[![](http://2.bp.blogspot.com/-gmHwfOMnk6k/UxccyyMGJxI/AAAAAAAAHQM/JNfrfCPL_yc/s1600/20140304_205943_Android.jpg)](http://2.bp.blogspot.com/-gmHwfOMnk6k/UxccyyMGJxI/AAAAAAAAHQM/JNfrfCPL_yc/s1600/20140304_205943_Android.jpg)[![](http://2.bp.blogspot.com/-yyHX-eUPA6M/Uxcc3bNP7eI/AAAAAAAAHQU/Dw5toHtJ1wg/s1600/20140304_210011_Android.jpg)](http://2.bp.blogspot.com/-yyHX-eUPA6M/Uxcc3bNP7eI/AAAAAAAAHQU/Dw5toHtJ1wg/s1600/20140304_210011_Android.jpg)

[![](http://4.bp.blogspot.com/-y2pVi-_qF-Y/Uxcc6A0-GgI/AAAAAAAAHQc/nSQtJThVboo/s1600/20140304_210030_Android.jpg)](http://4.bp.blogspot.com/-y2pVi-_qF-Y/Uxcc6A0-GgI/AAAAAAAAHQc/nSQtJThVboo/s1600/20140304_210030_Android.jpg)

## Dual boot s Chromium OS

V komentářích se objevil dotaz (za což velmi děkuji – je vidět, že to nepíšu sám pro sebe) na téma dual boot. Ten v případě ZG5 a jeho 16GB SSD nebyl absolutně realizovatelný. V případě D250 jsem si to na 350GB prostoru již mohl dovolit. Zatím se mi teda jako nejjednodušší řešení jeví.

1. Nainstalovat Chromium OS (protože instalace je těžce konfigurovatelná)
2. Poté pomocí např. [Gparted](http://gparted.org/)&nbsp;zredukovat místo pro Chromium OS
3. Na nepřiděleném místě vytvořit nový oddíl
4. Na prázdný oddíl nainstalovat další systém
5. Zavaděč bych řešil např. pomocí [GRUB](http://cs.wikipedia.org/wiki/GRUB)u, který s Chromium OS bezproblémově funguje.

&nbsp;

<!--kg-card-end: html-->