# FallingSound (坠音)

[简体中文](README.zh-CN.md)

FallingSound (坠音) is a cross-platform music player built with **Kotlin Multiplatform** and **Compose Multiplatform**, supporting **Android, iOS, and Desktop** (Windows / macOS / Linux). Through a JS plugin system, it aggregates multiple music sources and delivers a unified experience of search, playback, playlists, lyrics, and comments — plus local music, WebDAV multi-device sync, and playback statistics.

## Features

- **Playback** — a unified playback engine on every platform: Media3 ExoPlayer on Android (foreground service, notification controls, audio focus management), AVPlayer on iOS (background playback, call interruption handling), JavaFX Media on Desktop (keeps playing when the window is minimized)
- **Plugin system** — QuickJS-powered JS source plugins, loadable from URL or local files; aggregated search across plugins with similarity ranking and de-duplication; automatic fallback to alternative sources when a plugin's source fails
- **Search & discovery** — parallel multi-source search with scored, de-duplicated results
- **Lyrics & comments** — unified lyrics and comments across sources
- **Local music** — play local files with built-in ID3v2.3 metadata parsing / writing
- **Download & cache** — offline downloads and local caching
- **Backup & sync** — WebDAV-based multi-device synchronization
- **Playback statistics** — track listening history and stats
- **UI & personalization** — Material 3 design with dynamic cover color theming

## Supported Platforms

| Platform | Playback Engine | Notes |
|---|---|---|
| Android (API 24+) | Media3 ExoPlayer | Foreground service, notification controls, audio focus management |
| iOS (15.0+) | AVPlayer | Background playback via AVAudioSession, KVO state observation, call interruption handling |
| Desktop (Windows / macOS / Linux) | JavaFX Media | Keeps playing when the window is minimized |

## Download

Grab the latest build for your platform from the [Releases](../../releases) page.

| Platform | Artifact |
|---|---|
| Android | APK |
| iOS | IPA (unsigned) |
| Windows | EXE installer |
| macOS | DMG (unsigned) |
| Linux | DEB |

> **Note:** iOS IPA and macOS DMG are unsigned builds intended for development and testing only; they cannot be installed via the App Store or sideloaded onto non-jailbroken devices.

## Screenshots

<!-- Add your screenshots here, e.g.:
![Android](screenshots/android_main.png)
![iOS](screenshots/ios_main.png)
![Desktop](screenshots/desktop_main.png)
-->

*Screenshots coming soon.*

## Tech Stack

- **Language / UI** — Kotlin, Compose Multiplatform, Material 3
- **Network** — Ktor (OkHttp / Darwin engines), Okio
- **Database** — Room (KMP) + SQLite
- **DI** — Kodein DI
- **Image loading / theming** — Coil 3, kmpalette
- **Serialization / data flow** — kotlinx.serialization, Store5
- **Plugin engine** — QuickJS (JS source plugins)
- **Files / sync** — FileKit, WebDAV client KMP
- **Metadata** — custom ID3v2.3 parsing / writing module
- **Logging** — Napier with local file logs and crash capture

## Disclaimer

This project is intended for learning and technical exchange only. Music content provided by source plugins belongs to the respective copyright owners; please do not use it for commercial purposes.
