---
title: "Instalace Chromium OS na net/notebook"
date: "2013-07-22"
tags: 
  - "Laptop"
category: Linux
image: 
  path: "img/page/chromium-os.jpg"
  alt: "Chromium OS"
---

## Chromium OS

Chromium OS je volně šířená varianta komerčního Chrome OS od společnosti Google, který koncem roku 2009 uvolnil zdrojové kódy plánovaného Chrome OS pod svobodnou licencí.
Prostředí Chromium dominuje webový prohlížeč a vše důležité odehrává v něm avšak prostředí je dle mého názoru další desktopová distribuce GNU/Linuxu, která z se z pohledu použitých prostředků nápadně podobá Debianu. Je postaven na souborovém systému ext3/ext4, jsou využity klasické unixové démony (např. cron) a grafická knihovna Xlib. 
Rychlý start zajišťuje [upstart](https://en.wikipedia.org/wiki/Upstart_(software)).

![Netbook](/img/2013-07-22-chromium-os-netbook-install/Chrome-OS-Netbook.jpg)
_Acer Aspire ONE ZG5_

## Využití

Jak jsem již výše poznamenal, vše se v systému točí kolem webového prohlížeče a jeho (google) online služeb jako jsou vzdálený disk GoogleDrive (i když ukládat soubory lokálně je povoleno), GoogleDocuments (na této distribuci nenajdete žádný offline kancelářský balík typu LibreOffice), Gmail, Keep, Google Kalendář atd.
Pro získání nových aplikací a funkcí využíváte "Obchod Chrome", který obsahuje i aplikace spustitelné lokálně (offline) jako je např. Offline Gmail, poznámkový blok či kalkulačka...
Systém zvládne jednoduché úkony jako je například změnit hlasitost či jas display nebo připojit USB flash/externí disk a přehrát audio/video (na některém HW bývají problémy). Pro používání systému se ale striktně vyžaduje přihlášení pomocí google accuont (gmail login).
Verze Chrome OS je dodávána pouze s tzv. Chromebooky na které je optimalizována a nabízí větší kótu pro využití google drive, až 100GB...

## Minimální hardwarové požadavky

Minimální požadavky na a Váš hardware nejsou úplně striktně vymezeny. 
Někde jsem se dočetl, že leze systém spustit na 600Mhz procesoru s 256MB paměti RAM. Já však instaloval na netbooku __Acer Aspire ONE ZG5__ verzi s __16GB SSD__ diskem na ZIF rozhraní, procesorem __Intel Atom__ první generace (bez HT) na __1.6Ghz__ a __512MB__ operační paměti. Který mi už díky bohu neříká pane.

![ZG5](/img/2013-07-22-chromium-os-netbook-install/2013-02-28-10.53.51.jpg)
_Acer Aspire ONE ZG5_

## Acer Aspire One D250

Dostal se mi do ruky větší bráška ZG5 jde konkrétně o netbook s označením D250 o proti výše zmíněnému modelu disponuje větším __10" WSVGA LCD LED__ displayem a klasickým SATA HDD (s módem AHCI). Tento notebook jsem doplnil o __2GB DRR2 RAM__ (Kingston) avšak dále vše naznačuje tomu, že CPU, VGA a nejspíše i chipset jsou stejné.

Tento notebook se dělal samozřejmě ve více variantách. Mě se naštěstí dostala do ruky varianta se wifi kartou od výrobce __Atheros__, která dle oficiálního kompatibility listu funguje korektně na Chromium OS, varianta s kartou od výrobce Broadcom není podporována.

Spuštění systému a instalace proběhla naprosto identicky jako v případě ZG5 (dle návodu výše). Systém byl opět velmi svižný a vypadal o něco lépe což dokazuje, že vývoj jde zlehka ku předu.
Jediná věc, která se mi moc nezamlouvala bylo ovládání touchpadu, který reagoval velmi pomalu a při prudším pohybu dost agresivně akceleroval. Jinak mohu s klidným svědomím uznat, že i tento netbook je s Chromium OS použitelný!

![D250](/img/2013-07-22-chromium-os-netbook-install/20140304_210011.jpg)
_Acer Aspire One D250_

## Instalace 

- Nejprve je důležité stáhnout Chormium jako takové. ~~Nejlépe ze stránek ChromeOS.hexxeh.net.~~ (Vanilla build)

[Archív původního buildu](https://archiveos.org/chromiumos-vanilla/)

Poté vytvořit USB bootovatelné médium se systémem Chromium. Popíšu postup pro Windows, avšak na stránce je popsán i postup pro Lunux a Mac OSX..

1. Použijte WinRAR či [7Zip](https://www.7-zip.org/) k rozbalení .img souboru, který jste stáhli v předchozím kroku.
2. Dále použijte např. [Windows Image Writer](https://launchpad.net/win32-image-writer/) k vytvoření bootovatelného flashdisku (doporučuje se minimálně 4GB flash disk).
3. Vyberte `.img` soubor a zapište ho na daný flash disk, kliknutím na __Write__
4. Nyní máte vytvořen bootovatelný USB disk ze kterého můžete systém zavést (bez instalace) či nainstalovat na libovolné zařízení.
5. Do počítače na který chcete systém instalovat (či jen vyzkoušet) __vložte flash disk__ a __restartujte ho__.
6. Pomocí funkční klávesy vyvolejte nabídku výběru zařízení ze kterého se má bootovat (např. na ASUS Eee se jedná o klávesu Escape) či v BIOSu (nejčastěji pomocí klávesy "Del") v záložce BOOT přenastavte pořadí zařízení ze kterých se má bootovat tak aby USB Drive/Key bylo __na prvním místě.__
7. Po naběhnutí Chromium OS __se přihlaste__ pomocí svého Google Accontu.
8. V prostředí OS stiskněte kombinaci kláves `Ctrl + Alt + F2` pro přechod do textového módu
9. Zde se přihlaste pomocí loginu `chronos` a hesla `facepunch`
10. Dále napište příkaz `crosh` a podvrďte enterem.
11. Nyní napište příkaz `install` a potvrďte.
12. Instalace se Vás už jen dotáže, jestli skutečně může začít s instalací a jestli jste srozuměn s tím, že přijdete o svá data na disku, pokud ano, potvrďte klávesou `y`.
13. Možná budete znovu požádáni o zadání hesla (`facepunch`)
14. Po dokončení instalace vyjměte USB disk a __restartujte počítač__.

## Dual boot

Ten v případě ZG5 a jeho 16GB SSD nebyl absolutně realizovatelný. V případě D250 jsem si to na 350GB prostoru již mohl dovolit. Zatím se mi teda jako nejjednodušší řešení jeví.

1. __Nainstalovat Chromium OS__ (protože instalace je těžce konfigurovatelná)
2. Poté pomocí např. [Gparted](https://gparted.org/) __zredukovat místo__ pro Chromium OS
3. Na nepřiděleném místě __vytvořit nový oddíl__
4. Na prázdný oddíl __nainstalovat další systém__
5. Zavaděč bych řešil např. pomocí [GRUB](https://cs.wikipedia.org/wiki/GRUB)u, který s Chromium OS bezproblémově funguje.