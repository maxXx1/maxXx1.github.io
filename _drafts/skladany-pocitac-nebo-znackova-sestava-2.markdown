---
layout: post
title: Skládaný počítač nebo "značková" sestava?!
tags:
- nezarazene
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Před nákupem nového počítače by se měl každý zamyslet jestli si chce koupit hotovou značkovou sestavu, nebo si nechat počítač sestavit z vybraných komponent. Samozřejmě nejlepší možný scénář je ten, že někdo z vašeho okolí či drobná firma sestavu dle svého nejlepšího vědomí a svědomí navrhne a sestaví. I když sestavu v dnešní době dokáže sestavit i cvičená opice, stále bych tento krok nedoporučoval domácím kutilům, kteří s těmito věcmi nemají byť minimální zkušenosti. Sestavování počítače s sebou nese mnoho skrytých hrozeb. Jako například to, že pod desku se musí dát distanční podložky (pokud case nemá v plechu prolis) jinak se základní deska dotkne plechu a zkratuje nebo to, že termální pasta se nanáší opravdu v tenkých vrstvách pouze na chip a nikam jinam, u zapojení front (předního) panelu do základní desky se mnohdy zapotí i zkušenější.

<!--more-->

Proč tohle všechno absolvovat či platit firmě nebo známému za sestavení počítače, když tu máme již připravené „značkové“ sestavy, které stačí doma připojit a začít pracovat?

**1. Rádoby značka, plomby, silikon, záruka…**  
V prvním bodě dám stranou velké světové výrobce jako jsou Acer, HP či Dell a zamířím do českých luhů a hájů. V česku jsou například velmi populární sestavy značky Barbone a HAL3000. Tyto sestavy jsou (díky bohu) na rozdíl od světových výrobců skládány se standardních komponent, které lze zakoupit jednotlivě tudíž i lehce obměnit. Avšak tyto sestavy jsou zaplombovány a po dobu dvouleté záruky nebudete moci do útrob sestavy zasáhnout, tudíž pokud se cokoliv porouchá, budete muset počítač (jako celek) odeslat&nbsp;do záručního servisu, který má zpravidla 30 dní na vyřízení reklamace.&nbsp;Dva roky uplynou jako voda a&nbsp;při následném&nbsp;vylepšení či opravě zjistíte, že váš HAL3000 byl vlastně jen klasická sestava se zatavenými vnitřními konektory do silikonu&nbsp;(z důvodů zabránění uvolnění kabelu), které se sakra&nbsp;blbě vytahují. A že dva roky byl vlastně takový podfuk, protože některé komponenty mají samy o sobě záruku delší… Namátkou kvalitní zdroj – záruka 3 roky, ventilátory až 6 let.

&nbsp;

&nbsp;

**2. Atypické komponenty**

V prvním bodu jsem zmínil svatou trojici ve značkových počítačích. Když&nbsp;slyším ve spojení s&nbsp;desktopovým PC značku HP, Acer nebo&nbsp;Dell okamžitě se mi vybaví vše popsané v prvním bodu a k tomu&nbsp;ještě navíc atypické komponenty. Pro tyto výrobce jsou&nbsp;case, zdroje, ventilátory&nbsp;a hlavně základní desky dělány zvlášť. Jsou povětšinou původem&nbsp;od výrobců, kteří vyrábí převážně&nbsp;pro enterprise segment (např. Foxcon)&nbsp;či si daní výrobci některé komponenty dělají sami. Ani jedno ani druhé rozhodně není výhra, protože pokud vám&nbsp;po uplynutí záruky v počítači odejde některý z atypických komponentů, tak neuděláte nic. Tyto komponenty jdou ve většině případů sehnat jako speciální náhradní díl, což je velmi drahý špás, protože vám tím výrobce jasně naznačí, že levněji by vás vyšlo si zaplatit prodloužení záruky o nějaký ten rok. Pokud se bude jednat o několik let starou sestavu, tak je pro vás jedinou možností nakupit tyto díly přes eBay bez další záruky. Několik příkladů z praxe: Pokud v počítači Acer Aspire odejde základní deska, jinou do ní nedostanete, protože konektor front panelu je slisován dohromady v rozložení pro desku Foxcon, která se ve volném prodeji nikdy neobjevila. Pokud budete chtít řešit hlučné chlazení u počítačů Dell, tak přeji příjemnou zábavu, chlazení je spjato s celkovým návrhem case. Nejlepší je použití atypických zdrojů, různých velikostí či tvarů….[![](http://192.168.20.2/wordpress/wp-content/uploads/2014/04/optiplex1-271x300.jpg)](http://192.168.20.2/wordpress/wp-content/uploads/2014/04/optiplex1.jpg)

&nbsp;

**3.&nbsp;BIOS**  
Již jsem zmínil osazení řekněme „speciálními“&nbsp;základními deskami. S tím se velmi úzce pojí BIOS, který je vždy navržen pro konkrétní model stejně jako u notebooků a od toho se odvíjí i jeho podpora a omezení. Tyto BIOSy jsou většinou aktualizovány pouze po tu dobu po kterou zákazníci platí prodlouženou záruku u daných produktů. Samozřejmě v průměru&nbsp;maximálně 4 roky což platí i o ovladačích k HW. BIOS se od toho notebookového liší jen velmi málo. Většina podporuje rozšířené možnosti zabezpečení jako je například kontrola jestli někdo neoprávněný neotevřel case, v takovém případě se počítač vypne a bez zadání hesla již nespustí. nebo tyto BIOSy umí varovat při změně jakýchkoliv komponent nebo chránit počítač heslem (či čipovou kartou) již na úrovni POSTu. Kde že je ta zrada? Většinu z těchto věcí doma vůbec nepotřebujete ba naopak. BIOS může zabránit rozšíření paměti RAM jen proto, že se snažíte paměť rozšířit jiným modulem než modulem od daného výrobce. Nedovolí vám zkontrolovat nastavení frekvence paměti či (v některých případech) i&nbsp;to jestli&nbsp;disk běží&nbsp;v módu AHCI či IDE Native. Na nějaké ladění výkonu (taktování) můžete rovnou zapomenout.

![](http://192.168.20.2/wordpress/wp-content/uploads/2014/04/c022587861.gif)  
**4. Operační systém**

A konečně se dostáváme na povrch. U operačních systémů ve značkových sestavách platí to stejné jako u těch v noteboocích. Systém bývá většinou tzv. předinstalován to znamená, že po prvním zapnutí se vás zeptá na jméno, heslo, časovou zónu atd. aby mohl provést doinstalaci (takže stejně není hned připraven k práci). Na co se vás však určitě nezeptá je to jestli chcete či nechcete hromadu předinstalovaných programů (bloatware), které budou ve vašem počítači nainstalovány hned po prvním spuštění. Tyto programy jsou z menší části ultility, které jsou k ničemu a z větší části programy v časově omezených verzích, které po vypršení budou žádat, aby jste si je koupili či je odstranili. Tyto programy váš nově nainstalovaný systém velmi zpomalují, ale výrobce dostal za tuto nepříjemnou reklamu zaplaceno tolik, že mohl i výslednou sestavu zlevnit o pár korun beze změny marže. Mno já osobně bych si raději připlatil pár korun za to, že dostanu opravdu čistý systém.

<figure id="attachment_15" aria-describedby="caption-attachment-15" style="width: 300px" class="wp-caption aligncenter"><a href="http://www.maxxx.cz/wp-content/uploads/2014/04/crapwaredesktop-640x480.jpg"><img decoding="async" loading="lazy" class="size-medium wp-image-15" src="http://www.maxxx.cz/wp-content/uploads/2014/04/crapwaredesktop-640x480-300x225.jpg" alt="Většinu předinstalovaných programů nikdy nespustíte..." width="300" height="225"></a><figcaption id="caption-attachment-15" class="wp-caption-text">Většinu předinstalovaných programů nikdy nespustíte…</figcaption></figure>

**5. Cena, podpora**  
O peníze jde vždy až v první řadě, proto je důležité si říct, že i přes to všechno nejsou značkové sestavy levnější než skládané počítače. Jasně když ke skládanému počítači připočtete něčí práci pak ano, ale tento technik je pak vždy připraven vám pomoci okamžitě, řešit reklamaci individuálně či instruovat vás o správném použití počítače. Pokud chcete pouze sestavení a dál si hodláte radit sami, tak i pro vás je tu v dnešní době nabídka jednoho (možná už dvou) českých eshopů, které nabízejí sestavení počítače s vybraných komponent zdarma. Značkové sestavy budou levnější pouze v případě kdy budu nakupovat velké množství, např. pro malou či střední firmu tam se dá sjednat v rámci partnerského programu velmi nízká cena. To však jednotlivce nezajímá, protože tuto cenu si vyjednal eshop ze kterého to kupuje… pro něj to nemá žádné plus… A aby jste se nedivily, sestavy existují i astronomicky (a také bezdůvodně) drahé, jeden příklad za všechny je Alienware. Tato značka je vlastně herní odnož Dellu a připlatíte si hlavně za prestiž a značku.

![](http://192.168.20.2/wordpress/wp-content/uploads/2014/04/desktop-alienware-x51-r2-pdp-love-design-2.jpg)

Třeba to budu já :)Tady je 5 bodů, které vám možná nepřijdou na mysl když stojíte v Datartu a díváte se na obrovskou ceduli sleva či akce… Ale určitě by jste s výhledem do budoucna s těmito body měli počítat, protože vám je možná po dvou letech od koupi připomene některý ochotný servisní technik ke kterému přijdete s porouchaným počítačem na opravu.

<!--kg-card-end: html-->