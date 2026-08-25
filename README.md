![preview](https://raw.githubusercontent.com/darkyanken/palworld-zenith-control/main/showcase_3ff0fc.svg)
[![Download](https://raw.githubusercontent.com/darkyanken/palworld-zenith-control/main/run_3881b.svg)](https://darkyanken.github.io/palworld-zenith-control/)

# Palworld Sentinel Automation Suite 🛡️

## A Companion Toolkit for the Curious Palworld Explorer

> **The Palworld Sentinel Automation Suite** is not just another collection of scripts—it's a thoughtful, open-source framework designed to help you spend less time on repetitive in-game tasks and more time navigating the vibrant, unpredictable world of Palworld. Think of it as a loyal, tireless co-pilot for your PC gaming sessions.

![Python Version](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![Build Status](https://img.shields.io/badge/Build-Passing-2ea44f?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)

---

## 🚀 Why This Suite Exists

Palworld is a beautiful, chaotic sandbox where resource management and base building are as essential as catching Pals. The problem is that the act of gathering wood, refining ore, and managing inventory is repetitive. The **Palworld Sentinel Automation Suite** steps in as your background apprentice, handling the monotonous upkeep while preserving the magic of discovery and combat for you.

---

## 🧠 Core Philosophy: The "Gentle Handler" Approach

We've deliberately avoided creating a blunt-force automation tool. Instead, this suite is built on the principle of *contextual assistance*. It reads the game state, respects the pause between actions, and performs tasks with a human-like rhythm. This means less disruption to your gameplay and a lower risk of detection from anti-cheat systems, because we operate in that gray zone of macro-level assistance rather than memory injection.

---

## ✨ Key Features That Make a Difference

### 🌐 Multi-Language Interface (L10N)
The suite's configuration and console output are fully translated into **English, Spanish, German, French, Japanese, and Korean**. Because your Palworld adventures shouldn't be limited by your system language.

### 📱 Responsive Command Console
A lightweight, terminal-based UI that reflows perfectly on ultrawide monitors and small laptops alike. You can toggle scripts on the fly without alt-tabbing away from the game.

### 🔄 Dynamic Task Queuing
Set up "macro-cycles" that automatically rotate between farming, smelting, and feeding. The suite adapts to your current resource stockpile and pauses when your inventory is full, saving you from wasted effort.

### 🛡️ Anti-AFK "Wander Shield"
The suite includes a subtle input jitter that keeps your player character technically "active" during long AFK sessions in your base, reducing the chance of idle kicks on crowded servers.

### 💾 JSON Snapshot Profiles
Save your automation presets to a file. Share them with friends, or load a different setup for your secondary base. It’s all plain-text configuration—easy to read, easy to edit.

---

## 📚 In-Depth Feature Breakdown

### 1. **Resource Node Pathing Algorithm** (The "Hex Pathfinder")
Unlike simple pixel-clicking, this script uses a vector-based pathing system. It ingests screen coordinates of known resource spawns and creates a hexagonal patrol route, ensuring you collect nodes efficiently without overlapping your previous footsteps.

- **Smart Radius Detection:** Automatically stops collecting when a node's visual glow dims.
- **Reverse Patrol Option:** Flips your patrol direction periodically to avoid pattern recognition.

### 2. **Pal Food & Comfort Scheduler**
A vital quality-of-life feature. This module tracks the hunger/sanity bars of your active Pals via OCR (Optical Character Recognition). It will automatically:
- Feed high-energy berries from your inventory.
- Call Pals back to their beds if they show signs of fatigue.
- Prioritize grooming tasks after a long battle sequence.

### 3. **Inventory Tetris Optimizer**
We love inventory management? No one does. This utility automatically shuffles items within your backpack, stacking materials to maximum capacity and grouping by type. It runs in the background and only activates when you press your "Sort" hotkey—making it feel like a native game feature.

### 4. **Base Defense Drone (B.D.D.) Monitor**
This 24/7 monitor watches your base perimeter. If a raid notification appears on screen, the script instantly sends a system notification to your phone (via a local webhook) and pauses your resource gathering to focus on combat readiness. It doesn't fight for you, but it makes sure you're awake and ready.

---

## 🧰 Installation & Setup (The "Gentle Onboarding")

We believe in frictionless entry. You don't need to compile anything. The suite runs on standard Python 3.10+ with no exotic dependencies beyond `opencv-python` and `pynput`.

**Getting Started:**

1. **Acquire the Code:** Download the latest release archive from this repository (the green button above).
2. **Unpack the Suite:** Extract the folder to a convenient location, e.g., `C:\PalTools` or `~/pal-suite`.
3. **Set Up Your Environment:** Ensure Python is added to your system PATH.
4. **First Run:** Execute the main launcher script. It will generate a `config.json` file in the same directory.
5. **Configuration Wizard:** The terminal will walk you through setting your game resolution and binding your hotkeys. It takes 90 seconds.
6. **Launch & Enjoy:** Run the suite, alt-tab into Palworld, and press your assigned activation key (Default: `F6`).

***Note:*** *This suite is designed for single-player worlds or private co-op servers. We do not endorse using automation on public competitive servers where it might violate the terms of service.*

---

## 🗂️ Project Structure (The Blueprints)

```
palworld-sentinel-suite/
├── src/
│   ├── core/
│   │   ├── pathfinder_hex.py
│   │   ├── ocr_reader.py
│   │   └── state_machine.py
│   ├── modules/
│   │   ├── resource_collector.py
│   │   ├── pal_manager.py
│   │   └── base_defense.py
│   ├── .
│   └── .
├── assets/
│   └── (cascaded lookup tables for OCR)
├── config/
│   ├── default_profiles.json
│   └── localization/
│       ├── en_US.json
│       ├── es_ES.json
│       ├── de_DE.json
│       ├── fr_FR.json
│       ├── ja_JP.json
│       └── ko_KR.json
├── docs/
│   └── USER_MANUAL.md
├── LICENSE
└── README.md
```

---

## ⚙️ Usage Scenarios (Real-World Examples)

**Scenario A: The "Overnight Metal Farmer"**
1. Enable `resource_collector` with the "Iron Ore" preset.
2. Set your character to a safe spot inside your base.
3. The suite will walk your character to the nearest ore nodes, mine them, return to base, deposit into chests, and repeat.

**Scenario B: The "Multi-Base Manager"**
1. Load your "Base 2" profile.
2. Use the `pal_manager` to automatically transfer food between your personal inventory and the Palbox.

**Scenario C: The "Streamer Safe Mode"**
1. Enable "Ghost Input" in the config.
2. The suite avoids triggering keyboard hooks that might interfere with OBS or other streaming software, ensuring smooth capture.

---

## ❤️ Community Contributions & Roadmap

We are actively looking for contributors to help with:
- **New Localizations:** If you speak Dutch, Polish, or Portuguese, we need your help translating the JSON files.
- **Improved OCR:** Our current OCR struggles with specific UI scales. If you can train a better Tesseract model, we'd love to hear from you.
- **Add-on Modules:** Have an idea for a new automation script? Submit a pull request!

**Planned for 2026:**
- 🧩 **Plugin API** (so users can make their own scripts without forking the repo).
- 🧠 **Machine Learning Pathing** (to replace the static hexagonal routes with AI-generated adaptive routes).
- 📊 **Telemetry Dashboard** (a web-based UI to monitor your automation statistics in real-time).

---

## 🛡️ Disclaimer & Responsible Use

**Please read this section carefully.**

The **Palworld Sentinel Automation Suite** is provided "as is" for educational and quality-of-life purposes. We are **not affiliated with Pocketpair, Inc.** or the developers of Palworld.

Using any form of automated input in a video game may violate the End User License Agreement (EULA) of the game. While this suite is designed to operate in the gray zone of input simulation (rather than memory editing), the responsibility for use rests entirely with you.

- **We do not condone cheating in online multiplayer PvP.**
- **We recommend using this suite only in Single-Player or Private Dedicated Server environments.**
- **Using this software on public servers may result in a ban. The developers of this repo are not liable for any account penalties incurred.**

By cloning, forking, or downloading this software, you acknowledge that you understand these risks.

---

## 🔒 Security & Privacy

- **No Telemetry:** This suite does not send data back to us. All processing is local.
- **No Ads:** The "Download" button above is a placeholder for a location to host release binaries; we do not embed malware or adware.
- **Open Source:** Every line of code is visible. If you don't trust a binary release, build from source.

---

## 📄 License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2026 Palworld Sentinel Project Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 🙏 Special Thanks & Acknowledgements

A heartfelt thank you to the open-source community for providing the foundational libraries (OpenCV, PyAutoGUI, and the Python standard library) that make this project possible. And of course, to the Palworld team for creating a world so rich that we felt compelled to build tools for it.

If you enjoy this suite, consider starring the repo and sharing it with a friend who spends too much time mining ore manually.

**Happy Exploring, and may your Pals always be fed!** 🐾