---
layout: post
title: Samsung Galaxy Mini 2 - Instalace ROM
date: '2016-12-13 10:51:06'
tags:
- android
- flash
- fw
- nezarazene
- samsung
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Dostal se mi do ruky malý Samsung Galaxy Mini 2 (GT-S6500) s klasickým boot loop problémem. Tedy, že po startu pouze zavibruje, zobrazí logo Samsung a pak se restartuje. Na tomto konkrétním kusu byl nefunkční i recovery, takže jsem přistoupil k instalaci kompletně celé ROM skrze Odin.

### Co budeme potřebovat

- **ROM** určenou k flashování skrze Odin najdete v databázi na stránkách [Sammobile.com](http://www.sammobile.com/firmwares/database/GT-S6500/). Pro stažení ROM je nutná registrace, která je zdarma a není nutno ji potvrzovat na emailu. Následně stahujte v bezplatném módu „Regular download“
- **Odin&nbsp;** je program který slouží pro nahrání ROM v surovém stavu a je vhodné stahovat jeho aktuální verzi ze stránek&nbsp;[Odindownload.com](http://Odindownload.com).
- **USB driver** který je sice postarší, ale lze jej nainstalovat i na Windows 10, za předpokladu, že vypnete vynucení podpisu ovladačů.

### Postup
<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="653" height="427" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213103326.png" alt="" class="wp-image-4334" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213103326.png 653w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213103326-300x196.png 300w" sizes="(max-width: 653px) 100vw, 653px"></figure>
1. Nainstalujte a spusťte Odin (s oprávněním správce)
2. Rozbalte vámi staženou ROM
3. Telefon pomocí tlačítek Volume – a Home (v přední části) a Power nastartujte v Download módu
4. Až uvidíte logo Samsung, tak klávesy pusťte a vstup do recovery na vyzvání potvrďte **Volume Up** tlačítkem.
5. Úspěšné připojení telefonu pomocí USB kabelu poznáte v Odin u kolonky&nbsp; **ID:COM** , který bude podbarvená žlutě nebo modře (záleží na verzi).
6. V Odin – záložce **Options** zkontrolujte zapnuté volby **Auto Reboot** a **F. Reset Time&nbsp;**
7. Nyní otevřete vámi stažený soubor ROM v sekci&nbsp; **AP** &nbsp;nebo **&nbsp;PDA** (opět záleží na verzi)  
8. Nyní už jen klikněte na tlačítko **Start&nbsp;** a počkejte dokud se proces instalace nedokončí.[![](https://www.maxxx.cz/wp-content/uploads/2016/12/snip_20161213101108.png)](https://www.maxxx.cz/wp-content/uploads/2016/12/snip_20161213101108.png)[![](https://www.maxxx.cz/wp-content/uploads/2016/12/snip_20161213101117.png)](https://www.maxxx.cz/wp-content/uploads/2016/12/snip_20161213101117.png)[![](https://www.maxxx.cz/wp-content/uploads/2016/12/snip_20161213101219.png)](https://www.maxxx.cz/wp-content/uploads/2016/12/snip_20161213101219.png)[![](https://www.maxxx.cz/wp-content/uploads/2016/12/snip_20161213101230.png)](https://www.maxxx.cz/wp-content/uploads/2016/12/snip_20161213101230.png)
9. Telefon se automaticky restartuje a můžete ho odpojit od PC.
<figure class="is-layout-flex wp-block-gallery-3 wp-block-gallery columns-1 is-cropped"><ul class="blocks-gallery-grid">
<li class="blocks-gallery-item"><figure><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213100548.png"><img decoding="async" loading="lazy" width="876" height="627" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213100548.png" alt="" data-id="4335" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213100548.png" data-link="https://maxxx.cz/?attachment_id=4335" class="wp-image-4335" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213100548.png 876w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213100548-300x215.png 300w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213100548-768x550.png 768w" sizes="(max-width: 876px) 100vw, 876px"></a></figure></li>
<li class="blocks-gallery-item"><figure><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101108.png"><img decoding="async" loading="lazy" width="857" height="164" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101108.png" alt="" data-id="4336" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101108.png" data-link="https://maxxx.cz/?attachment_id=4336" class="wp-image-4336" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101108.png 857w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101108-300x57.png 300w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101108-768x147.png 768w" sizes="(max-width: 857px) 100vw, 857px"></a></figure></li>
<li class="blocks-gallery-item"><figure><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101117.png"><img decoding="async" loading="lazy" width="857" height="164" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101117.png" alt="" data-id="4337" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101117.png" data-link="https://maxxx.cz/?attachment_id=4337" class="wp-image-4337" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101117.png 857w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101117-300x57.png 300w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101117-768x147.png 768w" sizes="(max-width: 857px) 100vw, 857px"></a></figure></li>
<li class="blocks-gallery-item"><figure><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101219.png"><img decoding="async" loading="lazy" width="857" height="164" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101219.png" alt="" data-id="4338" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101219.png" data-link="https://maxxx.cz/?attachment_id=4338" class="wp-image-4338" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101219.png 857w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101219-300x57.png 300w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101219-768x147.png 768w" sizes="(max-width: 857px) 100vw, 857px"></a></figure></li>
<li class="blocks-gallery-item"><figure><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101230.png"><img decoding="async" loading="lazy" width="857" height="164" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101230.png" alt="" data-id="4339" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101230.png" data-link="https://maxxx.cz/?attachment_id=4339" class="wp-image-4339" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101230.png 857w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101230-300x57.png 300w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101230-768x147.png 768w" sizes="(max-width: 857px) 100vw, 857px"></a></figure></li>
<li class="blocks-gallery-item"><figure><a href="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101240.png"><img decoding="async" loading="lazy" width="857" height="164" src="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101240.png" alt="" data-id="4340" data-full-url="http://192.168.20.2/wordpress/wp-content/uploads/2020/09/snip_20161213101240.png" data-link="https://maxxx.cz/?attachment_id=4340" class="wp-image-4340" srcset=" __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101240.png 857w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101240-300x57.png 300w, __GHOST_URL__ /content/images/wordpress/2020/09/snip_20161213101240-768x147.png 768w" sizes="(max-width: 857px) 100vw, 857px"></a></figure></li>
</ul></figure><!--kg-card-end: html-->