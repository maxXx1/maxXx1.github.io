---
layout: post
title: Facebook Massenger nefunguje na Windows XP ?!
tags:
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Stalo se Vám, že po spuštění Facebook Massegeru na Windows XP naskočila pouze hláška, která Vám nabízí odeslání reportu o chybě? Mě také, ale řešení je velmi jednoduché, až primitivní.  
Mám na svém netbooku čistou verzi Windows XP Home Edition bez jakýchkoliv zbytečností, avšak jsem se dnes rozhodl jednu zbytečnost nainstalovat. Facebook Massenger, který dle [oficiálních stránek](https://www.facebook.com/about/messenger)&nbsp;má Windows XP v aktualizaci SP3 podporovat. Dle citace z centra nápovědy…

<!--more-->

Jenomže po korektní instalaci jsem se dočkal pouze dialogového okna nabízející odeslání reportu o chybě.  
Někde na internetu jsem se dočetl, že v počítači musí být nainstalován Windows Live Massenger, což je samozřejmě naprostá hloupost, protože Microsoft již minulý rok avizoval definitivní ukončení této služby a integraci do Skype.

Řešení bylo tedy v chybějících knihovnách [.NET Framework](http://www.microsoft.com/cs-cz/download/details.aspx?id=21) (stahujte nejlépe přímo ze stránek Microsoft) konkrétně ve verzi 3.5, která obsahuje aktualizace .NET Framework 2.0 SP1 a 3.0 SP1. Takže stačí doinstalovat tento balík, který má zhruba 76MB a vše bude fungovat jak má i na Windows XP. Dejte však pozor na zvolenou jazykovou verzi, pro česky lokalizovaný operační systém by jste měli instalovat česky lokalizovaný balík.Minimální požadavky na systém udávané u balíku .NET Framework můžeme brát jako minimální požadavky Massengeru jako takového a jsou to:

**OS:** Windows Server 2003; Windows Server 2008; Windows Vista; Windows XP  
**Procesor:** Pentium 400 MHz nebo ekvivalentní (minimum); Pentium 1 GHz nebo ekvivalentní (doporučeno)  
**RAM:** 96 MB (minimum); 256 MB (doporučeno)  
**Pevný disk:** Může být požadováno až 500 MB volného místa  
Jednotka CD nebo DVD: Není vyžadována  
**Displej:** 800 x 600, 256 barev (minimum); 1024 x 768 High Color, 32 bitů (doporučeno)

Zůstává mi až rozum stát nad tím, že Facebook tuto důležitou věc do požadavků nenapsal. Nebo počítá s tím, že každý systém tento balík obsahuje? (i když tomu tak není)

<!--kg-card-end: html-->