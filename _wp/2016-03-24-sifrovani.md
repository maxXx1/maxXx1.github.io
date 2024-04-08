---
title: "Šifrování"
date: "2016-03-24"
categories: 
  - "nezarazene"
tags: 
  - "android"
  - "nezarazene"
  - "sirovani"
  - "whatsapp"
coverImage: "Encryption-1.jpg"
---

Po nedávných útocích se znovu roztočila diskuze okolo šifrování. Na jednu stranu chápu, že by se proti zločinu mělo využít pokud možno všech dostupných prostředků, na druhou stranu, ale odmítám odesílat úřadům stále [více a více informací](http://www.lupa.cz/clanky/eu-chce-po-utocich-v-bruselu-vic-dat-od-online-firem-a-operatoru/) o mně a mém chování nejenom v rámci internetu.

Nikdy mi nevadilo to, že online služby shromažďují za účelem bezpečnosti nezbytné informace (ať mají o mně v CIA třeba celý šanon informací a čtou si ho večer před spaním), protože já nemám co skrývat. Otázkou ale zůstává, co naše bezpečnost. Já vždy dbal na to, aby o mně byly dostupné pouze ty informace, které vědomě zveřejním a k mým citlivým datům se v tom nejhorším možném případě dostaly maximálně tajné služby, nikoliv však "Franta od vedle".

Téma šifrování v souvislosti se sporem [Apple vs. FBI](http://techcrunch.com/tag/apple-vs-fbi/) nakousl i John Oliver ve své show Last Week Tonight. Toto video doporučuji pustit pro lepší uvedení do problematiky.

https://www.youtube.com/embed/zsjZ2r9Ygzw

**S českými titulky jej naleznete [zde](http://www.videacesky.cz/ostatni-zabavna-videa/john-oliver-sifrovani).**

Ve videu zmínil jednu podstatnou informaci a to je ta, že pokud někomu na vlastním soukromí záleží, tak si cestu k vyššímu zabezpečení vždy najde např. použitím specializovaných aplikací a služeb. Některé z těchto služeb a aplikací bych vám chtěl v rychlosti představit.

### Email

Klasický email jakožto službu můžete zabezpečit např. a to především použitím dvoufázového ověření a silného hesla. Tím ale službu zabezpečíte před vnikem útočníka (nebo před sebou samotným). Pokud chcete mít jistotu, že email nepůjde odposlechnout během komunikace nebo samotným provozovatelem služby, tak byste se měli poohlédnout po službách nabízejících end-to-end šifrování, které způsobí to, že ani samotný provozovatel neuvidí co má na svých serverech uloženo. Zde je situace jednoduchá, protože z emailu pošlete zprávu komukoliv a kdokoliv může kontaktovat vás, proto bych doporučil dvě nejznámější služby [Tutanota](https://tutanota.com/cz/) (Německo) a [ProtonMail](https://protonmail.com/) (Švýcarsko). Není mezi nimi mnoho rozdílů. Obě nabízí klasický webmail i mobilní aplikace. /pozn. Tutanota je téměř kompletně lokalizovaná do češtiny.

### Chat a IM komunikace

Zde platí více méně to samé jako u emailu, ale situace je o poznání složitější, protože potřebujete komunikovat skrze stejnou službu jako váš protějšek. Většina služeb staví na základech protokolu [Jabber/XMPP](https://cs.wikipedia.org/wiki/Extensible_Messaging_and_Presence_Protocol) což byl v minulosti první velmi populární protokol, masivně využívaný ke komunikaci (pamatujeme ICQ?). Nejenom, že lze v případě čistého Jabberu vynutit šifrování, ale díky decentralizaci serverů může být služba i naprosto anonymní. Jenže ji dnes již skoro nikdo nepoužívá ve své čisté formě a vznikají specializované uzavřené protokoly. Např. [Google Jabber přetransformoval do podoby Hangouts](http://old.maxxx.cz/2016/02/10/jabber-a-google-talk/). Proto se podíváme na ty modernější služby.

Nejrozšířenější a dle mého názoru nejvíce uživatelsky přívětivá služba je [WhatsApp](https://www.whatsapp.com/?l=cs), ta sice již od roku 2014 patří Facebooku, který za ni zaplatil 16 miliard dolarů, ale na rozdíl od FB Messangeru využívá šifrování. Kvůli tomu, že se do služby nemohla dostat ani policie byl dokonce v Brazílii [zatčen jeden z vysokých managerů](http://www.zive.cz/bleskovky/spor-o-sifrovani-pokracuje-americkemu-ministerstvu-spravedlnosti-se-nelibi-whatsapp/sc-4-a-181719/default.aspx) Facebooku.

V Brazílii si tak hledí svého soukromí, že když postihl službu WhatsApp masivní výpadek, tak se dostala do popředí další služba, na kterou bych chtěl upozornit a tou je [Telegram](https://telegram.org/). Tato služba stejně jako WA využívá jako unikátní identifikátor tel. číslo a přenos i obsah je šifrovaný.

### Cloudové (internetové) úložiště

Pokud potřebujete poslat fotku či písničku, dá se k tomu využít emailu či IM komunikátoru i v rámci výše zmíněných služeb. Když však potřebujete poslat či uskladnit objemnější soubor pro jednu nebo více osob, tak byste se měli poohlédnout po nějakém úložišti.

V roce 2012 po [fiasku s megauploadem](https://cs.wikipedia.org/wiki/Megaupload) (obdoba našeho ulož.to) spouští Kim Dotcom z Nového Zélandu úložiště [Mega](https://mega.co.nz/). Toto úložiště je šifrované nejenom proto, aby ochránilo vaše soubory, ale hlavně proto, aby provozovatelé služby nevěděli co za obsah se na jejich serverech nachází a tím se vyvázali z případné odpovědnosti za porušování autorských práv.

Samozřejmě i zde je z čeho vybírat, ale ostatní služby jsou (hlavně z důvodu kontroverze Mega) zaměřeny spíše na zálohování a z velké části jsou to služby placené. Jedna z nejpopulárnějších je [SpiderOak](https://spideroak.com/).

### Soubory a složky

Jedno ze základních pravidel bezpečnosti říká, že pokud nechcete, aby se něco dostalo do nesprávných rukou, tak to nikam neposílejte. Pro případy lokálního uskladnění je tu dnes již legendární program [TrueCrypt](https://www.grc.com/misc/truecrypt/truecrypt.htm), který umožňuje vytvořit virtuální logickou diskovou jednotku uvnitř souboru a připojit ji jako reálný disk. Dále lze zašifrovat část HDD, FDD, USB paměť atd. Tento program vyvíjel neznámý programátor, který jeho vývoj z neznámých důvodů 28. května 2014 ukončil. [Spekuluje se](http://www.root.cz/n/truecrypt/) o tom, že se program taktéž nelíbil vládním složkám. Jeho nástupcem je [VeraCrypt](https://veracrypt.codeplex.com/), který by měl opravovat jeho chyby a disponovat stejnou mírou zabezpečení (které je mimochodem jedno z nejvyšších, kterého lze v daných podmínkách dosáhnout).

### Celé lokální úložiště vč. systému

To, že iPhone disponuje šifrováním již víme. Některé z vás to možná překvapí, ale i váš telefon s Androidem disponuje šifrováním. Naleznete ho v "Nastavení - Zabezpečení - Šifrování úložiště" (možnosti se liší v závislosti na konkrétním modelu a verzi androidu). Toto nastavení způsobí zašifrování souborů a složek uložených v telefonu či na paměťové kartě. Bohužel krutou daní za tuto formu zabezpečení je [rychlost odezvy zařízení](http://samsungmania.mobilmania.cz/clanky/android-50-sifruje-za-bezpeci-ale-zaplatite-rychlosti/sc-309-a-1329060?mobiredir=0) a výdrž baterie při aktivním používání.

U přenosných počítačů si šifrování řeší každý výrobce sám a po svém. Avšak těmito službami vybavuje zpravidla pouze dražší businessové notebooky. Např. u výrobce HP se služba jmenuje [Protect Tools](http://h10032.www1.hp.com/ctg/Manual/c02754330) a nachází se v sériích [ProBook](http://www.hpmarket.cz/product.asp?ccode=notebooky_probook), [EliteBook](http://www.hpmarket.cz/product.asp?ccode=hp_elitebook), [ZBook](http://www.hpmarket.cz/product.asp?ccode=hp-zbook).

U stolních počítačů lze využít opět programů True/VeraCrypt, které umí šifrovat celý disk vč. operačního systému. A na závěr musím zmínit, že i samotný [Windows se umí zašifrovat](http://windows.microsoft.com/cs-cz/windows-8/using-device-encryption).

### Ostatní

Pravdou je, že v dnešní době se dá již zaheslovat popř. zašifrovat úplně všechno. Od hovorů až po kompletní zařízení. Je vhodné vybírat si služby bezpečné, ale je naprostá hloupost používat kombinaci všech dostupných prostředků. (např. nástroj Protect Tools vždy vypínám - umí udělat více škody než užitku). Největším bezpečnostním opatřením je ale stále zdravý selský rozum.

 

A tím se opět dostáváme na začátek k diskuzi jestli šifrovat či nikoliv. Je to obousečná zbraň, která na jednu stranu chrání naše soukromí a na druhou stranu může být zneužita k nekalostem. Já osobně v této otázce zaujímám neutrální postoj. Jsem pro to, aby byl co možná nejefektivněji vystopovatelný útočník, dealer či násilník, ale odmítám obrazně řečeno chodit nahý, jen proto abych dokázal, že nejsem ozbrojen.
