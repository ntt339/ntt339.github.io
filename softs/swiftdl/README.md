# SwiftDL - High-Performance Turbo Download Manager for macOS

<p align="center">
  <img src="https://ntt339.github.io/softs/swiftdl/images/icon.png" alt="SwiftDL Icon" width="128" height="128" style="border-radius: 28px;">
</p>

<p align="center">
  <a href="https://apps.apple.com/us/developer/thang-truong-ngoc/id6818040142">
    <img src="https://img.shields.io/badge/Mac_App_Store-Download_Free-black?style=for-the-badge&logo=apple&logoColor=white" alt="Download on the Mac App Store">
  </a>
</p>

<p align="center">
  <a href="https://apps.apple.com/us/developer/thang-truong-ngoc/id6818040142"><img src="https://img.shields.io/badge/macOS-13.0%2B-blue?logo=apple&style=flat-square" alt="macOS 13.0+"></a>
  <a href="https://apps.apple.com/us/developer/thang-truong-ngoc/id6818040142"><img src="https://img.shields.io/badge/Architecture-Universal%202%20(Apple%20Silicon%20%26%20Intel)-purple?style=flat-square" alt="Universal 2"></a>
  <a href="https://developer.apple.com/swift/"><img src="https://img.shields.io/badge/Swift-6.0%20%7C%20SwiftUI-orange?logo=swift&style=flat-square" alt="Swift 6"></a>
  <a href="#privacy--security"><img src="https://img.shields.io/badge/Price-100%25%20Free%20%26%20Offline-brightgreen?style=flat-square" alt="100% Free"></a>
  <a href="#supported-languages"><img src="https://img.shields.io/badge/Languages-11%20International-blueviolet?style=flat-square" alt="11 Languages"></a>
</p>

---

A blazing-fast, lightweight, and 100% native download manager engineered exclusively for macOS. Built in **Swift 6 & SwiftUI**, SwiftDL accelerates downloads through multi-threaded segmented chunking, gives you full control with dynamic sliding-window speed limits, automates your queue with a smart scheduler, and provides seamless online video extraction.

* 🌐 **Official Website**: [https://ntt339.github.io/softs/swiftdl/](https://ntt339.github.io/softs/swiftdl/)
* 🔒 **Privacy Policy**: [https://ntt339.github.io/softs/swiftdl/privacy.html](https://ntt339.github.io/softs/swiftdl/privacy.html)
* 👨‍💻 **Developer Portfolio**: [https://ntt339.github.io/](https://ntt339.github.io/)
* 🍏 **Apple Developer Profile**: [https://apps.apple.com/us/developer/thang-truong-ngoc/id6818040142](https://apps.apple.com/us/developer/thang-truong-ngoc/id6818040142)

---

## ✨ Key Features

### 1. ⚡ 8x Segmented Multi-Thread Engine
* Splits target files into **1, 2, 4, or 8 parallel chunks** using HTTP `Range` requests (RFC 7233).
* Pre-allocates destination files on disk via `FileHandle.truncate(atOffset:)` for zero fragmented overhead.
* Concurrently streams byte chunks and writes directly into offset positions for maximum bandwidth saturation.
* Seamless auto-fallback to single-thread download if the remote server does not advertise `Accept-Ranges`.

### 2. 🚦 Adaptive Token-Bucket Speed Limiter
* Sliding 1.0-second time window rate-limiter protects your network for video calls, gaming, and 4K streaming.
* Instant quick presets: **500 KB/s**, **1 MB/s**, **2 MB/s**, **5 MB/s**, or configure any custom byte rate.
* Dynamically adjust or disable speed caps on-the-fly without pausing or restarting active download streams.

### 3. ⏱️ Intelligent Queue Scheduler
* Configure exact start and stop hours/minutes for automated night-time downloading during off-peak hours.
* Select active days of the week (Monday through Sunday).
* Dispatches native macOS User Notifications upon schedule launch and batch completion.

### 4. 🎥 YouTube & Online Video Grabber
* Built-in orchestration with `yt-dlp` for popular video platforms.
* Auto-discovers executable paths across Homebrew (`/opt/homebrew`, `/usr/local`) and Python environments.
* Seamless progress tracking and background muxing directly inside the main UI.

### 5. 📋 Instant Clipboard Auto-Detection
* Focus the app to instantly auto-detect download URLs from the system clipboard.
* One-click "Paste Link" quick bar for instant queue addition.

### 6. 📂 Automatic File Categorization
* Sorts files automatically based on extensions:
  * **Applications**: `.dmg`, `.pkg`, `.app`, `.exe`, `.msi`, `.deb`, `.rpm`, `.ipa`
  * **Archives**: `.zip`, `.rar`, `.7z`, `.tar`, `.gz`, `.bz2`, `.xz`, `.iso`
  * **Movies & Videos**: `.mp4`, `.mkv`, `.mov`, `.avi`, `.webm`
  * **Music**: `.mp3`, `.wav`, `.flac`, `.aac`, `.ogg`, `.m4a`
  * **Documents**: `.pdf`, `.doc`, `.docx`, `.txt`, `.pages`, `.xls`, `.xlsx`, `.ppt`, `.csv`
  * **Other**: General file downloads

### 7. 🌐 11 International Languages
Fully localized with on-the-fly language switching:
* 🇬🇧 English
* 🇩🇪 Deutsch
* 🇫🇷 Français
* 🇪🇸 Español
* 🇵🇹 Português
* 🇹🇷 Türkçe
* 🇯🇵 日本語
* 🇰🇷 한국어
* 🇲🇽 Español (México)
* 🇩🇰 Dansk
* 🇻🇳 Tiếng Việt

### 8. 🛡️ Apple Sandboxed & Privacy-First
* Enforces `com.apple.security.app-sandbox`.
* User-selected download folder permissions.
* Zero third-party trackers, zero telemetry, zero analytics SDKs, 100% offline-first.

---

## 🛠️ Build & Packaging Instructions

### Prerequisites
* macOS 13.0 or later
* Xcode 15 / 16 with Swift 6.0 toolchain

### 1. Build & Run Locally
```bash
# Clone the repository
git clone https://github.com/ntt339/SwiftDL.git
cd SwiftDL

# Build and run with swift
swift run
```

### 2. Build Signed Standalone .app Bundle
```bash
./build.sh
```

### 3. Build & Sign App Store Installer PKG
```bash
./build_appstore_pkg.sh
```

### 4. Upload to App Store Connect
```bash
./upload_appstore.sh
```

---

## 🔒 Privacy & Security

SwiftDL collects **zero** personal data:
- Direct connections only between your Mac and download servers.
- No user accounts, logins, or server-side telemetry.
- All configurations and states remain strictly local.

Read the complete [Privacy Policy](https://ntt339.github.io/softs/swiftdl/privacy.html).

---

## 📄 License

Developed and maintained by **NGOC THANG TRUONG** ([ngocthang@gmail.com](mailto:ngocthang@gmail.com)).  
All rights reserved © 2026.
