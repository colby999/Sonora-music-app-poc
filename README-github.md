# Sonora — Music Streaming POC

> **⚠️ Working proof-of-concept only. This app is NOT intended for actual use.**
> Built as a technical demo / portfolio piece to explore music-streaming architecture on Android.

<p align="center">
  <img src="https://img.shields.io/badge/status-POC-blue" alt="status: POC" />
  <img src="https://img.shields.io/badge/platform-Android-green" alt="platform: Android" />
  <img src="https://img.shields.io/badge/language-Kotlin%20%2F%20Compose-purple" alt="Kotlin + Compose" />
  <img src="https://img.shields.io/badge/media-Media3%20%2F%20ExoPlayer-orange" alt="Media3" />
</p>

---

## What this is

Sonora is a **working proof-of-concept** Android music app (Kotlin, Jetpack Compose, Media3/ExoPlayer) that demonstrates:

- **Multi-source streaming architecture** — a layered stream resolver that falls back between sources:
  `NewPipeExtractor (on-device) → direct InnerTube clients → Piped gateways → Invidious`, with
  SoundCloud, Audius and Internet Archive as independent first-class sources
- **Full offline downloads** with live progress, HLS segment concatenation, and artwork sidecars
- **Media3 session integration** — lockscreen + Bluetooth transport controls, background playback service
- **Home-screen widget** (play / pause / next / previous)
- **Google Takeout import** — parses whole Takeout archives (nested multi-part zips included) and rebuilds
  a user's YouTube Music playlists
- **Self-healing extraction layer** — a byte-patched extractor JAR (fixes an Android-13-only API call at the
  constant-pool level), cookie-jar redirect handling, and gzip-transparent HTTP for the extractor

The interesting engineering here is the **resolver pipeline and the failure forensics**: public
music-source APIs rot constantly (the Piped ecosystem largely died in 2025–2026), so the app ships an
in-app diagnostics screen that live-tests every layer and reports exactly which one fails — which is how
the redirect-loop and gzip double-decoding bugs were found and fixed.

## Download

Grab the APK from the [Releases](../../releases) page and sideload it.

## Why it's "not intended for use"

- It depends on **unofficial extraction of YouTube streams**, which violates YouTube's Terms of Service
  and can break at any time (and did, repeatedly, during development).
- There is **no support, no updates promised, and no maintenance plan** — it exists to demonstrate
  architecture and problem-solving.
- It is **not distributed on any app store** and must be sideloaded manually.

## Legal notes

- This project is a personal educational demo. It is **not affiliated with, endorsed by, or connected to**
  YouTube, Google, SoundCloud, Audius, or the Internet Archive in any way.
- All streams are fetched through publicly available APIs and endpoints of those services.
- **No license is granted** — all rights reserved by the author. You may read the code for educational
  purposes; you may not redistribute or reuse it without written permission.
- Users are responsible for complying with the laws and terms of service of their jurisdiction.

## Built with

| Tech | Purpose |
|---|---|
| Kotlin + Jetpack Compose | UI |
| Media3 / ExoPlayer | Playback, session, notification |
| NewPipeExtractor (patched) | YouTube/SoundCloud extraction |
| OkHttp | Networking |
| Audius API / Internet Archive API / SoundCloud API | First-class full-track sources |

---

*One person, one weekend of debugging the 2026 music-app apocalypse. For the full story, read the commit history.*
