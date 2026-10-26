<div align="center">

<img src="logo.png" alt="Wirá logo" width="160">

# Wirá

**A multi-system retro emulator, built from scratch in Flutter.**

*Wirá* (wee-RAH) means **bird** in Tupi/Nheengatu: a nod to Brazil 🇧🇷 and to Dash, Flutter's bird.

*Built with AI assistance: see the [disclaimer](#-ai-disclaimer).*

[![Latest release](https://img.shields.io/github/v/release/willtsan/wira-releases?style=for-the-badge&color=2e8b8b)](https://github.com/willtsan/wira-releases/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/willtsan/wira-releases/total?style=for-the-badge&color=7cb342)](https://github.com/willtsan/wira-releases/releases)
[![Patreon](https://img.shields.io/badge/Patreon-Wir%C3%A1%20Beta-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://www.patreon.com/cw/wira_emulator)
[![Discord](https://img.shields.io/badge/Discord-Join-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/7HGbFRed7X)
[![Buy me a coffee](https://img.shields.io/badge/Buy%20me%20a%20coffee-FFDD00?style=for-the-badge&logo=buymeacoffee&logoColor=black)](https://buymeacoffee.com/willtsan)

[**⬇️ Download**](https://github.com/willtsan/wira-releases/releases/latest) · [**🧪 Wirá Beta**](#-wirá-beta) · [**🐛 Report a bug**](https://github.com/willtsan/wira-releases/issues) · [**💬 Discord**](https://discord.gg/7HGbFRed7X)

</div>

---

## ✨ What is Wirá?

Wirá plays your favorite classic consoles in one app, with one library. Every emulation core is written from scratch in Dart, so there are no libretro cores and no native emulation code. It runs on **Android** for now, other platforms will come later.

This repository hosts the **release builds**. Grab the latest one from the [Releases page](https://github.com/willtsan/wira-releases/releases/latest).

## 🧪 Wirá Beta

The standard Wirá is free, and it will stay free. New features land first in **Wirá Beta**, an early-access build for supporters on [Patreon](https://www.patreon.com/cw/wira_emulator), where they get tested on real devices before they reach everyone.

> [!NOTE]
> **Everything in the beta comes to the standard version.** Patreon pays for test devices, servers and development time; it doesn't lock features away. When a feature is ready, it ships in the standard Wirá at no cost.

**In the beta right now:**

| | |
|---|---|
| 🪐 **Sega Saturn** | Early: Virtua Fighter 2 and Sega Rally Championship run at full speed, many other games don't yet. Needs your own `saturn_bios.bin`; plays `.chd`, `.cue` and `.iso`. |
| 🌐 **Netplay** | Two players on the same Wi-Fi or over the internet, with a room code or from the list of open rooms. Up to four on the Nintendo 64. |
| ⚡ **Rollback** | On NES, SNES, Mega Drive, Master System and Neo Geo your buttons answer right away, even with the other player far away. Saturn and N64 netplay wait for the other player instead. |
| 🎮 **Remote controller** | Other phones on your Wi-Fi become controllers for the game on your screen. Only you need the game. |

Some of it is rough: online play connects the phones directly, so it can fail on some mobile networks and strict routers.

**How it works:**

1. Join the beta tier on [Patreon](https://www.patreon.com/cw/wira_emulator).
2. You get an invite by email from Firebase App Distribution (use an address you check).
3. Install **Wirá Beta** from Google's App Tester app, which also brings you each new build.

Wirá Beta is a separate app (`com.willtsan.wira.beta`): it installs next to the standard Wirá, with its own library, settings and saves, so testing never touches your main games.

## 🤖 AI disclaimer

Wirá and its emulation cores are developed with AI assistance for code generation and opcode translation, while the system architecture, debugging, memory layout, and overall project management are fully human-driven.

## 🎮 Supported systems

| System | Extensions | Highlights |
|---|---|---|
| **NES** | `.nes` | Common mappers plus MMC5, VRC4/6, Namco 163 |
| **SNES** | `.sfc` `.smc` | SA-1, SuperFX (GSU), DSP-1/4 |
| **Nintendo 64** | `.z64` `.n64` `.v64` | Up to 2x internal resolution, analog stick, Rumble Pak and Controller Pak, up to four players |
| **Game Boy / Color** | `.gb` `.gbc` | - |
| **Game Boy Advance** | `.gba` `.agb` | Built-in BIOS, real BIOS optional |
| **Master System** | `.sms` | YM2413 FM audio |
| **Game Gear** | `.gg` | Stereo sound |
| **Mega Drive / Genesis** | `.md` `.gen` `.smd` `.bin` | YM2612 with SSG-EG and LFO, 6-button pad, PAL games at 50 Hz |
| **Neo Geo** | `.neo` | Home (AES) and arcade (MVS) boards, picked per game; protected games like Garou, Metal Slug 3/5 and KOF 98-2003 |
| **Neo Geo Pocket / Color** | `.ngp` `.ngc` `.npc` `.ngpc` | Built-in BIOS, sampled voices, C/D buttons for strong attacks |
| **CHIP-8** | `.ch8` `.c8` `.bin` `.rom` | |

ROMs can also be loaded straight from **`.zip`** archives. Wirá picks the right system from the ROM header, or from the file extension.

## 🌟 Features

- 📚 **Game library** with list, grid and carousel views, plus box art from libretro thumbnails and ScreenScraper
- 📦 **3D boxes**, with a generated cover for games that have no scraped art
- 🖼️ **Game details** with every scraped image and manual: replace or remove any of them by hand
- 🏆 **RetroAchievements**, with an in-game Help screen based on rich presence
- 💾 **Save states** and battery saves
- 👆 **Touch controls** with customisable layouts; slide your finger across buttons to run and jump
- 📺 **Screen filters**: CRT shader, scanlines, LCD grid, Eagle, sharp bilinear
- ⚡ **Run-ahead** to reduce input lag
- 📊 **Play statistics** per game and per system
- 🚀 **Frontend-friendly** on Android: launch games from ES-DE, Daijisho, Beacon and more

## 📦 Installation

1. Open the [latest release](https://github.com/willtsan/wira-releases/releases/latest).
2. Download the `.apk` (Android 7 or later, 64-bit ARM: practically every phone and handheld of the last years).
3. Install it, open Wirá, and point it to your ROMs folder.

> [!IMPORTANT]
> Wirá does **not** include any ROMs or BIOS files. Please use your own legally obtained copies.
> Only Neo Geo needs a BIOS: your own `neogeo.zip` (arcade) or `aes.zip` (home console). Game Boy Advance and Neo Geo Pocket use a built-in replacement; for Game Boy Advance you can optionally use your own `gba_bios.bin`. Add BIOS files with **Import BIOS** in Wirá's system settings, or put them in its `bios` folder.

## 🚀 Launching from other apps (Android)

Frontends like **ES-DE**, **Daijisho** or **Beacon** can start a game directly with an explicit Intent:

| | |
|---|---|
| Package | `com.willtsan.wira` |
| Activity | `com.willtsan.wira.MainActivity` |
| Extra `rom` (string) | Absolute file path of the ROM (required) |
| Extra `core` (string) | Optional: `nes`, `snes`, `n64`, `gb`, `gbc`, `gba`, `sms`, `gg`, `md`, `neo`, `ngp`, `chip8` |

<details>
<summary><b>Details and tips</b></summary>

- **Data URI:** instead of the `rom` extra, the path can be the Intent's data URI (`-d /path/rom.sfc` or `file:///path/rom.sfc`).
- **`core` extra:** case-insensitive. Any extension from the systems table also works (`sfc`, `smc`, `gen`, `ngc` and so on). If it's missing, unknown, or shared by two systems (`bin`), the system is detected from the ROM.
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

Add Wirá as a custom emulator in ES-DE/custom_systems/es_find_rules.xml:
```xml
<ruleList>
  <emulator name="WIRA">
    <rule type="androidpackage">
      <entry>com.willtsan.wira/.MainActivity</entry>
    </rule>
  </emulator>
</ruleList>
```

Then add a command to the system in ES-DE/custom_systems/es_systems.xml, for example for SNES:
```xml
<command label="Wirá">%EMULATOR_WIRA% %EXTRA_rom%=%ROM% %EXTRA_core%=snes</command>
```

</details>

Other frontends: use the same am start arguments. Pass the ROM's file path, not its URI.

## 💬 Feedback

Found a bug or a game that doesn't run right? [Open an issue](https://github.com/willtsan/wira-releases/issues) and include the system, the game name and what you expected to happen. Or come say it on [Discord](https://discord.gg/7HGbFRed7X), where beta news, requests and chat happen too.

## 💚 Support

Wirá is made in spare time. If you enjoy it:

- **[Patreon](https://www.patreon.com/cw/wira_emulator)**: support it monthly and get [Wirá Beta](#-wirá-beta).
- **[Buy me a coffee](https://buymeacoffee.com/willtsan)**: a one-off thank you.

Using the standard version and reporting bugs helps just as much. Thank you! 💚

---

<div align="center">
<sub>Made with 💙 in Portugal by a brazilian, using Flutter.</sub>
</div>
