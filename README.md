# acAdvance

<p align="center">
  <img src="https://img.shields.io/badge/platform-SA--MP-2ea44f?style=for-the-badge" alt="SA-MP">
  <img src="https://img.shields.io/badge/MoonLoader-Lua-4169E1?style=for-the-badge" alt="MoonLoader">
  <img src="https://img.shields.io/badge/version-1.3.1-blue?style=for-the-badge" alt="Version">
</p>

<p align="center">
  <b>Client-side anti-cheat for SA-MP</b><br>
  Detects aim assistance in real time — right in your game.
</p>

---

## Overview

**acAdvance** is a MoonLoader script that watches nearby players' aim and shot data, then flags suspicious patterns typical of **smooth** and **silent** aim cheats.

Alerts appear in chat. Optional file logging and an ImGui settings panel keep things simple for admins and regular players alike.

---

## What it detects

| Module | What it looks for |
|--------|-------------------|
| **SMOOTH** | Unnaturally consistent tracking — low error, locked-on motion, aim that “pulls” onto a target too cleanly |
| **SILENT** | Aim direction that does not match the bullet path or weapon cone — classic silent-aim behaviour |

Each hit builds a score. When the score crosses a threshold (with cooldown), you get a warning.

---

## Features

- Live analysis of aim sync and bullet hits  
- Chat alerts with short messages or detailed metrics  
- Optional log file: `moonloader/acAdvance/warnings.log`  
- Settings UI (`/acarp`) — enable/disable, warning style, logging  
- Auto-update from GitHub Releases  

---

## Requirements

- [MoonLoader](https://www.blast.hk/threads/13305/)
- [SAMPFUNCS](https://www.blast.hk/threads/17/) / SAMP.Lua
- [mimgui](https://www.blast.hk/threads/13305/)

---

## Installation

1. Download `acAdvance.lua` from the [latest release](https://github.com/nullusWise/acAdvance/releases/latest).
2. Put it into your `moonloader` folder.
3. Start the game — you should see a load message in chat.

```
moonloader/
└── acAdvance.lua
```

---

## Usage

| Command | Action |
|---------|--------|
| `/acarp` | Open / close the settings window |

**Settings**

- Enable or disable detection without removing the script  
- Warning type: short hint (`possibly uses SILENT/SMOOTH`) or full metrics  
- File logging on/off  

Config is saved to `moonloader/acAdvance/acAdvance.ini`.

---

## Example alerts

```
(AC) PlayerName[42] возможно использует (SILENT)
(AC) PlayerName[42] SILENT aim=12.4 deg > engine=3.1 deg | dBullet=9.8 deg | hit@28m
(AC) PlayerName[17] SMOOTH mean=1.12 deg s=0.41 deg | w=84 deg/s | lock=72% | tgt=35m
```

---

## Disclaimer

This is a **client-side helper**, not a server anti-cheat.  
False positives can happen — treat warnings as a signal to investigate, not as final proof.

---

