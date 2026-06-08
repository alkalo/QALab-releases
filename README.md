# QALab — Desktop Releases

[![Latest release](https://img.shields.io/github/v/release/alkalo/QALab-releases?label=desktop)](https://github.com/alkalo/QALab-releases/releases/latest)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

**Public download page** for the QALab Windows desktop app.

This repository contains **installers only** — no source code. The main project is maintained in a private repository; releases are published here so anyone can download and receive automatic updates without repository access.

---

## What is QALab?

**QALab** is a **local AI suite for QA departments** in casual and mobile games. Visual analysis, bug triage, LQA, release advisor, Jira KPIs, and executive reports — **100% local** with [Ollama](https://ollama.com), no paid cloud APIs.

Built for studios like **Scopely, Socialpoint, Rovio, King, Voodoo, Gameloft**.

| Capability | Description |
|------------|-------------|
| **Visual analysis** | Capture a screenshot → AI drafts a bug report with a vision model (VLM) |
| **Bug review** | Human validation, AI triage, duplicate detection, batch export to Jira / Linear |
| **LQA** | Localization QA on screenshots |
| **KPIs & Insights** | Configurable Jira metrics, dashboards, AI analysis of bug patterns |
| **Release Advisor** | AI go / no-go recommendation from draft bugs and Jira KPIs |
| **QA Assistant** | Natural-language questions about local bugs and metrics |
| **Weekly report** | Downloadable executive Markdown for leadership |

Everything runs on your machine. Data stays local in `%APPDATA%\QALab\`.

---

## Typical QA workflow

```
1. Visual analysis or LQA  →  draft bug
2. Bug review              →  validate / AI triage / detect duplicates
3. Export to Jira          →  OAuth in Insights → Sources
4. Release Advisor         →  weekly executive report for leadership
```

---

## Tools in the app

| Tool | What it does |
|------|--------------|
| **QA Assistant** | Ask questions about bugs, KPIs, and test data |
| **Visual analysis** | Capture + VLM → structured bug draft |
| **Bug review** | Validate, batch triage, export to Jira |
| **LQA** | Localization checks on screenshots |
| **Release Advisor** | AI go / no-go for a build |
| **Weekly report** | Executive Markdown download |
| **KPIs & Metrics** | Jira dashboards, OAuth sources, AI insights |

Navigation: **Cmd/Ctrl-K** command palette · light/dark theme · AI telemetry in Settings.

---

## Download (Windows 10/11, 64-bit)

**Latest release:** [v0.2.19](https://github.com/alkalo/QALab-releases/releases/latest)

| File | Use |
|------|-----|
| [**QALab-0.2.19-Setup.exe**](https://github.com/alkalo/QALab-releases/releases/download/v0.2.19/QALab-0.2.19-Setup.exe) | NSIS installer — **recommended** (desktop shortcut, updater) |
| [**QALab-0.2.19-Portable.exe**](https://github.com/alkalo/QALab-releases/releases/download/v0.2.19/QALab-0.2.19-Portable.exe) | Portable — no install, run from any folder |

[All releases →](https://github.com/alkalo/QALab-releases/releases)

---

## Quick start

1. Download **Setup** or **Portable** from [Releases](https://github.com/alkalo/QALab-releases/releases/latest).
2. Run the `.exe`. If Windows SmartScreen warns (unsigned installer), click **More info → Run anyway**.
3. **First launch** (5–15 min): the app installs Ollama if needed and downloads AI models (~4–8 GB).
4. The QALab dashboard opens in a native window — API and web UI are embedded; no Docker or Node required.

| Item | Location |
|------|----------|
| User data | `%APPDATA%\QALab\` (SQLite, sessions, templates) |
| Config | `%APPDATA%\QALab\.env` (auto-created) |
| Logs | `%APPDATA%\QALab\logs\` |
| System tray | Open panel, Ollama status, **Check for updates** |

---

## Requirements

| Component | Minimum |
|-----------|---------|
| OS | Windows 10/11, 64-bit |
| RAM | 8 GB (16 GB recommended for VLM) |
| Disk | ~10 GB free (app + Ollama models) |
| Ollama | Installed automatically on first run if missing |
| Network | First run only (model download); then works offline |

**Optional:** Jira / Linear integration via OAuth (Insights → Sources).

---

## Updates

The desktop app checks **this repository** for new versions:

- System tray → **Check for updates…**
- Or download the latest `.exe` manually from [Releases](https://github.com/alkalo/QALab-releases/releases/latest)

Installers from **v0.2.18+** use this public repo for auto-update. Older builds may need a one-time manual download.

---

## Integrations

| Service | How to connect |
|---------|----------------|
| **Jira** | KPIs & Metrics → Sources → Connect Atlassian (OAuth) |
| **Linear** | Configure in Insights sources |
| **TestRail / APIs** | QA Assistant and Insights use local API tokens |

All credentials are stored locally in `%APPDATA%\QALab\`.

---

## Stack (local-first)

| Layer | Technology |
|-------|------------|
| AI | Qwen2.5-VL / Qwen2.5 via **Ollama** |
| Backend | FastAPI + SQLite |
| Frontend | Next.js + TypeScript |
| Desktop | Electron (Windows) |

No data is sent to external AI APIs during normal use.

---

## Troubleshooting

### SmartScreen: "Windows protected your PC"

The installer is not Authenticode-signed (common for open-source tools). Click **More info → Run anyway**. Verify downloads come from `github.com/alkalo/QALab-releases`.

### First run is slow

Ollama and vision models are downloading (~4–8 GB). Check the splash screen log; ensure stable internet.

### Error checking for updates (404)

Download the latest version manually from [Releases](https://github.com/alkalo/QALab-releases/releases/latest), or upgrade to **v0.2.18+**.

### Jira / OAuth fails

Restart QALab. If it persists, delete `%APPDATA%\QALab\.env` (regenerates on start; you will need to reconnect OAuth).

---

## About this repository

| Repository | Visibility | Contents |
|------------|------------|----------|
| **QALab-releases** (this repo) | Public | Windows installers, `latest.yml`, release notes |
| **QALab** (main project) | Private | Source code, CI, development |

Questions about source access or contributions: contact the maintainer.

---

## License

MIT — personal and commercial use of the distributed binaries, subject to third-party licenses (Ollama, Electron, etc.).

---

<p align="center"><strong>QALab</strong> — Local AI for game QA teams</p>