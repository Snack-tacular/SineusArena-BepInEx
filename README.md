# Sineus Arena - BepInEx 6 (IL2CPP)

[![BepInEx](https://img.shields.io/badge/BepInEx-6.0.0--pre.2-blue.svg)](https://github.com/BepInEx/BepInEx)
[![Unity Version](https://img.shields.io/badge/Unity-6000.4.1f1%20IL2CPP-black.svg)](https://unity.com/)
[![Game](https://img.shields.io/badge/Game-Sineus%20Arena%20Survivors-orange.svg)](https://store.steampowered.com/app/4227400/Sineus_Arena_Survivors/)

Pre-configured, drop-in **BepInEx 6 (IL2CPP x64)** setup tailored specifically for **Sineus Arena Survivors**.

Normally, running BepInEx on Sineus Arena fails or hangs during startup due to the game running on **Unity 6 (6000.4.1f1)** with IL2CPP, where Cpp2IL / Il2CppInterop assembly generation requires specific base libraries and patches. This repository provides an already tested, pre-generated interop environment so you can jump straight into installing and developing mods without assembly generation headaches.

---

## 📦 Downloads

Grab the latest ready-to-use package from the **[Releases Page](https://github.com/Snack-tacular/SineusArena-BepInEx/releases)**:

- **[SineusArena-BepInEx-v6.0.0-Full.zip](https://github.com/Snack-tacular/SineusArena-BepInEx/releases/latest)** *(Recommended for players)*: Complete plug-and-play package including `BepInEx`, `dotnet` (CoreCLR runtime), `doorstop_config.ini`, and `winhttp.dll`.
- **[SineusArena-BepInEx-v6.0.0-FolderOnly.zip](https://github.com/Snack-tacular/SineusArena-BepInEx/releases/latest)**: Just the pre-configured `BepInEx` directory if you already have Doorstop and CoreCLR installed.

---

## ⚡ Features & Why This Build?

- **Pre-generated IL2CPP Interop Assemblies**: Contains complete, functional interop assemblies for Unity 6000.4.1f1 and Sineus Arena game code (`Assembly-CSharp.dll`, `UnityEngine.CoreModule.dll`, etc.).
- **Optimized Configuration**: `BepInEx.cfg` is pre-configured with `UpdateInteropAssemblies = false` to prevent slow startup times and avoid breaking existing assemblies.
- **Pre-bundled Unity Base Libraries**: Includes `unity-libs/6000.4.1.zip` matching the exact engine version of Sineus Arena.
- **Mod-Ready**: Comes with `BepInEx/plugins/` ready for immediate mod installation.

---

## 🚀 Installation Guide

1. Download **`SineusArena-BepInEx-v6.0.0-Full.zip`** from the [Releases](https://github.com/Snack-tacular/SineusArena-BepInEx/releases) tab.
2. Locate your **Sineus Arena** installation directory.
   - Typically:
     ```
     C:\Program Files (x86)\Steam\steamapps\common\Sineus Arena\
     ```
   - (In Steam: Right-click **Sineus Arena** > **Manage** > **Browse local files**).
3. Extract the contents of the ZIP archive directly into your game folder so the files align with `SineusArena.exe`.

Your game directory should look like this:

```text
Sineus Arena/
├── BepInEx/
│   ├── cache/
│   ├── config/
│   │   └── BepInEx.cfg
│   ├── core/
│   ├── interop/
│   ├── patchers/
│   ├── plugins/              <-- Place your mod DLLs here!
│   └── unity-libs/
├── dotnet/                   (CoreCLR runtime)
├── doorstop_config.ini       (Doorstop boot configuration)
├── winhttp.dll               (Doorstop proxy loader)
├── SineusArena.exe
└── SineusArena_Data/
```

4. Launch the game normally via Steam. BepInEx will automatically load!

---

## 🎮 Installing Mods

To install mods:
1. Download the mod DLL file (e.g. `DPSMeter.dll`).
2. Place the DLL into:
   ```text
   Sineus Arena/BepInEx/plugins/
   ```
3. Launch the game.

### Compatible Mods for Sineus Arena
Check out these mods designed for Sineus Arena:
- [PowerupMinimap](https://github.com/Snack-tacular/PowerupMinimap) — Live powerup icons on the minimap overlay.
- [DPSMeter](https://github.com/Snack-tacular/DPSMeter) — Real-time damage and DPS breakdown with character skin icons.
- [ObjectTrackerMod](https://github.com/Snack-tacular/ObjectTrackerMod) — Real-time on-screen tracker for map objects and chests.
- [QuestTrackerMod](https://github.com/Snack-tacular/QuestTrackerMod) — In-game quest tracker with progress and pinning.
- [ZoomOutMod](https://github.com/Snack-tacular/ZoomOutMod) — Customizable camera zoom out distance.
- [MonsterHPBars](https://github.com/Snack-tacular/MonsterHPBars) — Overhead health bars for enemies.
- [ModSettingsMenu](https://github.com/Snack-tacular/ModSettingsMenu) — In-game UI settings menu for configuring mods.
- [TowerStatsMod](https://github.com/Snack-tacular/TowerStatsMod) — Real-time tower DPS and kill counts.
- [buildingleveldisplay](https://github.com/Snack-tacular/buildingleveldisplay) — Building current and max level indicators.
- [ChestWindowMove](https://github.com/Snack-tacular/ChestWindowMove) — Repositioned and cleaned up chest selection window.

---

## 🛠 For Mod Developers

If you are developing C# mods for Sineus Arena using BepInEx 6 IL2CPP:
1. Add references in your `.csproj` to the generated assemblies located in `BepInEx/interop/` (e.g. `Assembly-CSharp.dll`, `Il2Cppmscorlib.dll`, `UnityEngine.CoreModule.dll`).
2. Add references to `BepInEx.Core.dll` and `BepInEx.Unity.IL2CPP.dll` in `BepInEx/core/`.
3. Target `.NET 6.0` (`net6.0`).
4. Inherit from `BasePlugin` and implement your mod logic.

---

## 📄 License & Credits

- [BepInEx](https://github.com/BepInEx/BepInEx) is developed by the BepInEx team under the LGPL-2.1 license.
- [Il2CppInterop](https://github.com/BepInEx/Il2CppInterop) is developed by Samboy063 and contributors under the LGPL-3.0 license.
- Setup and maintenance by [Snack-tacular](https://github.com/Snack-tacular).
