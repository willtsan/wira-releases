<div align="center">

<img src="logo.png" alt="Wirá logo" width="160">

# Wirá

**A multi-system retro emulator, built from scratch in Flutter.**

*Wirá* (wee-RAH) means **bird** in Tupi/Nheengatu: a nod to Brazil 🇧🇷 and to Dash, Flutter's bird.

*Built with AI assistance: see the [disclaimer](#-ai-disclaimer).*

[![Website](https://img.shields.io/badge/Website-wira-2e8b8b?style=for-the-badge&logo=googlechrome&logoColor=white)](https://willtsan.github.io/wira-site/)
[![Latest release](https://img.shields.io/github/v/release/willtsan/wira-releases?style=for-the-badge&color=2e8b8b)](https://github.com/willtsan/wira-releases/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/willtsan/wira-releases/total?style=for-the-badge&color=7cb342)](https://github.com/willtsan/wira-releases/releases)
[![Patreon](https://img.shields.io/badge/Patreon-Wir%C3%A1%20Beta-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://www.patreon.com/cw/wira_emulator)
[![Discord](https://img.shields.io/badge/Discord-Join-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/7HGbFRed7X)
[![X](https://img.shields.io/badge/X-@wiraemulator-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/wiraemulator)
[![Buy me a coffee](https://img.shields.io/badge/Buy%20me%20a%20coffee-FFDD00?style=for-the-badge&logo=buymeacoffee&logoColor=black)](https://buymeacoffee.com/willtsan)

[**🌐 Website**](https://willtsan.github.io/wira-site/) · [**⬇️ Download**](https://github.com/willtsan/wira-releases/releases/latest) · [**🎮 Compatibility**](https://willtsan.github.io/wira-site/compatibility/) · [**🐛 Report a bug**](https://github.com/willtsan/wira-releases/issues) · [**💬 Discord**](https://discord.gg/7HGbFRed7X)

</div>

---

## ✨ What is Wirá?

Wirá plays your favorite classic consoles in one app, with one library. Every emulation core is written from scratch in Dart, so there are no libretro cores and no native emulation code. It runs on **Android** for now, other platforms will come later.

This repository hosts the **release builds**. Everything else lives on the **[website](https://willtsan.github.io/wira-site/)** ([em português](https://willtsan.github.io/wira-site/pt-br/)):

| | |
|---|---|
| 🎮 **[Systems](https://willtsan.github.io/wira-site/systems/)** | Every system Wirá emulates: file types, BIOS needs and what each core supports |
| ✅ **[Compatibility](https://willtsan.github.io/wira-site/compatibility/)** | How games run, system by system. Played something? [Report a game](https://github.com/willtsan/wira-releases/issues/new?template=compat.yml&title=%5BCompat%5D%20) |
| ⬇️ **[Download](https://willtsan.github.io/wira-site/download/)** | The latest build with its checksum, every release, and how to join Wirá Beta |
| 📰 **[News](https://willtsan.github.io/wira-site/news/)** | Release notes and announcements |

<table>
<tr>
<td width="50%"><img src="screenshot0.jpeg" alt="Welcome screen: continue playing, recent games and your stats"><br><sub>Welcome screen: continue playing, recent games and your stats</sub></td>
<td width="50%"><img src="screenshot1.jpeg" alt="Library lanes: Playing, Up next, Random picks and more"><br><sub>Library lanes: Playing, Up next, Random picks and more</sub></td>
</tr>
</table>

More screenshots and the full feature list are on the [website](https://willtsan.github.io/wira-site/).

## 📦 Installation

1. Open the [latest release](https://github.com/willtsan/wira-releases/releases/latest).
2. Download the `.apk` (Android 7 or later, 64-bit ARM: practically every phone and handheld of the last years).
3. Install it, open Wirá, and point it to your ROMs folder.

> [!IMPORTANT]
> Wirá does **not** include any ROMs or BIOS files. Please use your own legally obtained copies. Each system's page on the [website](https://willtsan.github.io/wira-site/systems/) says which BIOS it needs, if any. Add BIOS files with **Import BIOS** in Wirá's system settings, or put them in its `bios` folder.

## 🧪 Wirá Beta

The standard Wirá is free, and it will stay free. New features land first in **Wirá Beta**, an early-access build for supporters on [Patreon](https://www.patreon.com/cw/wira_emulator).

> [!NOTE]
> **Everything in the beta comes to the standard version.** Patreon pays for test devices, servers and development time; it doesn't lock features away.

**In the beta right now:** 🪐 [Sega Saturn](https://willtsan.github.io/wira-site/systems/saturn/) · 💿 [PlayStation](https://willtsan.github.io/wira-site/systems/ps1/) · 🕹️ [PC Engine CD-ROM²](https://willtsan.github.io/wira-site/systems/pce/) · 🔺 N64 on Vulkan · 🌐 Netplay over Wi-Fi or the internet · ⚡ Rollback on NES, SNES, Mega Drive, Master System and Neo Geo · 🎮 Other phones as remote controllers.

[How to join](https://willtsan.github.io/wira-site/download/#beta): join the beta tier on Patreon, accept the Firebase App Distribution invite by email, and install Wirá Beta from Google's App Tester app. It's a separate app (`com.willtsan.wira.beta`) with its own library, settings and saves.

## 🚀 Launching from other apps (Android)

Frontends like **ES-DE**, **Daijisho** or **Beacon** can start a game directly with an explicit Intent:

| | |
|---|---|
| Package | `com.willtsan.wira` |
| Activity | `com.willtsan.wira.MainActivity` |
| Extra `rom` (string) | Absolute file path of the ROM (required) |
| Extra `core` (string) | Optional: `nes`, `snes`, `n64`, `gb`, `gbc`, `gba`, `sms`, `gg`, `md`, `neo`, `ngp`, `a26`, `chip8` |

<details>
<summary><b>Details and tips</b></summary>

- **Data URI:** instead of the `rom` extra, the path can be the Intent's data URI (`-d /path/rom.sfc` or `file:///path/rom.sfc`).
- **`core` extra:** case-insensitive. Any extension a system opens also works (`sfc`, `smc`, `gen`, `ngc` and so on). If it's missing, unknown, or shared by two systems (`bin`), the system is detected from the ROM.
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

- **A game runs well or badly?** [Report it](https://github.com/willtsan/wira-releases/issues/new?template=compat.yml&title=%5BCompat%5D%20) for the [compatibility list](https://willtsan.github.io/wira-site/compatibility/).
- **Found a bug?** [Open an issue](https://github.com/willtsan/wira-releases/issues) with the system, the game and what you expected to happen.
- **Just want to chat?** Come to [Discord](https://discord.gg/7HGbFRed7X), where beta news and requests happen too.

## 🤖 AI disclaimer

Wirá and its emulation cores are developed with AI assistance for code generation and opcode translation, while the system architecture, debugging, memory layout, and overall project management are fully human-driven.

## 💚 Support

Wirá is made in spare time. If you enjoy it:

- **[Patreon](https://www.patreon.com/cw/wira_emulator)**: support it monthly and get [Wirá Beta](#-wirá-beta).
- **[Buy me a coffee](https://buymeacoffee.com/willtsan)**: a one-off thank you.

Using the standard version and reporting bugs helps just as much. Thank you! 💚

---

<div align="center">
<sub>Made with 💙 in Portugal by a brazilian, using Flutter.</sub>
</div>
