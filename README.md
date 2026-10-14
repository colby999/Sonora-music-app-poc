# Sonora-music-app-poc
this is a music app with streaming and downloading avalaible it is fully working . it is just a poc for educational purposes, not intended to be used at all

# Sonora — Music Streaming POC

> **⚠️ Working proof-of-concept only. Built for educational demonstration.**  
> A technical demo exploring resilient multi-source music streaming architecture on Android.

<p align="center">
  <img src="https://img.shields.io/badge/status-POC-blue" alt="status: POC" />
  <img src="https://img.shields.io/badge/platform-Android-green" alt="platform: Android" />
  <img src="https://img.shields.io/badge/language-Kotlin%20%2F%20Compose-purple" alt="Kotlin + Compose" />
  <img src="https://img.shields.io/badge/media-Media3%20%2F%20ExoPlayer-orange" alt="Media3" />
  <img src="https://img.shields.io/badge/license-Closed%20Source-lightgrey" alt="Closed Source" />
</p>

<p align="center">
  <a href="https://github.com/colby999/Sonora-music-app-poc/releases/download/Sonora-3.6.0.apk/Sonora-3.6.0.apk">
    <img src="https://img.shields.io/badge/Download-Sonora%20v3.6.0%20APK-brightgreen?style=for-the-badge&logo=android" alt="Download APK" />
  </a>
</p>

---

## 📱 Screenshots


<img width="644" height="1280" alt="photo_5944888621125013389_y" src="https://github.com/user-attachments/assets/68638057-9282-439b-9b80-673fccf42bf5" />
<img width="632" height="1280" alt="photo_5944888621125013388_y" src="https://github.com/user-attachments/assets/8c302ad6-de40-4f2c-9655-8e9c8ba3c7c1" />
<img width="632" height="1280" alt="photo_5944888621125013388_y" src="https://github.com/user-attachments/assets/d1e61441-5601-4c3f-a270-6002970e5777" />
<img width="626" height="1280" alt="photo_5944888621125013387_y" src="https://github.com/user-attachments/assets/85db2985-63e0-47b1-abfb-0c51f6ee922d" />
<img width="627" height="1280" alt="photo_5944888621125013386_y" src="https://github.com/user-attachments/assets/e7b8b837-5524-4c32-ae26-9bd7ebdcd192" />
<img width="632" height="1280" alt="photo_5944888621125013385_y" src="https://github.com/user-attachments/assets/99f6b8a0-2888-4f75-a7f7-e724886d7ec4" />
<img width="639" height="1280" alt="photo_5944888621125013384_y" src="https://github.com/user-attachments/assets/d691eb8a-4e11-44e2-a248-db3f11f4401c" />
<img width="639" height="1280" alt="photo_5944888621125013383_y" src="https://github.com/user-attachments/assets/d8c683d0-bb66-4595-86fa-8a5ffed346bb" />


## What this is

Sonora is a **working proof-of-concept** Android music app (Kotlin, Jetpack Compose, Media3/ExoPlayer) demonstrating:

- **Multi-source streaming architecture** — a layered stream resolver that falls back between sources:  
  `NewPipeExtractor (on-device) → direct InnerTube clients → Piped gateways → Invidious`, with SoundCloud, Audius, and Internet Archive as independent first-class sources.
- **Full offline downloads** with live progress, HLS segment concatenation, and artwork sidecars.
- **Media3 session integration** — lockscreen + Bluetooth transport controls, background playback service.
- **Home-screen widget** (play / pause / next / previous).
- **Google Takeout import** — parses Takeout archives (nested multi-part zips included) and rebuilds a user's YouTube Music playlists.
- **Self-healing extraction layer** — byte-patched extractor JAR, cookie-jar redirect handling, and gzip-transparent HTTP.
- **In-app diagnostics** — live-tests every resolver layer and reports exact failure points.

---

## Download & Installation

1. Click the **Download APK** button above (or grab it from the [Releases page](https://github.com/colby999/Sonora-music-app-poc/releases/latest)).
2. Open the downloaded `Sonora-3.6.0.apk` on your phone and allow installation from unknown sources if prompted.

---

## Notice & Disclaimers

- **POC Status:** Depends on unofficial stream extraction APIs which can break at any time.
- **No maintenance promise:** This repository exists strictly as a technical demonstration and portfolio piece.
- **Closed Source:** The source code is private and proprietary. Only pre-compiled APK binaries are distributed for evaluation.
- **Legal:** This project is a personal educational demo not affiliated with or endorsed by YouTube, Google, SoundCloud, Audius, or the Internet Archive.
