---
title: "Call of Duty 2 na Windows 7 / 8.1"
date: "2013-10-20"
category: Hry
tags: 
  - "COD2"
coverImage: "waffen_ss_by_crowhitewolf-d3agp3e-1024x656-1.png"
---

_"Jak zprovoznit Call of Duty 2 na Windows 8 ?"_ Pokusil jsem dnes po nedávném upgrade Windows 8 na Windows 8.1 v mém případě verze Pro s Media Centrem nainstalovat Call of Duty 2 a zahrát si multiplayer. Avšak čekalo mě nemilé překvapení. Zprovoznění této hry na novějším operačním systému, než je ten pro který byla tato hra vydána (tj. Windows XP) byl vždy velký problém. Pamatuji si tak jsem přijel na turnaj do PGCC a od počítače k počítači létal vyděšený technik který nemohl COD2 korektně spustit na počítačích s Windows Vista. Je pravda, že na Windows Vista stejně jako na později vydaném Windows 7 stačilo hru spouštět s vyšším oprávněním (resp. oprávněním správce) a v režimu kompatibility pro Windows XP SP2 či SP3. Já se ale pokusil tuto hru na Windows 8 (později na všech bezplatných updatech tohoto systému) prvně spustit bez zásahu...

### Při vložení DVD do mechaniky se instalace (AutoPlay) vůbec nespustí a vrátí pouze chybu:

> "List index out of bounds (-1)"

Stačí pouze **spustit instalaci ručně**. Tedy jít do "Tento počítač" a na `COD2DVD\setup.exe`{: .filepath} kliknout druhým tlačítkem a "Spustit jako správce". Poté by se již měla instalace spustit korektně. Na konci instalace vám instalátor nabídne instalaci starší DirectX rozhraní - to instalovat můžete či nemusíte, ale poté **důrazně doporučuji aktualizovat DirextX** ze [stránek Microsoft](https://www.microsoft.com/cs-cz/download/details.aspx?id=35 "directX dowload").

### Po spuštění hry se zobrazí pouze černá obrazovka a po chvíli tradiční chybová hláška:

> `CoD2MP_s.exe`{: .filepath} přestal pracovat

Toto šlo na Windows 7 řešit pouze režimem kompatibility z **Windows XP (Service Pack 2)** a spuštěním **programu v režimu správce**. čehož docílíme kliknutím na ikonu zástupce na ploše druhým tlačítkem, dále Vlastnosti -> Kompatibilita

![kompatibilita](/assets/img/2013-10-20-call-of-duty-2-na-windows-8-1/kompatibilita.png)

### Problém s ovladačem zvukových karet Realtek HD Audio

Na Windows 8 je však ještě problém s ovladačem zvukových karet Realtek HD Audio, kdy hra někomu funguje pouze když je připojen mikrofon . Mě však hra nefungovala ani když sluchátka s mikrofonem připojeny byli. Tento nedostatek jde tedy obejít i softwarově. A to tak že:

1. Druhým tlačítkem kliknete na ikonu **Ovládání hlasitosti** u hodin
2. Vyberete položku Z**ařízení pro záznam**
3. Zde kliknete druhým tlačítkem do pole kde máte zobrazené záznamové zařízení
4. A vyberete **Zobrazit zakázaná zařízení**
5. Mělo by se tam objevit zařízení "**Směšovač stereo**"
6. Na něj kliknete druhým tlačítkem a dáte "**povolit**"

![zvuk](/assets/img/2013-10-20-call-of-duty-2-na-windows-8-1/zvuk.png)

### Steam verze

Pokud máte hru zakoupenu přes steam (Tato verze se od verze na DVD téměř v ničem neliší). **Tak musíte provést vše co je již výše popsáno!**  Nýbrž je tu ještě jeden problém. Při spuštění hry se zobrazí chybové hlášení:

> "Application Error: Failed to find Steam"

Tento problém má dvě možné řešení. Prvním řešením je: Stačí jít do složky ve které je nainstalován Steam, ta se nachází v `C:\Program Files (x86)\Steam`{: .filepath} a **překopírovat** z ní soubor `Steam.dll`{: .filepath} do složky s hrou, která se nachází v `C:\Program Files (x86)\Steam\steamapps\common\Call of Duty 2`{: .filepath} - Toto řešení zprovozní hru bez Steam overlay (Alt+tab nefunkční).

Druhým řešením je: Přejí do složky kde se nachází soubor Steam.exe (`C:\Program Files (x86)\Steam`{: .filepath}) a nastavit mu parametr "Spustit program jako správce" ve vlastnostech, záložka kompatibilita. - Toto řešení zprovozní hru včetně Steam overlay a všech jeho funkcí.

### Pokud hrajete na notebooku se dvěma GPU

Častý problém je také to, že notebook má integrovanou grafickou kartu (nejčastěji Intel HD) a další dedikovanou (Nvidia či ATi). Pokud se hra spustí na integrovanou, tedy Intel HD - může to způsobit zobrazení černé obrazovky při startu hry. Pokud jste provedli všechny výše zmíněné úpravy, hrajete na notebooku a při spuštění máte pouze "black screen", tak zkontrolujte v ovládacím panelu vaší grafické karty (Nvidia control panel, Catalyst control center) jestli se hra skutečně spouští pomocí Nvidia/ATi karty, v opačném případě to nastavte.

### Problém s výkonem ve hře (nízké či kolísající FPS)

Nyní se vám bude stávat, že ve hře bude vidět systémový kurzor myši a ten herní bude neaktivní. To však lze vyřešit zkratkou **Alt + TAB** kdy skočíte zpět do OS a pak se opět přepnete do hry. Kurzor již bude aktivní.Když již v systému, tak by jste vždy mohli nastavit hře vyšší prioritu, což vyřeší problém s **nízkými či kolísajícími FPS** uděláte to jednoduše tak že:

1. Při spuštěné hře se pomocí **Alt + TAB** přepnete zpět na plochu
2. Kliknete druhým tlačítkem na hlavní panel a spustíte "**Správce úloh**"
3. Vyberete záložku "**Podrobnosti**" a najdete `CoD2MP_s`{: .filepath}
4. Kliknete na něj druhým tlačítkem a vyberete možnost "**Nastavit prioritu**" - "**Vysoká**"
5. Poté nezapomeňte vypnout správce úloh a vraťte se do hry...

![priorita](/assets/img/2013-10-20-call-of-duty-2-na-windows-8-1/priorita.png "Task Manager")

> Toto nastavení bohužel musíte provádět po každém spuštění hry znovu (systém si ho nepamatuje)!
{: .prompt-warning }