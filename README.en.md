# MCU Map Analyzer

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
![Platform](https://img.shields.io/badge/platform-browser-brightgreen)
![Compilers](https://img.shields.io/badge/compilers-CC--RL%20%7C%20CA78K0R-orange)
![Languages](https://img.shields.io/badge/i18n-14%20languages-blueviolet)
![No Dependencies](https://img.shields.io/badge/dependencies-none-success)

> 🌐 **[日本語版 README](README.md)** | This page is in English

A **map file visualization tool** for the Renesas RL78 family. Loads map files produced by CC-RL / CA78K0R and provides intuitive insight into ROM usage, per-file breakdown, memory layout, mirror area utilization, and diff comparison.

It runs entirely in the browser as a **single HTML file** — easy to distribute, easy to run. Zero server communication, zero dependencies.

🌐 **Demo** ▶ [https://welch-10.github.io/mcu-map-analyzer/](https://welch-10.github.io/mcu-map-analyzer/)

---

## ✨ Features

- 📦 **Single-file distribution** — Just open `MCUMapAnalyzer.html`. No server, install, or build required
- 🔒 **Fully offline** — Files are parsed locally; nothing is sent to any server
- 🌐 **14 languages** — 日本語 / English / 简体中文 / 繁體中文 / 한국어 / Tiếng Việt / ไทย / Bahasa Indonesia / Français / Italiano / Español / Português / Polski / Deutsch
- 🔢 **Locale-aware number formatting** — `1.234,56` (German / Italian / Spanish / Portuguese / Dutch) / `1 234 567` (French / Polish) / `1,234.56` (English / Japanese / Chinese / Korean / Thai) automatically
- 📱 **Mobile friendly** — Works on Android Chrome / iOS Safari
- 🎨 **Intuitive UI** — Big-picture ROM usage and memory layout
- 🔍 **Interactive memory map** — Cursor-anchored zoom on Alt+wheel, file name on hover
- 🪞 **Mirror area utilization visible** — See exactly how much of the RL78 hardware mirror region is occupied, in one screen
- ⚖️ **Diff comparison** — Load two map files side-by-side to see what changed between builds
- 🧪 **Sample analysis** — On the GitHub Pages version, try the anonymized sample (RL78/G23 384KB) with one click

## 🛠 Supported Compilers

| Compiler | Status | Notes |
|---|---|---|
| **CC-RL** | ✅ Supported | For RL78, Renesas Optimizing Linker (rlink) |
| **CA78K0R** | ✅ Supported | For RL78/78K0R, 78K0R Linker |
| CC-RX | 🔍 Detected only | Detection implemented, parser not yet |
| CC-RH | 🔍 Detected only | Detection implemented, parser not yet |

## 📋 Supported Formats

- Extensions: `.map` / `.map.txt` / `.lis`
- Max size: 20 MB
- Encoding: UTF-8 / Shift_JIS (auto-detected)

## 🚀 How to Use

### Option 1: Direct in browser via GitHub Pages (recommended)

Open [https://welch-10.github.io/mcu-map-analyzer/](https://welch-10.github.io/mcu-map-analyzer/) and load a map file.

Click **"Try sample file"** to load the anonymized sample with one click (GitHub Pages version only).

### Option 2: Run locally

1. Download the latest `MCUMapAnalyzer.html` from [Releases](../../releases)
2. Open it in a browser (works on intranet / offline environments)
3. Drag & drop a map file or click "Choose File"

> All processing happens in your browser. Nothing is uploaded.

## 🌍 Supported Browsers

| Browser | Minimum version | Notes |
|---|---|---|
| Chrome / Edge | 90+ | April 2021+ |
| Firefox | 103+ | July 2022+ (backdrop-filter) |
| Safari | 16+ | September 2022+ (`:has()` / `replaceChildren()`) |
| Android Chrome | 90+ | Mobile |
| iOS Safari | 16+ | Mobile |

## 📊 Analysis Features

### Overview
- ROM usage at a glance (capacity, used, remaining, percent)
- Category breakdown donut chart (Code / Const / RFD / Other Lib / System — 5 categories)
- **Hardware mirror area card** — Range, size, mirror source physical addresses, MAA bank inference

### By File
- Per-file size and usage rate
- Stacked bars showing category breakdown
- Filter by file name / category
- ROM usage table (click column headers to sort)
- CSV export (filter-aware, English-locale numbers for stable Excel parsing)

### Memory Map
- Whole ROM range visualized with section placement (virtual scrolling, smooth even with thousands of rows)
- Color by category or by file (toggle)
- Row width selector (auto / 32 B/row … 256 KB/row)
- **Alt+wheel zoom anchored to mouse cursor**
- **File name tooltip on hover**
- Section search and pinning (Esc to clear)
- **Mirror source overlay** — Hatched overlay highlights the physical ROM range that is also readable via F-region mirror

### Compare
- Diff between two map files
- Per-category diff summary (increase/decrease for each of 5 categories)
- Per-file diff table (Increased / Decreased / Added / Removed / Unchanged buckets)
- Auto-detect incompatible cases (compiler mismatch, device mismatch, ROM capacity mismatch, low common-file ratio)
- Diff CSV export

### Raw Data
- Section-total size table
- File × Section breakdown matrix

## 🤝 Contributing

Bug reports, feature requests, and pull requests welcome.

- File issues at [Issues](../../issues)
- Discussion / questions at [Discussions](../../discussions)
- See [CONTRIBUTING.md](CONTRIBUTING.md) before opening a PR

Especially welcome:
- **CC-RX / CC-RH parser implementation**
- Adding more RL78 series to the device DB
- Translation improvements / additional languages
- Screenshots

## 📝 Changelog

See [CHANGELOG.md](CHANGELOG.md)

## ⚖ License

[MIT License](LICENSE)

Copyright (c) 2026 ウェルチ (welch)

Commercial and personal use both permitted under MIT, but **provided AS IS without warranty**.
The author bears no responsibility for any damages arising from use of this tool.

## 📑 Trademarks

CC-RL, CC-RX, CC-RH, CA78K0R, and RL78 are trademarks or registered trademarks
of Renesas Electronics Corporation. This tool is not a Renesas Electronics
product and is not affiliated with or endorsed by Renesas Electronics
Corporation.
