---
layout: post
title: Oprava Windows Update na Windows 7
date: '2016-09-20 11:51:05'
tags:
- update
- windows-7
- hash-wordpress
- hash-import-2023-08-28-13-25
---

V poslední době se nejenom u Windows 7 setkávám s nepříjemným problémem, kdy jak po čisté instalaci, tak po delší době přestane fungovat Windows Update. Projevuje se to tak, že Windows Update neustále hledá aktualizace, ale žádné nenachází ani po desítkách hodin. Že je něco špatně poznáte také tak, že Windows Update začne vytěžovat CPU na určité ustálené hodnotě. V případě dvoujádrových CPU je tato hodnota 50% a v případě čtyřjádrových 25%. Zjistíte to jednoduše skrze správce úloh.

<figure class="aligncenter"><a href="https://www.maxxx.cz/wp-content/uploads/2016/09/50procent.png"><img decoding="async" src="https://www.maxxx.cz/wp-content/uploads/2016/09/50procent.png" alt="50procent" class="wp-image-2323"></a></figure>

Toto vytížení způsobuje konkrétně proces **svchost.exe** , přičemž aktivita pevného disku je minimální.

Pokud již máte nainstalované aktualizace přibližně do května 2016, tedy tento problém se u vás projevil až nyní, tak vám k opravě poslouží&nbsp;**[kumulativní aktualizace z Července 2016](https://support.microsoft.com/cs-cz/kb/3172605)**.

**Pozn.** Dávejte pozor na to aby jste stahovali aktualizaci 32/64 bit dle vašeho OS!

Pokud však máte čistou instalaci systému, pouze se [Service Packem 1](https://www.microsoft.com/cs-CZ/download/details.aspx?id=5842), tak bude nejdříve nutno doinstalovat **[aktualizaci sady služeb z dubna 2015](https://support.microsoft.com/cs-cz/kb/3020369)**&nbsp;a poté&nbsp;Convenience rollup update, což je takový „Sevice Pack 2“ čili souhrnný balík všech aktualizací do května 2016.

**Convenience rollup update** stáhnete nyní pouze s [Microsoft update katalog](http://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB3125574)u, ale vzhledem k tomu, že se nyní Microsoft na svých stránkách zbavuje ActiveX, tak lze katalog otevřít pouze skrze Internet Explorer (který vyzve k nainstalování doplňku).

### Postup instalace aktualizací

Vzhledem k tomu, že proces aktualizací je nyní zaseknutý na „vyhledávání“, tak vám nedovolí spustit další instalace update. Je nutné jej ukončit!

První možností je zastavení služby Windows Update ( **wuausrv** ) ve „Správě počítače“.

1. Stiskněte **Win + R**
2. Napište „ **services.msc** “ (bez uvozovek)
3. Vyhledejte službu „ **Windows Update** „
4. Klikněte na „ **Zastavit** „
<figure class="wp-block-image"><a href="http://192.168.20.2/wordpress/wp-content/uploads/2016/09/stopwu-1024x413-1.png"><img decoding="async" loading="lazy" width="1024" height="413" src="http://192.168.20.2/wordpress/wp-content/uploads/2016/09/stopwu-1024x413-1.png" alt="" class="wp-image-4360" srcset=" __GHOST_URL__ /content/images/wordpress/2016/09/stopwu-1024x413-1.png 1024w, __GHOST_URL__ /content/images/wordpress/2016/09/stopwu-1024x413-1-300x121.png 300w, __GHOST_URL__ /content/images/wordpress/2016/09/stopwu-1024x413-1-768x310.png 768w" sizes="(max-width: 1024px) 100vw, 1024px"></a></figure>

Druhou a rychlejší možností je skrze **Win + R** či příkazový řádek ( **cmd** ) spustit příkaz:

    net stop wuauserv

Ve chvíli kdy je služba zastavena, můžete začít manuálně instalovat vámi stažené aktualizace. Pokud se i stažená aktualizace zastaví na „vyhledávaní aktualizací“, tak počítač restartujte a postup se zastavením služby opakujte.

**Pozn.** Pokud se zobrazí hlášení&nbsp;„Tato aktualizace není použitelná pro váš počítač“, překontrolujte jestli již není nainstalována.

Poté co jsou vámi stažené aktualizace manuálně nainstalovány, (se předpokládá restart počítače) by měli být zbylé aktualizace skrze Windows Update již korektně vyhledány do několika minut.

<figure class="wp-block-image"><a href="http://192.168.20.2/wordpress/wp-content/uploads/2016/09/aktf.png"><img decoding="async" loading="lazy" width="995" height="594" src="http://192.168.20.2/wordpress/wp-content/uploads/2016/09/aktf.png" alt="" class="wp-image-4361" srcset=" __GHOST_URL__ /content/images/wordpress/2016/09/aktf.png 995w, __GHOST_URL__ /content/images/wordpress/2016/09/aktf-300x179.png 300w, __GHOST_URL__ /content/images/wordpress/2016/09/aktf-768x458.png 768w" sizes="(max-width: 995px) 100vw, 995px"></a></figure>

**Nevím jak dlouho tento postup bude funkční!**

_Omlouvám se za sníženou kvalitu snímků obrazovky, pro účely tohoto článku jsem postup ještě jednou testoval na vzdáleném počítači._

<!--kg-card-end: html-->