# Core Companion

Core Companion is an Android application for MeshCore LoRa mesh radios and off-grid field operations. It connects to companion nodes over Bluetooth Low Energy (BLE), USB Serial (OTG), or TCP/KISS and provides messaging, live radio telemetry, offline mapping, and emergency preparedness tools without requiring cellular or internet access.

All official APK builds and release candidates are published on the [Releases](https://github.com/RO-Mesh/core-companion/releases) page of this repository. You can also check the [project overview page](https://ro-mesh.github.io/core-companion/) for live release status and direct downloads.

## Two Editions, One Core

Every release cycle builds two Android editions from the same shared core engine:
- **Core Client**: Simple, focused radio client built specifically for everyday field testing and LoRa mesh communications.
- **Core Companion**: Modular, extensible civil resilience suite integrating multi-protocol comms, offline vaults, and emergency coordination.

### Feature Comparison

| Feature | Core Client | Core Companion | Details |
|---|:---:|:---:|---|
| **Interface** | **Simple** | **Modular** | Direct radio focus vs. extensible central hub. |
| **Operational Workspaces** | ❌ | ✅ | Go (Citizen), Pro (Operator), MAX (SAR Command). |
| **MeshCore Messaging** | ✅ | ✅ | Public channels, encrypted channels, direct messages. |
| **Hardware Connectivity (BLE & USB OTG)** | ✅ | ✅ | Direct companion node support (LilyGO, Heltec, RAK, Seeed). |
| **Offline Topo & Signal Coverage Maps** | ✅ | ✅ | OpenStreetMap & OpenTopoMap with RF signal heatmaps (no API keys). |
| **RF Diagnostics Suite** | ✅ | ✅ | RX Log, spectrum noise floor, field coverage mapper, topology. |
| **Personal Operator & Medical ID** | ✅ | ✅ | Personal callsign & medical profile for emergency SOS broadcasting. |
| **RO-MESH Online Services (SSO Login)** | ✅ *(Optional)* | ✅ *(Optional)* | Secure single sign-on access to community services & presets. |
| **Family & Team Emergency Plan** | ❌ | ✅ | Multi-member coordination, roles, rally points. |
| **Printable Emergency Binder** | ❌ | ✅ | Formatted paper export for offline analog archive. |
| **Document Vault & Survival Guides** | ❌ | ✅ | Offline first-aid, earthquake, blackout guides & encrypted storage. |
| **Civil Defense Shelter Directory** | ❌ | ✅ | Complete nationwide offline shelter database for Romania. |
| **Multi-Protocol (HAM, TNC, Reticulum)** | ❌ | ⏳ | Expanding beyond MeshCore *(In Development)*. |
| **Recommended Target** | **Field Testers & Daily Radio Operators** | **Emergency Preparedness, Families & SAR Responders** | Choose the edition tailored to your operational profile. |

## Which APK File Should I Download?

Each release includes split builds per processor architecture alongside a universal package:

| File | Target Devices | Notes |
|---|---|---|
| `*-arm64-v8a.apk` | Modern Android phones & tablets (2018+) | Recommended for 99% of physical devices (Samsung, Pixel, Xiaomi, Motorola, etc.). Smaller download (~38 MB) and native 64-bit performance. |
| `*-universal.apk` | Any Android device | Bundles all CPU architectures into one APK (~96 MB). Use this if you are unsure which processor your phone has. |
| `*-armeabi-v7a.apk` | Older 32-bit Android phones | Built for legacy 32-bit ARM devices manufactured before 2017. |
| `*-x86_64.apk` | PC Emulators & Intel tablets | Built for Android Studio, Waydroid, or x86_64 tablets. |

Every release includes a `SHA256SUMS.txt` file so you can verify the downloaded APK before installing:

```bash
sha256sum -c SHA256SUMS.txt --ignore-missing
```

## Release Channels: Stable vs. Release Candidates (`-rc`)

Similar to the [MeshCore lusofw firmware releases](https://github.com/Meshcore-Portugal/lusofw/releases), both editions of Core Companion share a unified version number across two release stages:

1. **Release Candidates (`vX.Y.Z-rcN-<commit>`)**:
   Marked as **Pre-release** on GitHub. Each release candidate tag (for example `v0.1.0-rc1-88be70a`) publishes APKs for both **Core Client** (`Core-Client-v*`) and **Core Companion** (`Core-Companion-v*`) so field testers can verify BLE reconnect behavior, LoRa packet framing, and battery consumption on real hardware before promotion.
2. **Stable Releases (`vX.Y.Z`)**:
   Marked as **Latest** on GitHub. Once a release candidate passes field testing without regressions, it is promoted to a clean semantic version tag (for example `v0.1.0`).

### Automatic Updates with Obtainium

If you use [Obtainium](https://github.com/ImranR98/Obtainium) on Android, you can add Core Companion or Core Client with 1 click directly from the [showcase page](https://ro-mesh.github.io/core-companion/), or configure it manually:

- **App Source URL**: `https://github.com/RO-Mesh/core-companion`
- **Fallback to older releases**: Enabled (ensures you don't receive updates meant for the other edition)
- **Filter APKs by architecture**: Enabled (automatically selects `arm64-v8a` for 64-bit devices, `armeabi-v7a` for 32-bit, or `x86_64` for emulators)
- **APK Filter RegEx**:
  - **Core Client**: `^Core-Client-v.*[.]apk$`
  - **Core Companion**: `^Core-Companion-v.*[.]apk$`

You can also import the pre-configured [obtainium-full.json](https://ro-mesh.github.io/core-companion/obtainium-full.json) or [obtainium-client.json](https://ro-mesh.github.io/core-companion/obtainium-client.json) directly into Obtainium.

## Reporting Bugs and Requesting Features

This repository hosts the public issue tracker for both editions of Core Companion.

- Found a bug, BLE disconnect, or UI glitch? [Open a Bug Report](https://github.com/RO-Mesh/core-companion/issues/new?template=bug_report.yml) and include your app edition (`Full` or `MeshCore Client`), version tag (including the `-rc` commit suffix if applicable), Android version, and companion radio hardware.
- Have an idea for a new radio tool or workflow improvement? [Open a Feature Request](https://github.com/RO-Mesh/core-companion/issues/new?template=feature_request.yml).
