---
title: "Službě Profil uživatele se nepodařilo přihlášení"
date: "2016-03-29"
categories: 
  - "Windows"
tags: 
  - "Windows-7"
image:
  path: "/img/2016-03-29-sluzbe-profil-uzivatele-se-nepodarilo-prihlaseni/chyba-1.jpg"
  alt: Windows 7
---

Poslední dobou se čím dál častěji stává, že při přihlášení k počítači se systémem Windows 7 nebo Windows Vista se zobrazí následující chybová zpráva:

> _Službě Služba Profil uživatele se nepodařilo přihlášení. Nelze načíst profil uživatele._

Tato chyba může být zapříčiněna virem, nekompatibilitou software třetí strany (nejčastěji nevhodným anti-virovým řešením) či vadnými sektory na pevném disku. V ideálním případě není odstranění této chyby nijak složité.

## Pokud je na počítači více než jeden účet s oprávněním správce

V tomto případě doporučuji skrze "Start - Ovládací panely - Uživatelské účty" založit nového uživatele (uživatelský profil) a z `C:\Users\jméno poškozeného profilu\`{: .filepath} zkopírovat všechna data do nově založeného profilu. Toto by měl zvládnout naprosto každý.

## Pokud je na počítači pouze jeden účet s oprávněním správce

> Postupujte přesně podle návodu a bez rozmyslu nic jiného nemažte ani neupravujte, protože jakákoliv operace v regtru je definitivní a nevratná!
{: .prompt-danger }

1. Počítač spustíme v **Nouzovém režimu** (při startu stlačená klávesa F8)
2. Přihlásíme se ke svému účtu správce (v nouzovém režimu by se měl načíst "dočasný profil")
3. Spustíme Editor Registru (CTRL + R - "regedit")
4. Přejdeme do větve registru
```    
HKEY\_LOCAL\_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList
```    
5. Zde uvidíte výpis SID - po kliknutí na dané SID uvidíte v pravé části (v řádku ProfileImagePath) o jaký profil se jedná 
![reg](/img/2016-03-29-sluzbe-profil-uzivatele-se-nepodarilo-prihlaseni/reg.jpg)
6. Vaše SID naleznete ve dvou podobách a jedna z nich bude mít příponu .bak. To SID bez přípony **přejmenujeme**, tak aby mělo příponu **.bak2** a u SID s .bak příponou - **tuto příponu smažeme**.
7. Po tomto zákroku se ze zálohovaného SID (.bak) stane SID hlavní (tedy bez backup příznaku)!
8. Toto (hlavní) SID otevřeme a překontrolujeme klíče `RefCount` a `State`. **Oba klíče musí mít hodnotu 0!** 
![hodnoty](/img/2016-03-29-sluzbe-profil-uzivatele-se-nepodarilo-prihlaseni/hodnoty.jpg)
   To znamená, že pokud mají jinou, tak dvojklikem na daný klíč otevřeme dialogové okno, kde "Údaj hodnoty" změníme na 0.
![dvojklik](/img/2016-03-29-sluzbe-profil-uzivatele-se-nepodarilo-prihlaseni/dvojklik.jpg)
9. Poté restartujeme PC a necháme normálně načíst systém Windows.

Prvotní přihlašovaní k vašemu účtu (po tomto zákroku) může trochu déle trvat, ale další přihlášení by již mělo proběhnout normální rychlostí.

## Hledání příčiny problému

Po provedení opravy důrazně doporučuji

- otestovat počítač anti-virovým scanem (např. [ESET Online Scanner](https://www.eset.com/cz/online-scanner-popup/))
- provést diagnostiku povrchu pevného disku např. pomocí [HD Tune](https://www.hdtune.com/files/hdtune_255.exe)
- oprava ingerity systémových souborů Spustit **příkazový řádek** jako správce a spustit scan pomocí příkazu 
```powershell
sfc /scannow
```

## Profil se nenačte ani v nouzovém režimu

Pokud se v nouzovém režimu nenačte ani "dočasný profil", tak je nutné nabootovat do tzv. live systému (např. MiniXP skrze [HirensBootCD](https://www.hirensbootcd.org/download/)) a provést výše uvedené úpravy skrze nástroj "**Registry Editor PE**".
