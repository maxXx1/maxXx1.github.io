---
title: "Windows 11 - původní kontext menu a explorer"
date: "2024-07-03"
tags: 
  - "Widnows-11"
category: "Windows"
image: 
  path: "/img/2024-07-03-windows11-kontext-explorer/Windows-11-vs-Windows-10.jpg"
  alt: "Windows 11 vs. Windows 10"
---

Windows 11 přináší vícero změn v uživatelském rozhraní systému. Zjednodušilo se kontextové menu, které zobrazuje pouze několik pevných položek v závislosti na typu souboru. Změnil se také explorer. Původní kontextové menu lze prozatím vyvolat možností __Zorazit dlaší možnosti__, ale málokdo ví, že se v systému ukrývá také původní průzkumník.
Pokud vám tedy nebude vadit, že tyto věci nebudou úplně designově zapadat do systému, tak se můžete vrátit k plné kontextové nabídce a exploreru z Windows 10.

## Původní kontextové menu

Zde je dvojice příkazů, která aktivuje původní kontextové menu se všemi možnostmi, pomocí vytvoření klíče v registru a příkaz, který vrátí nové kontextové menu, tím, že klíč v registru smaže.

- Spusťte si Powerhell jako správce a zadejte následující příkaz:

### Kontextové menu z Windows 10
```powershell
reg.exe add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve
```

### Kontextové menu z Windows 11
```powershell
reg.exe delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f
```

- Aby se změny projevily, tak je třeba restartovat explorer
  - Stiskněte `Ctrl` + `Shift` + `Esc`
  - V task manageru vleledejte proces `Explorer.exe`
  - Klik druhým tlačítkem a __Restartovat__

![ps](/img/2024-07-03-windows11-kontext-explorer/powershell.png)

## Půvondní explorer

Opět dvojice příkazů, která vrací do hry původní explorer z Windows 10, pomocí tvorby klíče v registru a příkaz který vrací nový exporer z Windows 11, smazáním onoho klíče.

- Spusťte si Powerhell jako správce a zadejte následující příkaz:

### Explorer z Windows 10
```powershell
reg.exe add "HKCU\Software\Classes\CLSID\{d93ed569-3b3e-4bff-8355-3c44f6a52bb5}\InprocServer32" /f /ve
```

### Explorer z Windows 11
```powershell
reg.exe delete "HKCU\Software\Classes\CLSID\{d93ed569-3b3e-4bff-8355-3c44f6a52bb5}" /f
```

- Aby se změny projevily, tak je třeba restartovat explorer
  - Stiskněte `Ctrl` + `Shift` + `Esc`
  - V task manageru vleledejte proces `Explorer.exe`
  - Klik druhým tlačítkem a __Restartovat__

![taskmanager](/img/2024-07-03-windows11-kontext-explorer/taskmanager.png)
