---
layout: post
title: Aktualizace PunkBusteru v CoD
tags:
- cod
- cod4
- punkbuster
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Po [ukončení podpory](http://www.maxxx.cz/2013/11/01/call-of-duty-2-bez-podpory-punkbusteru/)&nbsp;v březnu roku 2013 se dal anti-cheat ještě nějakou dobu aktualizovat skrze standalone ultilitu [pbsetup](http://www.evenbalance.com/pbsetup.php). Jenže před časem již hra zmizela z nabídky této ulitlity a tudíž je skrze oficiální server nemožné updatovat PB na čerstvých instalacích hry. K dnešnímu dni již nelze skrze ultilitu updatovat žádné COD&nbsp;(viz. screen). Proto pokud po vás herní server požaduje aktuální PunkBuster, tak je pro vás jedinou možností přepsat aktuálními soubory PB ty původní. Předtím by ale měla proběhnout kontrola běžících služeb (důležité hlavně u novějších OS).  
Pozn.: Aktuální PB vyžadují i servery [GameParku](http://www.gamepark.cz/)&nbsp;(RIP [GamePark](https://www.gamepark.cz/tema/gamepark-se-meni/)&nbsp;25. 7. 2018)

<figure id="attachment_4366" aria-describedby="caption-attachment-4366" style="width: 636px" class="wp-caption alignnone"><img decoding="async" loading="lazy" class="wp-image-4366 size-full" src="http://192.168.20.2/wordpress/wp-content/uploads/2016/08/pb-error-the-update-attemp-failed.jpg" alt="" width="636" height="407" srcset=" __GHOST_URL__ /content/images/wordpress/2016/08/pb-error-the-update-attemp-failed.jpg 636w, __GHOST_URL__ /content/images/wordpress/2016/08/pb-error-the-update-attemp-failed-300x192.jpg 300w" sizes="(max-width: 636px) 100vw, 636px"><figcaption id="caption-attachment-4366" class="wp-caption-text">ERROR: The update attemp failed because the file pbsecsv.htm is missing on the update servers. Please try again later.</figcaption></figure>

### Instalace/re-instalace PunkBuster služeb (Windows)

1. Stáhněte&nbsp;[pbsvc.exe](https://1drv.ms/u/s!AmaMNBEz9Mw0gbw5vC2JeTxkALJdZg)&nbsp;v0.994&nbsp;([mirror](http://www.evenbalance.com/downloads/pbsvc/pbsvc.exe))
2. Spusťte&nbsp;pbsvc.exe a vyberte možnost&nbsp;„Install/Re-install Punkbuster service“.  
Potvrďte licenční podmínky.  
Klikněte na&nbsp;„Next“ – na konci každé služby by se mělo zobrazit zelené&nbsp;„OK „.  
Opět klikněte na „Next“ a sledujte kontrolu, dokud se neobjeví výsledek&nbsp;„Tests completed successfully without error“

![](http://192.168.20.2/wordpress/wp-content/uploads/2016/08/pb3.png)

3. Nyní je třeba se ujistit jestli jsou služby&nbsp;„pnkbstrA.exe“ a „pnkbstrB.exe“ povoleny ve firewallu.

### Aktualizace PunkBusteru pro Call of Duty 2 (Windows a Linux)

1. V závislosti na vašem operačním systému stáhněte soubory pro Windows nebo Linux  
– [cod2\_pb\_windows.rar](https://1drv.ms/u/s!AmaMNBEz9Mw0gbw4fHYelAW06uRb_A)  
–&nbsp;[cod2\_pb\_linux.zip](https://1drv.ms/u/s!AmaMNBEz9Mw0gbw3lBpQfqEfJg5NTw)
2. Soubory z těchto archívů rozbalte a nakopírujte sloku PB a veškerý obsah do vaší složky s hrou:  
=C:\Program Files (x86)\Steam\steamapps\common\Call of Duty 2  
nebo pokud se jedná o non-steam verzi:  
=&nbsp;C:\Program Files (x86)\Activision\Call of Duty 2

### Nastavte správný cvar rate:

1. Spusťte multiplayer a povolte konzoli v nastavení.
2. Ve hře spusťte konzoli pomocí klávesy&nbsp;“ ~ „
3. Do konzole napište „rate 25000“
4. Potvrďte klávesou Enter.

### Ostatní díly série:

Postup je obdobný i pro ostatní díly série. Aktuální PB soubory jsou ke stažení např. zde:

- [Call of Duty & Call of Duty: United Offensive](http://www.callofdutyview.net/files/pb/cod_pb.zip)
- [Call of Duty 4: Modern Warfare  
](http://www.callofdutyview.net/files/pb/cod4mw_pb.zip)
- [Call of Duty: World at War](http://www.callofdutyview.net/files/pb/codwaw_pb.zip)
<!--kg-card-end: html-->