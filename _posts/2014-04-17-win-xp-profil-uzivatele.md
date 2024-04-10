---
title: "Win XP - zásek na login screenu"
date: "2014-04-17"
category: "Windows" 
tags: 
  - "Windows-XP"
image: 
  path: /img/page/Windows-XP.png
  alt: Windows XP
---

Je to takový nešvar posledních dní. Microsoft zřejmě tvrdě bojuje sám proti sobě tím, že nejdříve ukončil podporu pro 13 let starému Windows XP (SP3) a v ten samý den ukončil podporu svému antivirovému programu Microsoft Security Essentials pouze pro Windows XP. 
Včerejší respektive před-včerejší aktualizace jeho virových definic obsahovala kritickou chybu, která způsobí zaseknutí systému na obrazovce po přihlášení, či těsně po přihlášení do systému.

![xplock](/img/2014-04-17-win-xp-profil-uzivatele/xp-lock-1.jpg)

Přesněji ve chvíli kdy se inicializuje proces po spuštění MS antivirového programu. A to všichni tvrdili, že Windows XP pojedou bez problémů dál :) 
Proto pokud máte Microsoft Security Essentials nainstalovaný na počítači s Windows XP, tak vás nejspíše postihne tato chyba také. 
Pokud se tak již stalo, tak jste ve slepé uličce. Ke korektnímu odinstalování se skrz chybu nedostanete a v nouzovém režimu neběží služba pro odinstalaci, takže z něj program také neodinstalujete. A nepotěší Vás ani informace o tom, že Microsoft se uráčil na danou závadu dnes ráno vydat hotfix, který si díky chybě již nestáhnete...

## Manuální smazání

Nejrychlejším řešením, pro odstranění závady je manuální smazání:

1. Restartovat do nouzového režimu (pomocí klávesy `F8` při startu počítače)
2. V nouzovém režimu (pod účtem Administrator) stiskněte klávesu `Win` + `R`
3. Napište `msconfig` (nebo použijte program [Autoruns](https://learn.microsoft.com/cs-cz/sysinternals/downloads/autoruns))
4. Vyhledejte v záložce "Po spuštění" proces `mssecess` odškrtněte, aby nestartoval
5. V záložce _služby_ zastavte běh služby __Microsoft Antimalware Service__
6. Poté opět `Win` + `R` a napište `regedit` (před tímto korkem doporučuji export/zálohu registrů)
7. Vyhledejte klíče `Microsoft Security Essentials` a `Microsoft Antimalware` a odstraňte je
8. Poté manuálně odstraňte složku s programem na adrese
  ```
  C:\Program Files\Microsoft Security Essentials\
  ```
9. Po restartu počítače by měl již naběhnout systém korektně

Je to sice velmi rychlý a trochu neohrabaný postup, ale problém řeší. Vyzkoušel jsem tento postup během včerejšího a dnešního dne cca. na 10 počítačích různé konfigurace. Poté doporučují prohlédnout položku "Přidat či odebrat programy" v ovládacích panelech, jestli je program opravdu pryč a spustit systémový nástroj __Čištění systému__...

## Výskyt 

Tato chyba se Vám samozřejmě mohla vyhnout, za předpokladu, že...
 - Používáte jiný antivirový program než Microsoft Security Essentials
 - Že jste v inkriminovaný den (16.4.2014) neinstalovali aktualizace skrze Windows Update nebo skrze MSE
 - Se aktualizace nahradila opravenou aktualizací virových definic