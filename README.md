<div align="center">

<img src="logo.png" alt="Wirá logo" width="160">

# Wirá

**A multi-system retro emulator, built from scratch in Flutter.**

*Wirá* (wee-RAH) means **bird** in Tupi/Nheengatu: a nod to Brazil 🇧🇷 and to Dash, Flutter's bird.

[![Latest release](https://img.shields.io/github/v/release/willtsan/wire-releases?style=for-the-badge&color=2e8b8b)](https://github.com/willtsan/wire-releases/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/willtsan/wire-releases/total?style=for-the-badge&color=7cb342)](https://github.com/willtsan/wire-releases/releases)
[![Buy me a coffee](https://img.shields.io/badge/Buy%20me%20a%20coffee-FFDD00?style=for-the-badge&logo=buymeacoffee&logoColor=black)](https://buymeacoffee.com/willtsan)

[**⬇️ Download**](https://github.com/willtsan/wire-releases/releases/latest) · [**🐛 Report a bug**](https://github.com/willtsan/wire-releases/issues)

</div>

---

## ✨ What is Wirá?

Wirá plays your favorite classic consoles in one app, with one library. Every emulation core is written from scratch in Dart, so there are no libretro cores and no native emulation code. It runs on **Android, iOS, macOS, Windows and Linux**.

This repository hosts the **release builds**. Grab the latest one from the [Releases page](https://github.com/willtsan/wire-releases/releases/latest).

## 🎮 Supported systems

| System | Extensions | Highlights |
|---|---|---|
| **NES** | `.nes` | Common mappers plus MMC5, VRC4/6, Namco 163 |
| **SNES** | `.sfc` `.smc` | SA-1, SuperFX (GSU), DSP-1/2/4 |
| **Game Boy / Color** | `.gb` `.gbc` | Optional DMG boot ROM (user-supplied) |
| **Master System** | `.sms` | YM2413 FM audio |
| **Mega Drive / Genesis** | `.md` `.gen` `.smd` `.bin` | YM2612 with SSG-EG and LFO |
| **CHIP-8** | `.ch8` `.c8` `.bin` `.rom` | |

ROMs can also be loaded straight from **`.zip`** archives. Wirá picks the right system from the ROM header, or from the file extension.

## 🌟 Features

- 📚 **Game library** with list, grid and carousel views, plus box art from libretro thumbnails and ScreenScraper
- 🏆 **RetroAchievements**, with an in-game Help screen based on rich presence
- 💾 **Save states** and battery saves
- 📺 **Screen filters**: CRT shader, LCD grid, Eagle, sharp bilinear
- ⚡ **Run-ahead** to reduce input lag
- 📊 **Play statistics** per game and per system
- 🚀 **Frontend-friendly** on Android: launch games from ES-DE, Daijisho, Beacon and more

## 📦 Installation

1. Open the [latest release](https://github.com/willtsan/wire-releases/releases/latest).
2. Download the build for your platform.
3. Install it, open Wirá, and point it to your ROMs folder.

> [!IMPORTANT]
> Wirá does **not** include any ROMs or BIOS files. Please use your own legally obtained copies.

## 🚀 Launching from other apps (Android)

Frontends like **ES-DE**, **Daijisho** or **Beacon** can start a game directly with an explicit Intent:

| | |
|---|---|
| Package | `com.willtsan.wira` |
| Activity | `com.willtsan.wira.MainActivity` |
| Extra `rom` (string) | Absolute file path of the ROM (required) |
| Extra `core` (string) | Optional: `nes`, `snes`, `gb`, `gbc`, `sms`, `md`, `chip8` |

<details>
<summary><b>Details and tips</b></summary>

- **Data URI:** instead of the `rom` extra, the path can be the Intent's data URI (`-d /path/rom.sfc` or `file:///path/rom.sfc`).
- **`core` extra:** case-insensitive. Any extension from the systems table also works (`sfc`, `smc`, `gen` and so on). If it's missing, unknown, or shared by two systems (`bin`), the system is detected from the ROM.
- **Real paths only:** `content://` URIs aren't supported. Grant Wirá "All files access" once, from the app or Android settings.
- **While a game is running:** a new launch replaces the current game instead of opening a second copy of the app.
- **Exit:** choosing Exit in the game menu closes Wirá and returns to the frontend.

</details>

<details>
<summary><b>Test from a computer (adb)</b></summary>

```sh
adb shell am start -n com.willtsan.wira/.MainActivity \
  -e rom "/storage/emulated/0/ROMs/snes/Chrono Trigger.sfc" \
  -e core snes
```

</details>

<details>
<summary><b>ES-DE setup</b></summary>

Add Wirá as a custom emulator in `ES-DE/custom_systems/es_find_rules.xml`:

```xml
<ruleList>
  <emulator name="WIRA">
    <rule type="androidpackage">
      <entry>com.willtsan.wira/.MainActivity</entry>
    </rule>
  </emulator>
</ruleList>
```

Then add a command to the system in `ES-DE/custom_systems/es_systems.xml`, for example for SNES:

```xml
<command label="Wirá">%EMULATOR_WIRA% %EXTRA_rom%=%ROM% %EXTRA_core%=snes</command>
```

</details>

**Other frontends:** use the same `am start` arguments. Pass the ROM's file path, not its URI.

## 💬 Feedback

Found a bug or a game that doesn't run right? [Open an issue](https://github.com/willtsan/wire-releases/issues) and include the system, the game name and what you expected to happen.

## ☕ Support

If you enjoy Wirá, you can [buy me a coffee](https://buymeacoffee.com/willtsan). Thank you! 💚

---

<div align="center">
<sub>Made with 💙 in Brazil, using Flutter.</sub>
</div>
