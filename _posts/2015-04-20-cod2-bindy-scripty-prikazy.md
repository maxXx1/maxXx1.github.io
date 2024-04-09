---
title: "COD2 - Bindy, scripty, příkazy"
date: "2015-04-20"
tags: 
  - "COD2"
image: 
  path: "/img/2015-04-20-cod2-bindy-scripty-prikazy/screenshot_2015-04-08.jpg"
  alt: COD2 Console
---

V Call of Duty 2 leze využít mnoha příkazů sctiptů a podobných nastavení z configu, ale také přímo ze hry. Tyto příkazy vám mohou zvelebit váš nick name barvami, spustit nahrávání záznamu ze zápasu, nastavení předkonfigurovaného bindu a mnoho dalšího. Právě na tyto příkazy a další drobné nastavení se podíváme v tomto článku.

### Konzole

Konzole se zapíná pomocí klávesy `~` která se nachází pod klávesou Escape. Do této konzole se vypisuje veškeré dění ve hře a také se do ní vkládají příkazy. Pro úplný výpis konzole slouží zkratka `shift + ~`.

### Bindy

Bind je způsob mapování libovolného příkazu k libovolné klávese. Tedy například:
```console
/bind p name say Hello world!
``` 
Vypíše vždy po stisknutí klávesy `p` do chatu: *Hallo world!* <br> 
Takto se dá mapovat jakýkoliv příkaz, na jakoukoliv klávesu. Syntaxe je vždy 
`/bind "klávesa" "příkaz" "parametr"`

### Barevný nickname

Hra disponuje možností obarvit si jméno (nickname), které bude mít barvy jaké deklarujeme v tabulce výpisu score (scoreboard) či v chatu. Barvy mají v nicku určitou syntaxi a tou je, že před číslo, které určuje barvu vložíte znak `^`stříšky - jednoduše např. pomocí klávesové zkratky `alt + 94` v případě, že máte klávesnici přepnutou na českou znakovou sadu. __Příklad:__
```console
f^1$^7.max^9X^7x ^9RattenZone
```

![Nick](/img/2015-04-20-cod2-bindy-scripty-prikazy/17541545.jpg)

Takže pokud si potřebujete tento postup zrychleně vyzkoušet přímo ze hry zapněte konzoli a napište příkaz:
```console
name ^1Jmeno
```
Ve scoreboardu by se měl objevit nápis "Jméno" a být celý červeně.

#### Seznam barev:

  | kód | barva | poznámka |
  | :-- | :---- | :------ |
  | `^^0` | černá | u černé barvy musíte použít 2x stříšku ^ | 
  | `^1` | červená | |
  | `^2` | zelená | |
  | `^3` | žlutá | |
  | `^4` | modrá | |
  | `^5` | světle modrá | |
  | `^6` | fialová | |
  | `^7` | bílá | |
  | `^8` | matně zelená | když hrajete za Američany (i Němce) | 
  |    | růžová | když hrajete za Rusy (i Němce) |  
  |    | modrofialová |když hrajete za Brity (i Němce) | 
  | `^9` | šedá | |

#### Dvojité použití

Duplicitním použitím docílíte toho, že váš nick bude barevný i ve výpisu chatu a tabulce kde se zobrazuje kdo koho zabil. Problémem je, že v některých částech hry bude syntaxe celého příkazu viditelná, tedy bude vidět i stříška s jedničkou.
```console
max^11Xx
```

### Voice messages

Dalšími bezesporu rychlými příkazy, kterými lze vyjádřit velmi rychle a efektivně většinu příkazů vašim spoluhráčům jsou hlasové příkazy. Řadí se do několika kategorií a lze ve vyvolat defaultně klávesou `v` a vybírat čísly. nebudete se tedy muset zdržovat zdlouhavým vypisováním do chatu. Po zadání příkazu se ozve ve hře to co jste chtěli říci, souběžně se to vypíše do chatu a vaše ikona začne blikat na minimapě. Příkladem může být voice *"Enemy spotted!*, kdy spoluhráč nejenom ví, že jste zahlédl nepřítele, ale ví i přibližně kde.

#### Význam jednotlivých klávesových kombinací:

##### Pohyb (Move)

| Klávesy | Hláška | Význam |
| :-- | :---- | :------ |
| `v+1+1` | Follow me! | Za mnou! |
| `v+1+2` | Move in! | Pohyb! |
| `v+1+3` | Fall back! | Zpátky! |
| `v+1+4` | Suppressing fire! | Krycí palba! |
| `v+1+5` | Squad, attack left flank! | Útok na levé křídlo! |       
| `v+1+6` | Squad, attack right flank! | Útok na pravé křídlo! |         
| `v+1+7` | Squad, hold this position! | Držte pozice! |
| `v+1+8` | Squad, regroup! | Přeskupit se! |

##### Hlášky (Statements)

| Klávesy | Hláška | Význam |
| :-- | :---- | :------ |
| `v+2+1` | Enemy spotted! | Vidím nepřítele! |
| `v+2+2` | Enemy down! |  Nepřítel mrtev! |
| `v+2+3` | I’m in position. | Jsem na místě! |
| `v+2+4` | Area secure! | Prostor zabezpečen! |
| `v+2+5` | Grenade! | Granát! |
| `v+2+6` | Sniper! | Sniper! |
| `v+2+7` | Need reinforcements! | Potřebuji posily! | 
| `v+2+8` | Hold your fire! | Nestřílet! |

##### Odpovědi (Responses)

| Klávesy | Hláška | Význam |
| :-- | :---- | :------ |
| `v+3+1` | Yes sir! | Ano! |
| `v+3+2` | No sir! | Ne! |
| `v+3+3` | On my way. | Za mnou. |
| `v+3+4` | Sorry! | Promiň! |
| `v+3+5` | Great shot! | Skvělý zásah! |
| `v+3+6` | Took long enough! |  Trvá vám to moc dlouho! |
| `v+3+7` | Are you crazy? | Jsi normální? |

### Příkazy

Když spustíte konzoli musíte vymazat znak středníku a vždy vložit lomítko před zadávaný příkaz, pak můžete vkládat mnoho příkazů neboli `cvars`. 
U příkazu se vždy zobrazí nápověda pro jeho případné parametry.

#### Nejpoužívanější příkazy

| cvar | funkce | poznámka |
| :-- | :---- | :------ |
| `/kill` | Zabít se | |
| `/screenshotJPEG` | Vyfotí konzoli a obrázek uloží do složky s hrou | v případě použití bindu vyfotí danou scénu |
| `/connect 192.168.0.1` | připojení k dané IP drese | serveru |
| `/reconnect` | znovupřipojení | na poslední připojený server |
| `/disconnect` | odpojí se ze serveru | do menu hry |
| `/bind` | mapování příkazu na klávesu | přímo z konzole |
| `/name jmeno` | změni nickname | |
| `/record nazev` | začne nahrávat demo ze zápasu | uloží jej do složky s hrou |
| `/stoprecord` |  zastaví nahrávání | |
| `/demo název` | přehraje záznam | musí být ve složce "demos" |
| `/pb_plist` | seznam hráčů podle PunkBusteru | |
| `/pb_kick 1` | vyhození hráče č. 1 dle seznamu "plist" | je nutné mít oprávnění | 

### Scripty

Scriptování je zjednodušeně spouštění různých sekvencí příkazů pomocí buďto klávesou (bindem) nebo načtením konfiguračního souboru.
