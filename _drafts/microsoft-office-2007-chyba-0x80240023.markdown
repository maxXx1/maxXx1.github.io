---
layout: post
title: Microsoft Office 2007 – chyba 0x80240023
tags:
- office-2007
- windows-10
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Někdy se při pokusu o update kancelářského balíku **MS Office 2007** na Windows 10 stává, že služba Windows Update vyhodí chybu **0x80240023**. Stane se tak při načtení aktualizace **Microsoft Office File Validation Add-in** , která vyžaduje potvrzení licenčních podmínek.

<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="587" height="241" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/wupdaterr.png" alt="" class="wp-image-4510" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/wupdaterr.png 587w, __GHOST_URL__ /content/images/wordpress/2020/10/wupdaterr-300x123.png 300w" sizes="(max-width: 587px) 100vw, 587px"></figure>

Pro její odstranění můžete vyzkoušet následující postup:

1. Stiskněte klávesy „ **Win** &nbsp;+&nbsp; **R** “ a zadejte: „ **services.msc** „.
2. Vyhledejte službu&nbsp; **Windows update**.
3. Klikněte pravým tlačítkem na Windows update a dejte&nbsp; **stop**.
<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="409" height="468" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/wusrv.png" alt="" class="wp-image-4509" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/wusrv.png 409w, __GHOST_URL__ /content/images/wordpress/2020/10/wusrv-262x300.png 262w" sizes="(max-width: 409px) 100vw, 409px"></figure>

Nyní můžete vyčistit složku mezipaměti Windows update:

- Stiskněte klávesy „ **Win&nbsp;** +&nbsp; **R** „, zadejte:

    %windir%\SoftwareDistribution\DataStore%windir%\SoftwareDistribution\DataStore

- Potvrďte **OK**
- Odstraňte veškerý obsah této složky.
- Znovu&nbsp; **spusťte Windows update**.

Pokud tento postup nezabere, tak přejděte do složky:

    C:\Windows\SoftwareDistribution\Download

Tam je třeba nalézt složku, ve které je soubor **OFV.CAB**

- Tento **soubor otevřete** a zvolte umístění (třeba na Plochu)
- Extrahovaný soubor **OFV.msi** manuálně nainstalujte.
- Poté opětovně spusťte vyhledávání aktualizací Windows Update
<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="564" height="180" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/wupdateok.png" alt="" class="wp-image-4517" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/wupdateok.png 564w, __GHOST_URL__ /content/images/wordpress/2020/10/wupdateok-300x96.png 300w" sizes="(max-width: 564px) 100vw, 564px"></figure>

Pokud ani tato oprava nepomůže, zkuste zakázat aktualizace balíčku Microsoft Office 2007. Jeho **podpora skončila** v roce 2014.

<figure class="wp-block-image size-large"><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/wupdateost.png"><img decoding="async" loading="lazy" width="1024" height="796" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/wupdateost-1024x796.png" alt="" class="wp-image-4511" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/wupdateost-1024x796.png 1024w, __GHOST_URL__ /content/images/wordpress/2020/10/wupdateost-300x233.png 300w, __GHOST_URL__ /content/images/wordpress/2020/10/wupdateost-768x597.png 768w, __GHOST_URL__ /content/images/wordpress/2020/10/wupdateost-1200x932.png 1200w, __GHOST_URL__ /content/images/wordpress/2020/10/wupdateost.png 1202w" sizes="(max-width: 1024px) 100vw, 1024px"></a></figure>

Pro bezproblémový běh Office 2007 by měl být zapotřebí **Service Pack 3** a dodatečné aktualizace, které Windows Update je schopný stáhnout.

[Stáhnout SP3](https://uloz.to/file/IRBMZZXM8fT9/office2007sp3-kb2526086-fullfile-cs-cz-exe)

<!--kg-card-end: html-->