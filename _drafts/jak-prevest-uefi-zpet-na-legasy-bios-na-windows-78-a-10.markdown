---
layout: post
title: Jak převést UEFI zpět na Legasy BIOS (Windows 7,8 a 10)
tags:
- windows-10
- windows-7
- windows-8
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Pokud hledáte způsob, jak převést **UEFI** (Unified Extensible Firmware Interface) na **Legacy BIOS** (Basic Input / Output System) na již nainstalovaném systému **bez ztráty dat** , tak můžete pokračovat podle tohoto návodu. Proces byl sice prováděný na Windows 10, ale lze jej použít pro libovolný systém od Windows 7.

**KROK 1: Podívejte se, v jakém módu BIOS je**

Klávesovou zkratkou **Win + R** otevřete dialogové okno „Spustit“ napište „ **msinfo32** “ a potvrďte klávesou **Enter** pro zobrazení systémových informací.

<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="399" height="206" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/msinfo32.png" alt="" class="wp-image-4482" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/msinfo32.png 399w, __GHOST_URL__ /content/images/wordpress/2020/10/msinfo32-300x155.png 300w" sizes="(max-width: 399px) 100vw, 399px"></figure>

V souhrnu systémových informací vás zajímá řádek **režim systému BIOS** (BIOS Mode), pokud je v něm hodnota UEFI, tak můžete pokračovat v převedení výchozího bootování na Legacy.

<figure class="wp-block-image size-large"><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/Snimek-obrazovky-2020-10-19-133910.png"><img decoding="async" loading="lazy" width="1024" height="770" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/Snimek-obrazovky-2020-10-19-133910-1024x770.png" alt="" class="wp-image-4483" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/Snimek-obrazovky-2020-10-19-133910-1024x770.png 1024w, __GHOST_URL__ /content/images/wordpress/2020/10/Snimek-obrazovky-2020-10-19-133910-300x226.png 300w, __GHOST_URL__ /content/images/wordpress/2020/10/Snimek-obrazovky-2020-10-19-133910-768x578.png 768w, __GHOST_URL__ /content/images/wordpress/2020/10/Snimek-obrazovky-2020-10-19-133910.png 1166w" sizes="(max-width: 1024px) 100vw, 1024px"></a></figure>

**KROK 2: Podívejte se, v jakém formátu je diskový oddíl**

Další, co je třeba ověřit je, jestli je váš systém nainstalován na oddílu zformátovaném jako GUID Table ( **GPT** ).

K ověření opět použijeme zkratku **Win + R** a do okna „Spustit“ napište „ **diskmgmt.msc** “ a potvrďte klávesou **Enter** pro zobrazení správy disků.

<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="399" height="206" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/diskmgmt.png" alt="" class="wp-image-4484" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/diskmgmt.png 399w, __GHOST_URL__ /content/images/wordpress/2020/10/diskmgmt-300x155.png 300w" sizes="(max-width: 399px) 100vw, 399px"></figure>

Ve správě disků klikněte druhým tlačítkem na systémový disk, vyberte **Vlastnosti** a v záložce **Svazky** ověřte, zda styl oddílu je skutečně **GPT**.

<figure class="wp-block-image size-large"><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/diskpart.png"><img decoding="async" loading="lazy" width="1024" height="752" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/diskpart-1024x752.png" alt="" class="wp-image-4485" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/diskpart-1024x752.png 1024w, __GHOST_URL__ /content/images/wordpress/2020/10/diskpart-300x220.png 300w, __GHOST_URL__ /content/images/wordpress/2020/10/diskpart-768x564.png 768w, __GHOST_URL__ /content/images/wordpress/2020/10/diskpart.png 1151w" sizes="(max-width: 1024px) 100vw, 1024px"></a></figure>

**KROK 3: Zabraňte automatickému restartu**

Proto, aby následující operace proběhly korektně je třeba zabránit automatickému restartovaní, takže opět použijeme zkratku **Win + R** a do okna „Spustit“ napište „ **sysdm.cpl** “ a potvrďte klávesou **Enter** pro zobrazení vlastností systému.

<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="399" height="206" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/sysdm.png" alt="" class="wp-image-4489" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/sysdm.png 399w, __GHOST_URL__ /content/images/wordpress/2020/10/sysdm-300x155.png 300w" sizes="(max-width: 399px) 100vw, 399px"></figure>

Ve vlastnostech systému zvolte záložku **Upřesnit** a v sekci Spouštění a zotavení systému možnost **Nastavení…** Následně v sekci Selhání systému deaktivujte možnost **Automatického restartu**.

<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="476" height="557" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/zotaveni.png" alt="" class="wp-image-4490" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/zotaveni.png 476w, __GHOST_URL__ /content/images/wordpress/2020/10/zotaveni-256x300.png 256w" sizes="(max-width: 476px) 100vw, 476px"></figure>

**KROK 4: Stáhněte si program na úpravu diskových oddílů**

Já jsem zvolil AOMEI Partition Assistant, protože je ve verzi Professional zdarma [k vyzkoušení](http://www2.aomeisoftware.com/download/pa/PAssist_ProDemo.exe)a to pro náš účel plně postačuje.

- Program spustíme a v hlavním okně u našeho systémového disku vybereme možnost **Convert to MBR Disk**.
<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="880" height="660" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/convert-data-disk-to-mbr-1.png" alt="" class="wp-image-4488" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/convert-data-disk-to-mbr-1.png 880w, __GHOST_URL__ /content/images/wordpress/2020/10/convert-data-disk-to-mbr-1-300x225.png 300w, __GHOST_URL__ /content/images/wordpress/2020/10/convert-data-disk-to-mbr-1-768x576.png 768w" sizes="(max-width: 880px) 100vw, 880px"></figure>
- Následně potvrďte **OK** a nahoře spusťte proces tlačítkem **Apply**. Počítač vás vyzve k restartování systému a při načítání provede převedení diskového oddílu.

**KROK 5: Změna způsobu bootování na Legacy**

Nyní můžete v BIOSu změnit způsob bootování z UEFI na Legacy, uložit a nechat zařízení nabootovat až do systému.

**Pozn.** : Je také dobré překontrolovat pořadí bootování tak, aby váš disk byl v seznamu na prvním místě.

<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="646" height="480" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/mblegacybootV6.png" alt="" class="wp-image-4492" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/mblegacybootV6.png 646w, __GHOST_URL__ /content/images/wordpress/2020/10/mblegacybootV6-300x223.png 300w" sizes="(max-width: 646px) 100vw, 646px"></figure>

**KROK 6: Kontrola a navrácení původních dočasných úprav**

- Nyní již stačí jen zkontrolovat, že vaše deska již neoperuje v UEFI módu a to tak, že replikujete postup z prvního kroku – v řádku **režim systému BIOS** by již mělo být „ **Starší verze** „.
<figure class="wp-block-image size-large"><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/Snimek-obrazovky-2020-10-19-135809.png"><img decoding="async" loading="lazy" width="1024" height="770" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/Snimek-obrazovky-2020-10-19-135809-1024x770.png" alt="" class="wp-image-4493" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/Snimek-obrazovky-2020-10-19-135809-1024x770.png 1024w, __GHOST_URL__ /content/images/wordpress/2020/10/Snimek-obrazovky-2020-10-19-135809-300x226.png 300w, __GHOST_URL__ /content/images/wordpress/2020/10/Snimek-obrazovky-2020-10-19-135809-768x578.png 768w, __GHOST_URL__ /content/images/wordpress/2020/10/Snimek-obrazovky-2020-10-19-135809.png 1166w" sizes="(max-width: 1024px) 100vw, 1024px"></a></figure>

Následně je také dobré vrátit zpět nastavení automatického restartování při selhání systému. Toho docílíte replikováním postupu z třetího kroku.

<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="476" height="557" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/10/zotaveni2.png" alt="" class="wp-image-4494" srcset=" __GHOST_URL__ /content/images/wordpress/2020/10/zotaveni2.png 476w, __GHOST_URL__ /content/images/wordpress/2020/10/zotaveni2-256x300.png 256w" sizes="(max-width: 476px) 100vw, 476px"></figure>

To by mělo být vše. 🙂

<!--kg-card-end: html-->