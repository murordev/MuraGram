<div align="center">

# ⚡ MuraGram

**An independent Telegram client and bridge built for environments with restricted access, legacy hardware, and minimal JavaScript support.**

*Seamless. Fast. Unstoppable.*

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Quart](https://img.shields.io/badge/Quart-ASGI-2ECC71?style=for-the-badge)](https://pgjones.gitlab.io/quart/)
[![Telethon](https://img.shields.io/badge/Telethon-MTProto-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://github.com/LonamiWebs/Telethon)
[![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20Android%20%7C%20iOS%20%7C%20Windows%20Phone-black?style=for-the-badge)](#-supported-platforms--clients)

---

### 🌐 Live Mirrors & Links

| Service | URL | Description |
| :--- | :--- | :--- |
| 🌍 **Official Website** | [muror.ct.ws](http://muror.ct.ws) | Project portal & info hub |
| 🚀 **Web Client (Primary)** | [mura.alwaysdata.net](https://mura.alwaysdata.net) | Cloud-hosted Web interface |
| ⚡ **Web Client & API Gateway** | [muragram.muror.qzz.io](https://muragram.muror.qzz.io) | Production Web Client & REST API v1 |

---

</div>

## 📖 About The Project

**MuraGram** is a lightweight, asynchronous Telegram web client and proxy bridge designed to bypass strict network constraints, heavy browser engines, and platform limitations.

Modern web apps often require massive JavaScript bundles, heavy DOM rendering, and modern TLS handshakes that completely break on older browsers and low-spec devices. **MuraGram solves this** by shifting all heavy computational tasks (cryptography, MTProto 2.0 protocol handling, and binary serialization) to a lean asynchronous backend, delivering pure, clean HTML and a blistering-fast REST API for client apps.

---

## ✨ Key Features

* **🪶 Ultra-Low Footprint Web UI:** Optimized for low-end browsers (including legacy Internet Explorer, old Safari, and low-RAM environments) with graceful degradation and minimal JavaScript dependency.
* **🔌 Universal REST API v1:** Clean, standardized JSON endpoints powering independent third-party and retro mobile clients.
* **🛡️ Zero-Message-Storage Architecture:** MuraGram acts strictly as a transparent bridge. Message history, chat contents, and 2FA passwords are **never** stored in a server-side database.
* **🎥 Progressive Video & Range Streaming:** Full support for `HTTP 206 Partial Content` and `Range: bytes=...` headers, enabling instant video seeking, voice note playback, and progressive disk caching.
* **🔐 Multi-Flow Authentication:**
  * Interactive **QR Code Login** with auto-refresh and real-time polling.
  * Direct **Phone Number & 2FA** authorization with Telegram service-chat code delivery.
* **⚡ High-Efficiency Polling & WebSockets:** Real-time updates via WebSockets and lightweight incremental polling using message ID anchors (`min_id` and `offset_id`).

---

## 📱 Supported Platforms & Clients

The MuraGram backend bridges modern Telegram infrastructure with custom-built clients across multiple generations of devices:

* 🌐 **Web Interface:** Universal responsive web client with Light/Dark themes and low-bandwidth modes.
* 🤖 **Modern Android:** Native client designed for Android 5.0+ up to modern Android versions.
* 📟 **Retro Android:** Dedicated lightweight client for **Android 2.3 (Gingerbread)**.
* 🍏 **Retro iOS:** Native Objective-C client built for **iOS 6 (Skeuomorphism era)**.
* 📱 **Windows Phone:** Specialized C# / XAML client for **Windows Phone 8.0 & 8.1 (Silverlight / WinRT)**.

---

## 🏗️ Architecture & Tech Stack
┌────────────────────────────────────────────────────────┐
│ Client Apps │
│ (Web Browser / Android / iOS 6 / Windows Phone 8.1) │
└───────────────┬────────────────────────┬───────────────┘
│ HTTP / REST API v1 │ WebSockets
▼ ▼
┌────────────────────────────────────────────────────────┐
│ MuraGram Core │
│ Python 3 • Quart (ASGI Engine) │
├────────────────────────────────────────────────────────┤
│ • User Session Isolation (SQLite .session storage) │
│ • Video & Media Cache Management │
│ • REST API Blueprint Router │
└───────────────────────┬────────────────────────────────┘
│ MTProto 2.0 (TCP / Encrypted)
▼
┌────────────────────────────────────────────────────────┐
│ Official Telegram Servers │
└────────────────────────────────────────────────────────┘
* **Core Engine:** [Python 3](https://www.python.org/)
* **ASGI Framework:** [Quart](https://pgjones.gitlab.io/quart/) (Async Flask alternative)
* **Telegram Protocol Implementation:** [Telethon](https://github.com/LonamiWebs/Telethon) (Pure Python MTProto)
* **Image/QR Processing:** [Pillow](https://python-pillow.org/) & [qrcode](https://pypi.org/project/qrcode/)
* **Acceleration:** [cryptg](https://pypi.org/project/cryptg/) (C-accelerated cryptography)

---

## 🗺️ Project Roadmap

- [x] High-performance Quart async web interface
- [x] Multi-user session isolation & background cleanup tasks
- [x] REST API v1 for mobile integration
- [x] Range-header video streaming (HTTP 206)
- [x] User Profile & Group About/Bio inspection endpoints
- [x] Embedded `reply_to_message` preview generation
- [ ] Public source code release
- [ ] Docker & Docker-Compose self-hosting bundle

---

## 📄 License

This project is protected by a custom license. You can read and run MuraGram locally for testing, but you cannot use it to build your own products. Attribution to **murordev** is required for any public mentions. See the full [LICENSE](LICENSE) file for details.

---

<div align="center">

Crafted with care by **[@murordev](http://muror.ct.ws)**

</div>
