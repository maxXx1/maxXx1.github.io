---
title: "Zranitelnost rom-0 na vlastní kůži"
date: "2014-06-13"
tags: 
  - "rom-0"
  - "sit"
  - "td-w8901gb"
  - "tp-link"
coverImage: "tplink-750x410-1.jpg"
---

Určitě jste na internetu zachytili zprávu o tom, že až 1,5 milionu routerů v českých domácnostech trpí kritickou závadou rom-0, která umožňuje útočníkovi bez zadání hesla stáhnout kompletní konfigurační soubor vašeho routeru včetně přístupových údajů a hesel. Jeden z těchto kousků se mi právě dostal do ruky!

<!--more-->

Tato chyba je velmi kritická, protože zjednodušeně stačí za adresu vašeho routeru dodat /rom-0 a router bez dotazu na přístupové údaje začne stahovat konfigurační soubor, podobný tomu ve kterém zálohujete nastavení vašeho routeru. V tomto souboru je samozřejmě úplně všechno včetně přístupových údajů, takže útočník po vytažení přihlašovacích údajů skrz [dekompresor](http://198.61.167.113/zynos/ "dekompresor") z tohoto souboru získá plnou kontrolu nad vašim routerem naprosto čistým způsobem a to tak, že se prostě přihlásí.

![](images/rom-0.png)

### Ty routery se stále používají?

Problém je v tom, že tyto routery jsou založené na firmware ZyNOS, který forma ZyXEL představila někdy kolem roku 2008. Tento systém si s sebou nesl mnoho chyb a nedokonalostí, které se postupně opravovali, firmware není založen na žádném linuxu ani \*BSD, ale byl účelově vytvořen pro potřeby levných/méně výkonných routerů. Kladl jsem si otázku jak je tedy možné, že se tento systém respektive jeho chyby objevují na routerech značky TP-Link a odpověď byla prostá, je prostě všude i tam kde se o tom neví.

Člověk, který se routery a jejich bezpečností zabývá celý život mi vysvětlil, že tak jak byl jednou systém napsán tak se používal v širokém spektru routerů od různých nejčastěji Asijských výrobců. Systém se postupně opravoval tzv. za běhu, systém se tudíž s největší pravděpodobností nasazuje do routerů dodnes a je stále vyvíjen. Na některé routery se ale bohužel již nedostalo, tak jako v případě ADSL routeru TP-Link TD-W8901GB revize 3.4, který je na stránkách výrobce označený jako "End-of-Life Product" tudíž se u něho již žádné opravy nedočkáme. A to se internetem proslýchá, že útočníci o této chybě ví minimálně od roku 2010 a v roce 2011 na ni dokonce nějaký odborník veřejně poukázal, to tento router ještě nebyl mimo podporu, ale výrobce se o to nejspíše nezajímal.

Přesně tohle tvrdí i oficiální vyjádření firem jako je ZyXEL či TP-Link, ujišťují zákazníky o tom, že na nových zařízeních se tato chyba již neprojevuje a za ty staré neberou žádnou zodpovědnost. Hm mají asi jiné představy o životnosti routeru v českých domácnostech. Asi něco ve smyslu 2 roky a pak koupit nový, ale toho se v Česku budou marně dovolávat když ty nejprodávanější routery byly a jsou právě ty nejlevnější, které měli sporadickou podporu již po dobu své životnosti.

### V čem je tedy ten problém?

Kdyby router byl v klasické domácnosti bez veřejné IP adresy (skrytý za NATem), jak je většina bezdrátových přípojek v ČR řešena, tak by se toho až tolik nedělo, protože by útočník nejdříve musel být v dosahu bezdrátového signálu, proniknout do sítě. O složitosti tohoto kroku by jsme mohli dlouze diskutovat, protože jsem již viděl tolik nezabezpečených WIFI sítí či "zabezpečených" heslem 1234567...

Ale tento problém postihuje také ADSL routery, které mají vždy veřejnou IP adresu a co víc ty levné TP-Linky hromadně nabízeli své doby zákazníkům snad všichni menší poskytovatelé připojení do nájmu či vlastnictví. A v případě těch větších poskytovatelů jako je například O2 a jejich FREE NET bylo v nabídce pouze Huawei ADSL2+ (či VDSL), které touto chybou trpí v některých HW revizích také.

### Reálný případ!

> Zákazník mi dnes přinesl výše popsaný TP-Link, který u nás zakoupil zhruba před třemi lety se slovy: "Asi už to nebude v záruce. Po celou dobu fungoval perfektně, ale teď náš přihlásí pouze na Skype, ale webové stránky prostě nefungují" Z tohoto popisu se dá snadno vydedukovat, že je problém s DNS serverem, takže první co, tak jsem router resetoval, čímž bych měl nastavení DNS uvést do normálu. To by však nesměl být router již infikován.

### Jak jsem to poznal?

Ani po resetu nastavení router nefungoval tak jak by měl. Kdyby záškodník ručně změnil DNS server, tak by se to tímto anulovalo a pak mě práskla do očí zajímavá věc. Další možností bylo nahrát do routeru nejnovější dostupný firmware. Ze stránek výrobce jsem vyčetl že se jedná o sestavení 100820 (který nemůže být downgradován) a v routeru byl aktuálně nahrán build 100830, který dle stránek výrobce prostě neexistuje. Takže moje teorie je taková, že útočník po získání přístupu k routeru přehrál firmware na svoji upravenou verzi, která má DNS nastaveny nějakým způsobem napevno.

![](images/rom-01.png)

![](images/rom-02.png)

### Co tím útočník získá?

Změnou DNS vás útoční bez povšimnutí může nasměrovat na vlastní stránky, které budou vypadat například naprosto identicky jako vaše přihlašovací stránka do internetového bankovnictví a tam vyčkávat na zadání vašeho jména a hesla... Co se bude dít dál snad nemusím dlouze rozvádět....

### Závěrem

Tato bezpečnostní závada je alarmující hlavně z toho důvodu, že je tak kritická a přitom tak triviální, že ji zvládne zneužít i cvičená opice resp. programovaný automat. V případě jiných v minulosti objevených chyb by bylo vždy jednodušší vás  unést i s vaším routerem a máchat vám hlavu v kýblu s vodou prostě tak dlouho dokud si na heslo nevzpomenete... Tady je tomu bohužel jinak, protože reálný útok by byl jen o něco málo složitější než výše popsané postupy na zjištění zranitelnosti...[](http://old.maxxx.cz/wp-content/uploads/2014/06/td-w8901g.jpg)
