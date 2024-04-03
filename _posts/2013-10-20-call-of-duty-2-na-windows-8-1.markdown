---
layout: post
title: Call of Duty 2 na Windows 7 / 8.1
date: '2013-10-20 10:25:00'
tags:
- cod
- config
- steam
- windows
- hash-wordpress
- hash-import-2023-08-28-13-25
---

**Aktualizovaný článek pro finální sestavení Windows 10 naleznete [zde](http://www.maxxx.cz/2016/04/18/call-duty-2-na-windows-10/).**

_„Jak zprovoznit Call of Duty 2 na Windows 8 ?“_  
  
Pokusil jsem dnes po nedávném upgrade Windows 8 na Windows 8.1 v mém případě verze Pro s Media Centrem nainstalovat Call of Duty 2 a zahrát si multiplayer. Avšak čekalo mě nemilé překvapení. Zprovoznění této hry na novějším operačním systému, než je ten pro který byla tato hra vydána (tj. Windows XP) byl vždy velký problém. Pamatuji si tak jsem přijel na turnaj do PGCC a od počítače k počítači létal vyděšený technik který nemohl COD2 korektně spustit na počítačích s Windows Vista. Je pravda, že na Windows Vista stejně jako na později vydaném Windows 7 stačilo hru spouštět s vyšším oprávněním (resp. oprávněním správce) a v režimu kompatibility pro Windows XP SP2 či SP3. Já se ale pokusil tuto hru na Windows 8 (později na všech bezplatných updatech tohoto systému) prvně spustit bez zásahu…

<!--more-->

#### Při vložení DVD do mechaniky se instalace (AutoPlay) vůbec nespustí a vrátí pouze chybu:

> „List index out of bounds (-1)“

Stačí pouze **spustit instalaci ručně**. Tedy jít do „Tento počítač“ kliknout druhým tlačítkem na mechaniku ve které je vloženo „COD2DVD“ poté najít „setup.exe“, kliknout na něj druhým tlačítkem a „Spustit jako správce“.  
Poté by se již měla instalace spustit korektně. Na konci instalace vám instalátor nabídne instalaci starší DirectX rozhraní – to instalovat můžete či nemusíte, ale poté **důrazně doporučuji aktualizovat DirextX** ze [stránek Microsoft](http://www.microsoft.com/cs-cz/download/details.aspx?id=35 "directX dowload").

#### Po spuštění hry se zobrazí pouze černá obrazovka a po chvíli tradiční chybová hláška:

> „CoD2MP\_s.exe přestal pracovat“

Toto šlo na Windows 7 řešit pouze režimem kompatibility z **Windows XP (Service Pack 2)** a spuštěním **programu v režimu správce**.  
čehož docílíme kliknutím na ikonu zástupce na ploše druhým tlačítkem, dále Vlastnosti -\> Kompatibilita

[![](http://4.bp.blogspot.com/-ry9PTWoMVQU/UmOdiph6iSI/AAAAAAAADa8/aLJfDgiBCK0/s1600/kompatibilita.png)](http://4.bp.blogspot.com/-ry9PTWoMVQU/UmOdiph6iSI/AAAAAAAADa8/aLJfDgiBCK0/s1600/kompatibilita.png)

#### Problém s ovladačem zvukových karet Realtek HD Audio

Na Windows 8 je však ještě problém s ovladačem zvukových karet Realtek HD Audio, kdy hra někomu funguje pouze když je připojen mikrofon . Mě však hra nefungovala ani když sluchátka s mikrofonem připojeny byli. Tento nedostatek jde tedy obejít i softwarově. A to tak že:

1. Druhým tlačítkem kliknete na ikonu **Ovládání hlasitosti** u hodin
2. Vyberete položku Z **ařízení pro záznam**
3. Zde kliknete druhým tlačítkem do pole kde máte zobrazené záznamové zařízení
4. A vyberete **Zobrazit zakázaná zařízení**
5. Mělo by se tam objevit zařízení „ **Směšovač stereo** „
6. Na něj kliknete druhým tlačítkem a dáte „ **povolit** „

[![](http://4.bp.blogspot.com/-fA3p2TnhhaE/UmOgDIpTFwI/AAAAAAAADbE/J7-atn2q6G4/s1600/kompatibilita.png)](http://4.bp.blogspot.com/-fA3p2TnhhaE/UmOgDIpTFwI/AAAAAAAADbE/J7-atn2q6G4/s1600/kompatibilita.png)

#### Steam verze

Pokud máte hru zakoupenu přes steam (Tato verze se od verze na DVD téměř v ničem neliší).&nbsp; **Tak musíte provést vše co je již výše popsáno!** &nbsp;Nýbrž je tu ještě jeden problém. Při spuštění hry se zobrazí [chybové hlášení](http://i.imgur.com/Ds2asok.png "steam"):

> „Application Error: Failed to find Steam“

Tento problém má dvě možné řešení. Prvním řešením je:  
Stačí jít do složky ve které je nainstalován Steam, ta se nachází v  
„C:\Program Files (x86)\Steam“ a **překopírovat** z ní soubor „Steam.dll“ do složky s hrou, která se nachází v  
„C:\Program Files (x86)\Steam\steamapps\common\Call of Duty 2“  
– Toto řešení zprovozní hru bez Steam&nbsp;overlay (Alt+tab nefunkční).

Druhým řešením je:  
Přejí do složky kde se nachází soubor Steam.exe („C:\Program Files (x86)\Steam“) a nastavit mu parametr „Spustit program jako správce“ ve vlastnostech, záložka kompatibilita.  
– Toto řešení zprovozní hru včetně&nbsp;Steam overlay a všech jeho funkcí.

#### Pokud hrajete na notebooku se dvěma GPU

Častý problém je také to, že notebook má integrovanou grafickou kartu (nejčastěji Intel HD) a další dedikovanou (Nvidia či ATi). Pokud se hra spustí na integrovanou, tedy Intel HD – může to způsobit zobrazení černé obrazovky při startu hry. Pokud jste provedli všechny výše zmíněné úpravy, hrajete na notebooku a při spuštění máte pouze „black screen“, tak zkontrolujte v ovládacím panelu vaší grafické karty (Nvidia control panel, Catalyst control center) jestli se hra skutečně spouští pomocí Nvidia/ATi karty, v opačném případě to nastavte.

#### Problém s výkonem ve hře (nízké či kolísající FPS)

Nyní se vám bude stávat, že ve hře bude vidět systémový kurzor myši a ten herní bude neaktivní. To však lze vyřešit zkratkou **Alt&nbsp;+ TAB** &nbsp;kdy skočíte zpět do OS a pak se opět přepnete do hry. Kurzor již bude aktivní.Když již **&nbsp;** v systému, tak by jste vždy mohli nastavit hře vyšší prioritu, což vyřeší problém s **nízkými či kolísajícími FPS** &nbsp;uděláte to jednoduše tak že:

1. Při spuštěné hře se pomocí **Alt + TAB** &nbsp;přepnete zpět na plochu
2. Kliknete druhým tlačítkem na hlavní panel a spustíte „ **Správce úloh** „
3. Vyberete záložku „ **Podrobnosti** “ a najdete „ **CoD2MP\_s“**
4. Kliknete na něj druhým tlačítkem a vyberete možnost „ **Nastavit prioritu** “ – „ **Vysoká** „
5. Poté nezapomeňte vypnout správce úloh a vraťte se do hry…

| [![](http://4.bp.blogspot.com/-2CtzHn1Ixzk/UzR0XMqcFFI/AAAAAAAAHSE/DKfmYUnkqf8/s1600/priorita.png)](http://4.bp.blogspot.com/-2CtzHn1Ixzk/UzR0XMqcFFI/AAAAAAAAHSE/DKfmYUnkqf8/s1600/priorita.png) |
| Nastavení priority |

Toto nastavení bohužel musíte provádět po každém spuštění hry znovu (systém si ho nepamatuje)!

**Pozn. Hra byla instalována z originálního DVD disku s oficiálním sériovým číslem, hra je v české verzi a byl aplikován patch 1.3 pro CZ verzi. Který stáhnete např. [ZDE](http://www.ulozto.cz/xiFAKq2/cod2-patch-1-3-cz-exe)**

**Další problémy:**  
V polovině října se vyskytl v některých hrách běžících pod Windows 8.1 problém s „[lagující myší](http://www.maxxx.cz/2013/10/windows-8-1-a-lagujici-mys/ "lag mouse")„, který byl o měsíc později [vyřešen](http://www.maxxx.cz/2013/11/reseni-problemu-s-lagujici-mysi/ "řešení") oficiálním updatem ze strany Microsoftu. A také se na občas stává, že narazíte na neaktulizovaný server, který Vás bude bezdůvodně „kickovat“ což je způsobeno zrušením oficiální [podpory punkbusteru](http://www.maxxx.cz/2013/11/call-of-duty-2-bez-podpory-punkbusteru/ "PB").  
  

S dalšími problémy jsem se zatím na Windows 8.1 ohledně Call of Duty nesetkal. Pokud o nějakém víte, tak napište prosím do komentářů, pokusím se vám pomoct.

**Changelog:**

**#** Na požádání vyzkoušeno i na uzavřených serverech (vyžadující klient) jako je např. [GamePark](http://www.gamepark.cz/hra/call-of-duty-2)  
**#** Přidáno řešení problému s kolísajícími FPS

**#** Řešení problému kdy se instalace vůbec nespustí
<!--kg-card-end: html-->