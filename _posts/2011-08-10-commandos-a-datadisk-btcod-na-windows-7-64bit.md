---
title: "Commandos a datadisk BTCOD na Windows 7 (64bit)"
date: "2011-08-10"
category: Hry
tags: 
  - "Commandos"
image: 
  path: /img/2011-08-10-Commandos-a-datadisk-btcod-na-windows-7-64bit/commandos.jpg
  alt: Commandos GOG
---

Jediný způsob jak nainstalovat Commandos a jeho datadisk Beyond The Call of Duty na 64bitové verzi Windows 7 a dle všeho to platí i pro 64bitovou Vistu je ten který tedy popíšu. Je velmi důležité aby jste dodržely naprosto přesně všechny kroky mého návodu. Vyřešil jsem i problém s ukládáním a načítáním uložených her. Musí se to dělat tímto způsobem, protože 64bitové systémy nespustí ani instalátor `setup.exe`{: .filepath}, protože není kompatibilní s 64bitovými systémy.

 - Vytvořte složku pro hru v Program Files (x86) její struktura bude takováto: \
`C:\Program Files(x86)\Eidos Interactive\Pyro\Commandos\Beyond the Call of Duty`{: .filepath} \
pro datadisk (Beyond The Call of Duty) nebo \
`C:\Program Files (x86)\Eidos Interactive\Pyro\Commandos`{: .filepath}
pro puvodni hru (Beyond The Enemy Lines) \
![Folder](/img/2011-08-10-Commandos-a-datadisk-btcod-na-windows-7-64bit/commandos slozka.jpg)

 - Do vytvořené složky hry nebo datadisku zkopírujte soubory hry z CD.
**Pro Beyond The Call of Duty (datadisk):**
Zkopírujte soubory, které najdete je ve složce `comman_mp` na disku CD do složky
`C:\Program Files (x86)\Eidos Interactive\Pyro\Commandos\Beyond the Call of Duty`{: .filepath}, kterou jste vytvořily v prvním kroku.

**Jsou to tyto soubory:** (uvnitř složky `comman_mp`{: .filepath})

| Název | Formát |
| :--- | ---: |
| Datos | složka |
| mplayer | složka |
| output | složka |
| video | složka |
| coman_mp | exe |
| mpserver | exe | 
| MSS16 | dll |
| MSS32 | dll |
| mssb16 | tsk |
| tutorial | exe |
| WAR_MP | složka |

**Pro Beyond The Call of Duty (základní hru):** \
Zkopírujte soubory, které najdete je ve složce `COMMANDOS`{: .filepath} na disku CD do složky \
`C:\Program Files (x86)\Eidos Interactive\Pyro\Commandos`{: .filepath}, kterou jste vytvořily v prvním kroku.

**Jsou to tyto soubory:** (uvnitř složky `COMMANDOS`{: .filepath})

| Název | Formát |
| :--- | ---: |
| Datos | složka |
| mplayer | složka |
| output | složka |
| video | složka |
| comandos | exe |
| mpserver | exe | 
| MSS16 | dll |
| MSS32 | dll |
| mssb16 | tsk |
| WARGAME | složka |

> Složku `video`{: .filepath} kopírovat nemusíte (např. z důvodu úspory místa), ale pokud tak neučiníte, budete potřebovat při spuštění mít vložené CD v mechanice.
{: .prompt-tip }

-  Nastavte kompatibilitu spouštěcích souborů a to v datadisku u souboru `coman_mp.exe`{: .filepath} a u základní hry u souboru `Comandos.exe`{: .filepath} na __Windows 98 / Windows Me__.\
    - To uděláte tak, že na soubor ve složce s hrou kliknete druhým tlačítkem pak Vlastnosti - záložka Kompatibilita - a tam vyberete "Tento program spustit v režimu kompatibility pro:" Windows 98 / Windows Me. 
    - V této chvíli už by vám měli obě dvě hry jít spustit, pokud se tak neděje, bude třeba udělat ještě manuálně **zápis do registrů** 

- Až nakopírujete všechny soubory do příslušných složek a nastavíte kompatibilitu dle popisu výše, tak si otevřete Poznámkový Blok (notepad) a do něj vložte přesně toto.

```bat
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Pyro]

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Pyro\Comma ndos]

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Pyro\Comma ndos\1.0]
"DirCd"="D:\\Comandos"
"DirIns"="C:\\Program Files (x86)\\Eidos Interactive\\Pyro\\Commandos"
"Type"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Pyro\Comma ndos\1.0MP]
"DirCd"="D:\\COMAN_MP"
"DirIns"="C:\\Program Files (x86)\\Eidos Interactive\\Pyro\\Commandos, Beyond the Call of Duty""Type"=dword:00000003"
```
{: file='Pyro.reg'}

> Je velmi důležité aby jste nevynechaly ani první řádek!
{: .prompt-info }

-  Poté klikněte na Soubor - Uložit jako a soubor pojmenujte `Pyro.reg`{: .filepath} a uložte si ho třeba na plochu.

![Registry](/img/2011-08-10-Commandos-a-datadisk-btcod-na-windows-7-64bit/commandos-registry.jpg)

-  Spusťte `Pyro.reg`{: .filepath}. Vyskočí na Vás upozornění, že se chystáte udělat zápis do registru a že to může mít následky. To potvrdíte a poté by se Vám měla objevit oznámení o tom, že tato úprava byla provedena.
-  Nyní by jste pro jistotu měli mít disk CD v mechanice (buďto ve fyzické nebo pouze na mountovaný obraz disku) a bezproblémově začít hrát.

Pokud máte ve hře **problémy s ukládáním a načítáním hry**, tak postupujte následovně.

1. Jděte do složky s hrou kde dál projděte do složky s názvem `OUTPUT`{: .filepath} tam by se měl nacházet soubor `comando.cfg`{: .filepath}
2. Soubor `comando.cfg`{: .filepath} editujte např. v Poznámkovém bloku (notepadu) a za to co soubor obsahuje vložte tyto 3 řádky:

```bat
.SIZE [ .INITSIZE 3 ]
.PROFILE [ .USER 0 ]
.DEVELOP 1
```
{: file='C:\Program Files (x86)\Eidos Interactive\Pyro\Commandos\OUTPUT\comando.cfg'}

![Edit](/img/2011-08-10-Commandos-a-datadisk-btcod-na-windows-7-64bit/commandos-uprava%20cfg.jpg)

> Pokud bude s přepisováním souboru `comandos.cfg`{: .filepath} problém, tak stačí ve vlastnostech složky zakázat možnost __Pouze ke čtení__.
{: .prompt-tip }

- soubor uložte a spusťte hru. Vše by mělo být v pořádku a Vy můžete začít hrát a vesele ukládat svůj herní postup.

![Save](/img/2011-08-10-Commandos-a-datadisk-btcod-na-windows-7-64bit/commandos-druhamise.jpg)

**Alternativa:**

Pokud uvažujete o koupi této hry, tak zvažte digitální distribuci. Nejenom proto, že originální krabicová verze bude dnes již jen těžko k sehnání, ale digitální distribuce nabízí upravené verze her s podporou novějších operačních systémů a výrazné slevy. Pokud nakupujete v ekosystému Steam, tak je možno zakoupit celou [kolekci](https://store.steampowered.com/sub/4156/?snr=1_7_7_151_150_1), nebo je možnost zakoupit tzv. [Ammo Pack na GoG.com](https://www.gog.com/game/commandos_ammo_pack), kdy stáhnete instalční soubor bez [DRM](https://cs.wikipedia.org/wiki/Digital_rights_management) s hrou a datadiskem bez nutnosti instalovat herní klient (jako je Steam).
