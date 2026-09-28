# 🪨 Rock Boys — Official Android Releases

<p align="center">
  <strong>The official Android release repository for the Rock Boys Clan Portal.</strong><br/>
  <a href="https://rockboys.vercel.app/">🌐 Open Rock Boys</a>
  ·
  <a href="https://github.com/RahulExe69/Rock-Boys/releases">📦 Releases</a>
</p>

---

## 🏰 What is Rock Boys?

Rock Boys is a **Clash of Clans clan command center and companion app** built for the Rock Boys clan family.

The main website combines real-time clan data, war and CWL tracking, player profiles, strategic tools, analytics, and a native Android companion experience into one place.

### 🛡️ Supported Clan Family

| Clan | Tag | Focus |
|---|---|---|
| **Rock Boys** | `#U92JJPRC` | Main clan, wars, CWL, trophies & clan progression |
| **Clan War** | `#V9CJQGLC` | Secondary / training clan |

---

## ⚔️ What You Can Do

### 📊 Clan & Member Dashboard
- Live clan roster and member information
- Town Hall and trophy distributions
- Donation statistics and top contributors
- Roles, activity and progression indicators
- Switch between the Rock Boys and Clan War clans

### ⚔️ Wars & CWL
- Current war dashboard
- War history and performance tracking
- Opponent/roster comparison
- Clan War League group and round views
- Attack, stars and percentage statistics

### 🪙 Capital Raid Analytics
- Raid season information
- Raid medals and capital gold statistics
- Member attack completion tracking
- Historical raid analytics

### 👤 Player Profiles & Verification
- Detailed troop, spell and hero information
- Player progression and Town Hall data
- Verified-player workflow using in-game verification
- Detailed comparison between clan members

### 🧰 Clash Armory & Tools
A dedicated tools area brings together the utilities used most often by the clan:

- **Raid Reload** — native Android reload utility with a local loopback VPN flow scoped to Clash of Clans
- **Base Layouts** — curated community base-layout discovery
- **Army Library** — community army compositions and references
- **Player Comparison** — multi-metric player comparison and derived summaries
- **Analytics & War tools**
- **Chest Simulator** — interactive reward simulation and statistics
- **Screenshot tools** for sharing clan and war information

### 🎁 Chest Simulator
The portal includes an interactive chest/reward simulator with:
- Tap and hit interactions
- Animated chest effects
- Town Hall-aware reward constraints
- Bulk simulations
- Probability and result summaries

### 📸 Screenshot & Sharing
Important dashboard views can be captured and exported for sharing to Discord, Reddit, WhatsApp and other platforms.

---

## 📱 Android Companion App

The website is also packaged as a native Android application:

**Package:** `com.rockboys.app`

The APK combines the Rock Boys web experience with native Android capabilities such as:

- Native Android bridge
- Native APK update/install flow
- Native APK version detection
- Local OTA web-bundle updates
- Native floating overlay for Raid Reload
- Local loopback VPN service for Raid Reload
- Persistent Android notifications for the floating utility
- Android hardware back-button integration with in-app navigation

### 🔄 Two-Level Update System

Rock Boys uses two different update layers:

```text
Open App
   ↓
Check Native APK Release
   ↓
New APK available?
   ├── Yes → Native APK update flow
   └── No  → Check OTA web update
                    ↓
                Launch app
```

**APK updates** replace native Android functionality and require a new APK.

**OTA updates** update the web application bundle without requiring a new APK build.

The native APK check is intentionally performed before the OTA check so the two update systems do not race each other.

---

## 🧱 Architecture

### Web Application
- React 19
- TypeScript
- Vite
- Tailwind CSS
- Motion
- React Router
- Recharts
- Lucide React

### Backend
- Node.js
- Express
- TypeScript / TSX
- Shared API router
- Server-side API proxying
- Response caching and error handling

### Android
- Capacitor 8
- Native Java Android bridge
- Android PackageInstaller
- FileProvider
- Foreground services
- VPN service for Raid Reload

### Data & Services
The portal integrates Clash of Clans data through server-side API/proxy infrastructure and supporting community resources for specific tools such as base layouts and army references.

---

## 🔄 OTA Architecture

Rock Boys keeps the latest verified web bundle locally on the device.

The OTA system:

1. Checks the remote OTA manifest.
2. Compares bundle hashes.
3. Reuses unchanged files from the built-in APK or current OTA bundle.
4. Downloads only changed files.
5. Verifies downloaded files using SHA-256 hashes.
6. Atomically activates the new bundle.
7. Keeps the last valid bundle available as a fallback.

This allows web-side improvements to ship independently from native Android releases.

---

## 🛡️ Update & Installation Safety

The Android updater uses the official Android `PackageInstaller` APIs.

When Android permits it, Rock Boys requests a no-user-action update session. When the operating system requires confirmation, the updater gracefully falls back to Android's standard installation confirmation flow.

APK updates must remain properly signed and compatible with the installed application for Android to accept them as updates.

---

## 🚀 Getting the Latest APK

The latest official APK is published here:

**👉 [Download the latest Rock Boys APK](https://github.com/RahulExe69/Rock-Boys-Release/releases/latest)**

For source code and the web application itself:

**👉 [Rock Boys Main Repository](https://github.com/RahulExe69/Rock-Boys)**

**👉 [Rock Boys Website](https://rockboys.vercel.app/)**

---

## 🧑‍💻 Main Repository

The Android binaries in this repository are built from the private main project:

**[RahulExe69/Rock-Boys](https://github.com/RahulExe69/Rock-Boys)**

The main repository contains the full web application, API layer, OTA system, Android wrapper, native services and release workflow.

This repository exists primarily to provide the **publicly downloadable Android release builds**.

---

<div align="center">

### 🪨 Built for the Rock Boys Clan Family

Clash of Clans and related assets are trademarks of their respective owners.  
Rock Boys is an independent fan-made project.

</div>
