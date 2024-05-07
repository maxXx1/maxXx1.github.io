---
title: "Jak otestovat pevný disk ?"
date: "2017-06-01"
categories: 
  - "Hardware"
tags: 
  - "HDD"
image: 
  path: "/img/2017-06-01-otestovat-pevny-disk-hdd/repair-hdd.jpg"
  alt: "Testování disků"
---

Pevný disk je jedna z posledních mechanických součástek v počítačích a je to jedna z nejdůležitějších součástek, protože právě na pevném disku jsou fyzicky uložené všechny vaše data. Paradoxně se ale jedná o jednu z nejporuchovějších věcí. Disk (ostatně jako každá součástka) má svoji životnost. Bohužel právě na pevném disku jsou uloženy v mnoha případech fotky vašich dětí, které už se nikdy nezmenší (ty děti ofc.), fotky z dovolené v Dubaji (kam už znova nepojedete) a nezřídka také např. certifikát pro přístup do internetového bankovnictví... bolelo by vás u srdce, kdyby jste o tyto věci z minuty na minutu přišli?

## Odcházející disk

Disk může odejít hned několika způsoby, ale tak či tak se z něj již nikomu nemusí podařit vaše data získat zpět. Jako doporučení tedy berte občasný test pevného disku. Může se stát, že odejde během pár hodin, nebo postupně v rámci několika měsíců, kdy se bude zpomalovat a nepůjdou Vám otevřít některé složky.

## Záloha

Průběžně (!!!) zálohovat data o které nechcete přijít není doporučení, ale je to nutnost! Záloha spočívá v prostém překopírování (nikoliv přesunutí!) na jiné úložiště (externí pevný disk, jiný fyzický disk, flashdisk, optické médium, do cloudu). Nehledejte v tom prosím žádnou vědu. Podstatou zálohování, je aby data byli vždy na dvou či více místech. Kopírovat umíme všichni.

## "Čím testovat?"

Většinou se doporučuje použít na kontrolu disku utilitu od výrobce, ten totiž nejlépe zná své výrobky a proto dokáže napsat program "šitý na míru" konkrétnímu výrobku. Ale použití programu výrobce by vyžadovalo zjištění přesného typu pevného disku popř. alespoň výrobce. Já bych ale doporučil použít dva nejznámější programy, které umí spolupracovat s disky všech výrobců bez rozdílu. Jeden na rychlý test a ten druhý na podrobný hloubkový průzkum.

## Rychlý test - Crystal Disk Info

Na rychlý test bych doporučil [Crystal Disk Info](https://crystalmark.info/download/index-e.html#CrystalDiskInfo) - tento prográmek je v češtině a ihned po zapnutí vás bude přehledně informovat, zdali je disk v pořádku.

![crystal](/img/2017-06-01-otestovat-pevny-disk-hdd/crystal.png)

- "Stav disku" modrý, tedy s nápisem "dobrý", disk by měl být v pořádku, nemá pravděpodobně vadné nebo přemapované sektory.
- Pokud je žlutý, je třeba začít shánět nový disk. Takový disk může jet klidně půl roku, ale můžete přijít o některá nebo také všechna data.
- Červený rámeček už je hodně zlý. Pokud disk ještě jede, stahujte data okamžitě, dokud to jde. Protože v tomto stavu můžete být rádi, že váš disk ještě funguje.

## Hloubkový test - HD Tune

Na hloubkový test bych doporučil starší program [HDTune](https://www.hdtune.com/download.html), naprosto postačí jeho verze zdarma (v 2.55 z roku 2008). Tento program proklepne váš disk po více stránkách.

**Benchmark** - Po kliknutí na "Start" nejdřív dojde k testu rychlosti (na pc nic v tu chvíli nedělejte, čtení a zápis by byl ovlivněn). Poté se začnou objevovat žluté tečky, což je test konzistence disku. Tečky by měly tvořit pruh, neměly by být rozprostřeny přes celé okno. Také spojnice grafu při měření rychlosti by neměla být příliš "rozběhaná" a rychlost by měla odpovídat typu disku, který testujete. Starší ATA disky jsou pomalejší než disky SATA, SSD disk je výrazně nejrychlejší.

![hdtune](/img/2017-06-01-otestovat-pevny-disk-hdd/hdtune.png)

**Info** - Zde naleznete výpis parametrů disku. V dnešní době již této záložce nemusíte přikládat valného významu. Program je starší a tudíž nemusí korektně zobrazit všechny parametry. Ale určitě se to hodí pokud například chcete zjistit verzi firmware vašeho disku.

**Health** - V této záložce se vám zobrazí výpis S. M. A. R. T. (Self Monitoring Analysis and Reporting Technology). To je technologie sloužící k monitorování stavu vašeho disku a případném včasném odhalení vady předtím, než přijdete o všechna data. Touto technologií disponují již všechny vyráběné disky.  
Pokud se Vám v této tabulce nic nezobrazuje, pak máte pravděpodobně vypnutou tuto funkci v BIOSu. Doporučujeme mít tuto hodnotu stále zapnutou - v BIOSu v sekci ADVANCED přepněte S.M.A.R.T. do stavu ENABLE.

![hdtune2](/img/2017-06-01-otestovat-pevny-disk-hdd/hdtune2.png)

Zobrazuje-li se vám v dolní části Health Status: <span style="color:green">**Ok**</span>, pak je vše v pořádku, při <span style="color:orange">**Warnings**</span> se mějte na pozoru a je-li jedna z položek <span style="color:red">**Failed**</span>, pak disk dosluhuje.

## S.M.A.R.T

- (01) Raw Read Error Rate - Určuje počet chybně přečtených dat z plotny. Chyby vznikají poměrně běžně a jsou korigovány pomocí opakovaného čtení.
- (02) Throughput Performance - celkový výkon disku. Hodnota by neměla být nižší, než hodnota Threshold.
- (03) **Spin Up Time** - čas roztočení disku z nuly do plné rychlosti. Špatná hodnota znamená, že disk má vadný motorek.
- (04) Start/Stop Count - počet startů plotny
- (05) **Reallocatd Sector Count** - Počet realokovanych sektorů. Hodnota by měla být 0, dojde-li k narůstání této hodnoty, pak je na čase disk vyměnit.
- (07) **Seek Error Rate** - počet chybných přemístění hlavičky nad plotnu. Hodnota by měla být 0, je-li vyšší, pak je disk vadný.
- (08) **Seek Time Performance** - rychlost přemísťování hlaviček. Obvykle 0, je-li hodnota vyšší, může to znamenat začínající problémy s HDD.
- (09) Power On Hours Count - počet hodin provozu disku.
- (0A) Spin Retry Count - počet opakovaných pokusů o roztočení plotny. Špatné hodnoty nemusí nutně znamenat vadný disk, např. některé Seagate disky neuměli tuto hodnotu zobrazit korektně.
- (0B) Calibration Retry Count - počet pokusů o kalibraci disku, indikuje problémy s motorkem!
- (0C) Power Cycle Count - počet zapnutí PC (není stejné jako 04, Start/Stop započítává i probouzení z úsporného módu atd.)

**Error scan** - Je diagnostika povrchu disku blok po bloku. Opět jej spustíte tlačítkem "Start" (nastavení "Quick Scan" nepoužívejte, kladný výsledek neznamená, že disk je v pořádku!). Délka tohoto testu se odvyjí od kapacity testovaného disku, ale řádově trvá desítky minut. Všechny sektory by měly být zelené. Pokud je jeden nebo více červených, má disk vadný sektor a pravděpodobně brzy odejde. Existují případy, že na disku je jeden vadný blok trvale několik let a již se nešíří, ale přesto použití takového disku považujte za riskantní.

![hdtune3](/img/2017-06-01-otestovat-pevny-disk-hdd/hdtune3.png)

Vadné sektory (nebo chcete-li bloky), lze i ručeně realokovat poté co disk vyčerpá kapacitu náhradních sektorů a zamknout pro zápis. K takovému účelu slouží například velmi šikovný DOSový program [HDAT2](https://www.hdat2.com/download_cz.html), ale použití takového disku se již považuje za velmi riskantní.

**Pokud v disku cvaká, tak test vůbec neprovádějte** - urychleně zálohujte, pokud disk ještě trochu funguje, a vyměňte ho.
