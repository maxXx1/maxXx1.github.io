---
layout: post
title: Counter Strike 1.6 Android port
tags:
- android
- hash-wordpress
- hash-import-2023-08-28-13-25
---

Dneska bych vám rád ukázal jak spustit Counter Strike 1.6 na Androidu. Vzhledem k tomu, že konečně vyšel funkční klient pro jedno-jádrové i více-jádrové zařízení s Androidem. Za tímto klientem stojí vývojář&nbsp;Alibek Omarev, který svůj výtvor zveřejnil na [GitHub](https://github.com/a1batross)u.

Dotykové ovládání je sice hodně nepohodlné, ale s [kompatibilním ovladačem](https://steelseries.com/gaming-controllers) proměníte váš telefon v perfektní přenosnou konzoli.

<iframe loading="lazy" title="Counter Strike 1.6 Android Gameplay :)" width="600" height="338" src="https://www.youtube.com/embed/EWx6_jLia4Y?feature=oembed" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Co k tomu budeme potřebovat:

1. Zakoupenou hru v rámci [Steam](http://store.steampowered.com/app/10/)u (nebo její originální soubory)
2. Povolit na Androidu instalaci z neznámých zdrojů  
(Nastavení – Zabezpečení – Neznáme zdroje)
3. Cca. 700MB volného místa na SDkartě.

### Postup:

1. Stáhněte a nainstalujte klienta (v1.01)
  - Pro [jedno-jádrové zařízení](https://github.com/SDLash3D/cs16-client/releases/download/v1.01/cs16-client-release-noomp.apk) (onomp)
  - **Pro [více-jádrové zařízení](https://github.com/SDLash3D/cs16-client/releases/download/v1.01/cs16-client-release-omp.apk)** (omp)
2. Stáhněte a nainstalujte engine&nbsp;[Xash3D](https://github.com/SDLash3D/xash3d-android-project/releases/download/v0.17.1/xash3d-android-0.17.1.apk) (v0.17.1)
3. Vytvořte na vaší SDkartě složku „ **xash** „a nakopírujte do ní složky „ **cstrike** “ a „ **valve** “ ze složky s hrou&nbsp;(_…\Steam\steamapps\common\Half-Life_).
4. Nyní již pouze stačí spustit „ **CS16Client** “ a dát „Launch CS16-CLIENT!“

### Poznatky:

- Lze přizpůsobit citlivost dotykového nastavení.
- Lze přesunout či skrýt ovládací prvky.
- Na prázdné mapě stabilních 60FPS (testováno na telefonu Lenovo S60-a).
- Funkční ZBoti a YaPB boti (nastavení skrze konzoli).
- Vyhledalo to i nějaké servery v rámci internetu (lol 😀 )
- Možno nastavit&nbsp;spouštěcí&nbsp;příkazy (stejně jako v práci steamu).

&nbsp;

<!--kg-card-end: html-->