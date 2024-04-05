---
title: "Aktualizace PunkBusteru v CoD"
date: "2016-08-30"
tags: 
  - "cod"
  - "cod4"
  - "game"
  - "punkbuster"
coverImage: "punk_buster.png"
---

Po [ukončení podpory](http://old.maxxx.cz/2013/11/01/call-of-duty-2-bez-podpory-punkbusteru/) v březnu roku 2013 se dal anti-cheat ještě nějakou dobu aktualizovat skrze standalone ultilitu [pbsetup](http://www.evenbalance.com/pbsetup.php). Jenže před časem již hra zmizela z nabídky této ulitlity a tudíž je skrze oficiální server nemožné updatovat PB na čerstvých instalacích hry. K dnešnímu dni již nelze skrze ultilitu updatovat žádné COD (viz. screen). Proto pokud po vás herní server požaduje aktuální PunkBuster, tak je pro vás jedinou možností přepsat aktuálními soubory PB ty původní. Předtím by ale měla proběhnout kontrola běžících služeb (důležité hlavně u novějších OS). Pozn.: Aktuální PB vyžadují i servery [GameParku](http://www.gamepark.cz/) (RIP [GamePark](https://www.gamepark.cz/tema/gamepark-se-meni/) 25. 7. 2018)

\[caption id="attachment\_4366" align="alignnone" width="636"\]![](images/pb-error-the-update-attemp-failed.jpg) ERROR: The update attemp failed because the file pbsecsv.htm is missing on the update servers. Please try again later.\[/caption\]

### Instalace/re-instalace PunkBuster služeb (Windows)

1. Stáhněte [pbsvc.exe](https://1drv.ms/u/s!AmaMNBEz9Mw0gbw5vC2JeTxkALJdZg) v0.994 ([mirror](http://www.evenbalance.com/downloads/pbsvc/pbsvc.exe))
2. Spusťte pbsvc.exe a vyberte možnost "Install/Re-install Punkbuster service". Potvrďte licenční podmínky. Klikněte na "Next" - na konci každé služby by se mělo zobrazit zelené "OK ". Opět klikněte na "Next" a sledujte kontrolu, dokud se neobjeví výsledek "Tests completed successfully without error"
    
    ![](images/pb3.png)
3. Nyní je třeba se ujistit jestli jsou služby "pnkbstrA.exe" a "pnkbstrB.exe" povoleny ve firewallu.

### Aktualizace PunkBusteru pro Call of Duty 2 (Windows a Linux)

1. V závislosti na vašem operačním systému stáhněte soubory pro Windows nebo Linux - [cod2\_pb\_windows.rar](https://1drv.ms/u/s!AmaMNBEz9Mw0gbw4fHYelAW06uRb_A) - [cod2\_pb\_linux.zip](https://1drv.ms/u/s!AmaMNBEz9Mw0gbw3lBpQfqEfJg5NTw)
2. Soubory z těchto archívů rozbalte a nakopírujte sloku PB a veškerý obsah do vaší složky s hrou: =C:\\Program Files (x86)\\Steam\\steamapps\\common\\Call of Duty 2 nebo pokud se jedná o non-steam verzi: = C:\\Program Files (x86)\\Activision\\Call of Duty 2

### Nastavte správný cvar rate:

1. Spusťte multiplayer a povolte konzoli v nastavení.
2. Ve hře spusťte konzoli pomocí klávesy " ~ "
3. Do konzole napište "rate 25000"
4. Potvrďte klávesou Enter.

### Ostatní díly série:

Postup je obdobný i pro ostatní díly série. Aktuální PB soubory jsou ke stažení např. zde:

- [Call of Duty & Call of Duty: United Offensive](http://www.callofdutyview.net/files/pb/cod_pb.zip)
- [Call of Duty 4: Modern Warfare](http://www.callofdutyview.net/files/pb/cod4mw_pb.zip)
- [Call of Duty: World at War](http://www.callofdutyview.net/files/pb/codwaw_pb.zip)
