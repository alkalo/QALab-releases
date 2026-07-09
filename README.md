# QALab — Desktop Releases

[![Latest release](https://img.shields.io/github/v/release/alkalo/QALab-releases?label=desktop)](https://github.com/alkalo/QALab-releases/releases/latest)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

**Public download page** for the QALab Windows desktop app.

This repository contains **installers only** — no source code. Releases are published here so anyone can download and receive automatic updates without repository access.

---

## What is QALab?

**QALab v2** is a **local-first AI suite for game QA teams**. Everything runs on your PC with [Ollama](https://ollama.com) — no cloud AI, no subscription, no data leaving your machine.

Two modules share one stack:

| Module | What you get |
|--------|----------------|
| **QA Tools** | Six AI workflows: Metrics, Video Analysis, GDD Studio, Test Generator, Test Review, Ticket Auditor |
| **Arion Agent** | Autonomous mobile testing — device runs, live HUD, suite runner, free exploration, bug export |

Plus workspace tools: **Bug Reports**, **Knowledge Base**, **Insights/KPIs**, **Release Advisor**, and **Settings** (Ollama, Jira, TestRail, ADB, builds).

Built for studios that need **privacy, speed, and a full QA department in one installer**.

---

## Typical workflow

```
1. Connect Jira / TestRail (Settings or Insights → Sources)
2. QA Tools — metrics, video UX, GDD, tests, ticket audit
3. Arion — run a suite or free test on a device; watch the live HUD
4. Bug review → validate → export to Jira / Linear
5. Release Advisor + weekly report for leadership
```

Navigation: **Ctrl+K** command palette · light Ibdara theme · AI status in Settings.

---

## Download (Windows 10/11, 64-bit)

**Latest release:** [Releases](https://github.com/alkalo/QALab-releases/releases/latest)

| File | Use |
|------|-----|
| [**QALab-*-Setup.exe**](https://github.com/alkalo/QALab-releases/releases/latest) | NSIS installer — **recommended** (shortcuts, in-app auto-update via GitHub API) |
| [**QALab-*-Portable.exe**](https://github.com/alkalo/QALab-releases/releases/latest) | Portable — no install; run from any folder; updates swap the `.exe` in place |

On the [Releases](https://github.com/alkalo/QALab-releases/releases/latest) page, download **Setup** or **Portable** for the current version.

---

## Quick start

1. Download **Setup** or **Portable** from [Releases](https://github.com/alkalo/QALab-releases/releases/latest).
2. Run the `.exe`. If Windows SmartScreen warns (unsigned installer), click **More info → Run anyway**.
3. **First launch** (5–15 min): installs Ollama if needed and downloads AI models (~4–8 GB). Splash shows progress.
4. The dashboard opens in a native window — API + web UI embedded; no Docker or separate Node/Python install.

| Item | Location |
|------|----------|
| User data | `%APPDATA%\QALab\` (SQLite, sessions, templates, `.env`) |
| Logs | `%APPDATA%\QALab\launcher.log` |
| System tray | Open panel, Ollama status, **Check for updates** |

---

## Requirements

| Component | Minimum |
|-----------|---------|
| OS | Windows 10/11, 64-bit |
| RAM | 8 GB (16 GB recommended for vision models) |
| Disk | ~10 GB free (app + Ollama models) |
| Ollama | Installed automatically on first run if missing |
| Network | First run only (model download); then works offline |

**Optional:** Jira / Linear / TestRail via OAuth or API tokens in Settings.

---

## Updates

| Install type | Mechanism |
|--------------|-----------|
| **Setup (NSIS)** | Tray or Settings → Check for updates; GitHub REST API + optional SHA256 manifest |
| **Portable** | Same updater; downloads new `QALab-*-Portable.exe` and swaps in place |

Both install types use **this repository** only (`alkalo/QALab-releases`). The packaged app does **not** consume `latest.yml` at runtime (electron-builder may still publish it as an optional artifact).

Enable **Install updates automatically on startup** in Settings to download and install new releases without prompting at launch.

---

## Stack (local-first)

| Layer | Technology |
|-------|------------|
| AI | Qwen2.5-VL / Qwen2.5 via **Ollama** (hardware-aware model picker) |
| Backend | FastAPI + SQLite |
| Frontend | Next.js + TypeScript |
| Desktop | Electron (Windows) |

No screenshots, prompts, or bug data are sent to external AI APIs during normal use.

---

## Troubleshooting

### SmartScreen: "Windows protected your PC"

The installer is not Authenticode-signed. Click **More info → Run anyway**. Verify downloads from `github.com/alkalo/QALab-releases`.

### Error: `resolveModels is not a function`

Upgrade to **v0.4.1+** from [Releases](https://github.com/alkalo/QALab-releases/releases/latest).

### First run is slow

Ollama and vision models are downloading. Check the splash log; ensure stable internet.

### Portable update fails

Ensure the portable `.exe` is not on a read-only drive. Use **v0.4.1+** for correct portable update paths.

### Jira / OAuth fails

Restart QALab. If it persists, review `%APPDATA%\QALab\.env` (reconnect OAuth in Settings).

---

## About this repository

| Repository | Visibility | Contents |
|------------|------------|----------|
| **QALab-releases** (this repo) | Public | Windows installers, `latest.yml`, release notes |
| **QALab** (main project) | Private | Source code, CI, development |

---

## License

MIT — personal and commercial use of the distributed binaries, subject to third-party licenses (Ollama, Electron, etc.).

---

<p align="center"><sub>QALab v2 — Local AI for game QA teams</sub></p>
