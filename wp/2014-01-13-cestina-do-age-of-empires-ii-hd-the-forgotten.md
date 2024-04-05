---
title: "Čeština do Age of Empires II HD (vývoj)"
date: "2014-01-13"
tags: 
  - "age-of-empires"
  - "game"
  - "steam"
coverImage: "previewfile_474404119.jpg"
---

Tak se konečně pohnuly ledy a vedle do nedávna již fungující [slovenštiny](http://cestiny.idnes.cz/age-of-empires-ii-hd-edition-dff-/Hry.aspx?c=A130926_094127_bw-cestiny-hry_zel) se komunita na diskuzním fóru [Warforum](http://www.warforum.cz/index.php) pokusila o kompletaci českého překladu o který jsem prosil božstvo ve svých [předešlých článcích](http://maxxxcomp.blogspot.cz/search/label/Age%20of%20Empires%202%20HD). Prozatím je na světě verze "poslepovaná" ze starých češtin, které po update z listopadu 2013 nešli již nainstalovat korektně do steam verze pouhým přepsáním souborů.

<!--more-->

Na diskuzním fóru se v příslušném vláknu objevilo jak vysvětlení, proč češtiny z původní verze hry na té steamové v určité verzi přestali fungovat. Tak jednoduchý návod jak tyto staré lokalizace předělat, aby byli funkční pro aktuální verzi. Připojit k tvorbě češtiny se tedy pomocí návodu může opravdu každý. Již je na světě i první provizorní sestavení na kterém se dá dále pracovat. Pokud chcete o tvorbě lokalizace vědět více. či se chcete dokonce připojit ke komunitě pracující na překladu, tak čtěte dále...

Na vině bylo přemístění knihoven z lokalizací typu "_SteamsteamappscommonAge2HDBinenlanguage.dll_" do jednoho textovýho strings souboru "_...Binenen-language.txt_" s tím, že překlady budou realizovány přes soubor "_...Binlanguage\_base.txt_".

Dle uživatele **FJ08** se tak musí překlad udělat kompletně nový, resp. musí se urpavit a to tak, že se z \*.dll knihoven vytáhnou přeložený texty, vloží se do "_...Binlanguage\_base.txt_". A naváží se odkazy na anglický ekvivalenty v "_...Binenlanguage.txt_". Jediný co lze z češtin teď použít je překlad launcheru v "_...launcher\_reslocale.ini_" a překlad historie v "_...Historyennázev\_civilizace.txt_" (který je vytažen ze slovenské lokalizace).

Slovenská lokalizace je přeložená do posledního detailu a její tvůrce ragoval na jeden z emailů s požadavkem na úpravu slovenštiny dle výše popsaných změn takto:

> _"Dobry den._ _Planujem, avsak pracovne povinnosti ma trochu brzdia._ _Predpokladam, ze uprava by mohla byt v januari hotova."_ _Miro "Valec" Valko_  

Do českého překladu se tedy může zapojit každý, pro začátek stačí přeložit soubor "_...SteamsteamappscommonAge2HDBinenen-language.txt_", který nese hlavní anglickou lokalizaci AOEIIHD. FJ08 kontaktoval tvůrce [původní češtiny](http://www.abcgames.cz/?p=preklady_zobraz&id=127) pro základní hru a datadisk, který sice svolil k editování jeho češtiny komunitou za účelem úpravy pro steam verzi, avšak soubory z jeho lokalizace se nepodařilo dešifrovat.

Pokud však původní čeština není šifrována, lze její texty vytáhnout a upravit pro použití v aktuální steam verzi pomocí těchto jednoduchých kroků:

1. Z existující "staré" češtiny vzít soubor language.dll (Age of Kings), language\_x1.dll (The Conquerors Expansion).
2. Vytáhnout z něj české strings pomocí [Resource Hackeru](http://www.angusj.com/resourcehacker/).
3. **Použití ResHacku:** načíst language.dll - Action - Save all resources (\*.rc) - soubor pak přejmenovat na \*.txt.
4. V textovým editoru ručně, či pomocí funkce **najít a nahradit** osekat na formu: **číslo "překlad"** např. **1150 "Vyhrál jsi!"**
5. Nakonec vše vložit do výše zmíněného "_...SteamsteamappscommonAge2HDBinenen-language.txt_".

Pro účely vytvoření provizorní verze použil **FJ08** strings z nešifrovaných češtin, aby poskládal to kupy alespoň hrubý základ, který je funkční pro účely testování na aktuální steam verzi 3.1.1645 a 3.1.1645.DLC (The Forgotten).

Tyto zdrojové soubory, které stačí nakopírovat do složky s hrou (přepsat původní soubory) můžete stáhnout [zde](https://mega.co.nz/#!oJoi2CaC!T5HFQ1PXV6zMdqsVwh68rFlAfrMv9_cZwNnCKoY8G4k). K tomuto vydání však **FJ08** poznamenal:

- V češtině je vše až na část The Forgotten (nevím kde jsou strings v předešlých češtinách), historii a některé překlady v options, které jsou ve slovenčině by Valko. Jsou tam i jiné fonty, takže funguje i diakritika.
- Testováno na aktuální steam verzi 3.1.1645 a 3.1.1645.DLC (The Forgotten), tzn. mělo by fungovat i na všech předcházejících od verze 2.8.
- Pokud nemáte steam originální verzi, doporučuji zálohovat původní soubory!
- Je tam hromada gramatických chyb a hromada nepřesností, ale jako provizorní čeština to stačí.

Není přeložena pouze část "The Forgotten", která by se měla nacházet v původní verzi na konci souboru en-language.txt, resp. v souboru en-language\_x2.txt v případě datadisku.

**Připoj se k tvorbě češtiny i ty!**
