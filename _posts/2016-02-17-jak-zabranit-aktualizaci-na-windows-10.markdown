---
layout: post
title: Jak zabránit aktualizaci na Windows 10
date: '2016-02-17 20:14:35'
tags:
- update
- windows-10
- windows-7
- windows-8
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Microsoft s Windows 10 zamýšlí skutečně velké věci. Už to, že tomuto systému nechal otevřený životní cyklus a plánuje s ním obsadit více než jednu miliardu zařízení do roku 2018. Při svém počínání však nezvolil úplně šťastný způsob propagace a někomu (včetně mě) může připadat nabídka upgrade nucená až velmi agresivní.

Odpověď na otázku&nbsp;jestli upgradovat či nikoliv, nechám čistě na Vás. Co se týče nových počítačů dodaných s Windows 10 v rámci OEM licence, tak tam já osobně netlačím downgrade na nižší verzi OS. Na nových zařízení s Windows 8/8.1 (různé skladové ležáky) update na Windows 10 provádím v drtivé většině případů, protože Windows 8.1 se mezi uživateli moc neuchytilo a u těchto zařízení jsou dostupné oficiální ovladače od výrobce (pro W10).

Firemní uživatelé, uživatelé se zakoupenou licencí Windows 7 a majitelé starších PC (tedy alespoň ti, které já mám na starosti) spokojeně setrvávají&nbsp;na Windows 7. Dovolím si tvrdit, že minimálně do konce rozšířené podpory v roce 2025 &nbsp;budou tento systém bez problémů využívat a nepřesvědčí je ani časově omezená nabídka upgrade na Windows 10 zdarma.

> Železobeton! [pic.twitter.com/gAgrFodgOP](https://t.co/gAgrFodgOP)
> 
> — David Ježek (@dav\_je) [October 27, 2015](https://twitter.com/dav_je/status/659095948665180160)

<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

Nutno podotknout, že updatem na Windows 10 uděláte ze své přenosné či multi-licence, licenci vázanou na konkrétní PC. Zjednodušeně řečeno vám zůstane původní multi-licence (protože klíč v BIOSu se při updatovacím procesu změní), ale Windows 10 již bude vázáno na updatované PC (nezískáte další multi-licenci).

**Jak odstranit výzvu k rezervaci Windows 10 zdarma:**

Výzva k rezervaci Windows 10 se objeví v podobě bílého znaku Windows vedle hodin a občas na vás vychrlí nějaké to moudro o tom, kolik lidí již je na Windows 10 či jaké nesporné výhody pro vás nový OS má. Nejenom, že je to extrémně otravné, ale celá tato fraška je navíc absolutně nelogická, protože upgrade na Windows 10 není nijak limitován, proto by nemělo být třeba si ho nikterak rezervovat. Výzva vypadá takto:

![](http://192.168.20.2/wordpress/wp-content/uploads/2016/02/bezplatny-upgrade.png)

A stará se o ni na Windows 7 i 8 (8.1) aktualizace s označením&nbsp;**[KB3035583](https://support.microsoft.com/cs-cz/kb/3080351)**.

S přípravou systému pro přechod na nový operační systém souvisejí také tyto aktualizace –  
pro Windows 7: **KB2952664** , **KB3021917**  
pro Windows 8:&nbsp; **KB2976978**

Pokud upgrade neplánujete, můžete je odinstalovat jednoduše dvěma způsoby.

1. Pomocí **ovládacích panelů** :  
Přejděte do Nabídky Start – Ovládací panely – Programy a Funkce – Zobrazit nainstalované aktualizace a dle výše zmíněných názvů aktualizace vyhledat a odinstalovat.
2. Pomocí **příkazového řádku** :  
Do vyhledávání (v nabídce start) napište „ **cmd** “ – klikněte druhým tlačítkem a vyberte „Spustit jako správce“ – do příkazového řádku vypište příkaz:  
**wusa /uninstall /kb:3035583&nbsp;** a opakujte i pro ostatní výše zmíněné

![](http://192.168.20.2/wordpress/wp-content/uploads/2016/02/uninst3.png)

Pokud jste tak učinili, tak **restartujte počítač** a nechte **Windows Update** znovu vyhledat chybějící aktualizace. Tyto aktualizace by se měly znovu nabídnout k instalaci.  
Klikněte na ně pravým tlačítkem a u každé zvolte možnost „ **Skrýt** „. Aktualizace by se vám již neměly nikdy v této podobě nabídnout k instalaci.

Od jisté doby se začalo stávat to, že Windows Update nenabídne k instalaci nové aktualizace pro daný OS, nýbrž přímo aktuální build Windows 10, což je dle mého názoru absolutní nehoráznost. Microsoft postupem času usoudil, že Windows 10 je doporučená aktualizace. Tomu můžete předejít **vypnutím** funkce „Získávat doporučené aktualizace stejným způsobem jako důležité“ v nastavení **Windows Update**.

![](http://192.168.20.2/wordpress/wp-content/uploads/2016/02/nastaveni-aktualizaci.png)

Vypnutí této funkce, stejně jako skrytí aktualizace&nbsp; **KB3035583** je samozřejmě nejlepší provést dříve, než se u vás proces přípravy upgrade na Windows 10 zahájí. (např. v případě čisté instalace OS)

Pokud se tento proces u vás již instalací aktualizací spustil, tak je vhodné ještě prohledat kořenový adresář na systémovém disku (C:) a smazat složku „_ **$Windows.~BT** „,&nbsp;_která obsahuje instalační soubory Windows 10. Složka je skrytá a systémová, takže jejího smazání docílíte nejsnadněji pomocí nástroje&nbsp; **Vyčištění disku**.

1. Přejděte do „ **Počítač** “ (z plochy či nabídky start)
2. Zde vyberte disk na kterém máte operační systém (zpravidla C:)
3. Klikněte pravým tlačítkem myši a dejte **Vlastnosti**
4. Hned v první záložce klikněte na **Vyčištění disku**
5. Nyní musíte&nbsp;kliknout na **Vyčistit systémové soubory**
6. Po výpočtu velikosti souborů k odstranění klikněte na **OK**

Pokud jste toto učinili společně s předchozími kroky, tak by se mělo zabránit nejenom opětovnému vytvoření oné (mnohdy až 6GB velké) složky, ale také nabídce k upgrade v budoucnu.

**Alternativní postup:**

Nucený update lze také zakázat úpravou&nbsp; **zásad skupin** (verze Pro a vyšší):

1. vyhledejte a spusťte **Upravit zásady skupin**  
Cesta: _Konfigurace počítače \> Šablony pro správu \> Součásti systému Windows \> Windows Update_
2. Zde zvolte:&nbsp; **Vypnout aktualizaci na poslední verzi Windows pomocí Windows Update**  
Anglicky:&nbsp;_Turn off the upgrade to the latest version of Windows through Windows Update_
3. Zde dejte **Povolit&nbsp;** (ang.&nbsp;_Enable_)

Nebo **pomocí úpravy v** systémovém **registru&nbsp;** (všechny verze):

1. Spusťte „ **regedit** “ a vyhledejte podklíč:  
**HKLM\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate**
2. Zde vytvořte&nbsp;Hodnotu DWORD:  
**DisableOSUpgrade = 1**

(pokud jste zakázali aktualizaci přes zásady skupin, již tento klíč v registru budete mít)

**Zrušení notifikace** pro aktualizaci na Windows 10:

1. Spusťte „ **regedit** “ a vyhledejte podklíč:  
**HKLM\Software\Policies\Microsoft\Windows\Gwx**
2. Zde vytvořte Hodnotu DWORD:  
**DisableGwx = 1**

Kdyby se vám úprava s v systémovém registru nechtěla dělat ručně, tak je tu možnost &nbsp;stáhnout si připravený soubor registru, který udělá práci za vás:&nbsp;[DisableOSUpgrade.zip](http://www.maxxx.cz/download/disableosupgrade-zip/).

Pamatujte, že veškeré změny (nejenom registru) se projeví **až po restartu** počítače!

**To vše můžete provést na jedno kliknutí pomocí [.bat souboru](http://blog.ijacek007.cz/vypni-reklamu-w10-minimal.bat) od ijacek.007!&nbsp;**

<!--kg-card-end: html-->