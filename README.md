<div align="center">
  <a href="https://www.suntekai.com">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/SUNTEK-Official/.github/main/profile/assets/logo-dark.png">
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/SUNTEK-Official/.github/main/profile/assets/logo-light.png">
      <img alt="SUNTEK Technology Co., Ltd." src="https://raw.githubusercontent.com/SUNTEK-Official/.github/main/profile/assets/logo-light.png" height="44">
    </picture>
  </a>

  <h1>SUNTEK SM6 Flash Wizard for macOS</h1>

  <p>
    <strong>Official macOS Firmware Flashing Utility for SUNTEK SM6 Smart POS Terminals</strong> &middot; <em>Enjoy Smarter Service</em><br>
    Self-contained Universal 2 (<code>Apple Silicon</code> + <code>Intel</code>) desktop tool by <strong>SUNTEK Technology Co., Ltd.</strong>
  </p>

  <p>
    <a href="./LICENSE"><img src="https://img.shields.io/badge/License-Commercial_Utility-172A88?style=for-the-badge" alt="License"></a>
    <a href="https://github.com/SUNTEK-Official/suntek-sm6-flash-wizard/releases"><img src="https://img.shields.io/github/v/release/SUNTEK-Official/suntek-sm6-flash-wizard?style=for-the-badge&color=F39800&label=Release" alt="Latest Release"></a>
    <img src="https://img.shields.io/badge/macOS-12.0%2B_Universal_2-2563EB?style=for-the-badge" alt="macOS Universal 2">
    <img src="https://img.shields.io/badge/Languages-14_Languages-18339F?style=for-the-badge" alt="14 Supported Languages">
    <a href="mailto:support@suntekai.com"><img src="https://img.shields.io/badge/Support-support%40suntekai.com-0B1437?style=for-the-badge" alt="Support"></a>
  </p>

  <p>
    <a href="#overview--guided-workflow">Overview</a> &nbsp;&bull;&nbsp;
    <a href="#key-features">Features</a> &nbsp;&bull;&nbsp;
    <a href="#official-downloads--sha-256-verification">Downloads</a> &nbsp;&bull;&nbsp;
    <a href="#quick-start-guide">Quick Start</a> &nbsp;&bull;&nbsp;
    <a href="#troubleshooting--faq">FAQ</a> &nbsp;&bull;&nbsp;
    <a href="#support">Support</a>
  </p>

  <img src="https://raw.githubusercontent.com/SUNTEK-Official/suntek-sdk-sm6/main/assets/banner-sm6.webp" alt="SUNTEK SM6 Smart POS Terminal" width="100%">
</div>

---

## Overview & Guided Workflow

**SUNTEK SM6 Flash Wizard** is the official macOS desktop service tool for upgrading, restoring, and verifying **SUNTEK SM6** handheld Smart POS terminals over USB. Designed for field engineers, distributors, and service centers, it bundles all required runtime components inside a signed macOS `.app` installer with zero Homebrew or driver setup required.

```mermaid
flowchart LR
    S1["1. Environment Check & USB Conflict Cleanup"] --> S2["2. Official SM6 Firmware Validation"]
    S2 --> S3["3. Read-Only Device Compatibility Check"]
    S3 --> S4["4. Protected High-Speed USB Flashing"]
    S4 --> S5["5. Post-Flash Boot Verification"]
```

> [!NOTE]
> Application source code and proprietary servicing tools are the intellectual property of **SUNTEK Technology Co., Ltd.** This public repository hosts official documentation and SHA-256 verified signed macOS `.dmg` installers distributed exclusively via [**GitHub Releases**](https://github.com/SUNTEK-Official/suntek-sm6-flash-wizard/releases).

---

## Key Features

- **Native Universal 2 macOS Application**: Supports both **Apple Silicon** and **Intel** (`x86_64`) Macs running **macOS 12.0 (Monterey)** or newer, signed with an Apple Developer ID certificate.
- **Zero-Install Self-Contained Runtime**: All runtime engines, USB userspace drivers, and post-flash verification tools are embedded inside the application bundle.
- **14 Built-in Languages (Auto-Detect & Live Switching)**: Automatically follows the macOS system language or switches live in **Settings** (`Cmd + ,`) across **14 languages**:
  - `English` (`en`), `Simplified Chinese` (`zh-Hans`), `Traditional Chinese` (`zh-Hant`), `Spanish` (`es`), `French` (`fr`), `German` (`de`), `Russian` (`ru`), `Portuguese` (`pt`), `Italian` (`it`), `Romanian` (`ro`), `Turkish` (`tr`), `Polish` (`pl`), `Dutch` (`nl`), and `Indonesian` (`id`).
- **Pre-Flash USB Conflict Detector**: Detects background apps that commonly hijack POS USB ports (`Android Studio`, `Parallels Desktop`, `VMware`, `VirtualBox`, `Android File Transfer`, `scrcpy`, `adb`) and offers one-click cleanup.
- **Strict Hardware & Firmware Safety Guards**:
  - Validates official SUNTEK SM6 factory firmware packages offline (automatically rejecting incompatible files or OTA archives).
  - Performs a mandatory read-only device compatibility check before unlocking firmware writes.
  - Protects per-unit Serial Number (SN) and factory calibration partitions across both **Upgrade System (Keep Data · Recommended)** and **Factory Reset / Clean Reinstall** modes.
- **High-Speed Flashing & Real-Time Telemetry**: Displays overall component fraction (`X/N`), overall percentage, transfer speed, and remaining ETA, plus an active-write cancel confirmation dialog and an interactive **15-Second Power Reset Guide**.

---

## Official Downloads & SHA-256 Verification

<table>
  <tr>
    <td align="center" width="32%">
      <a href="https://www.suntekai.com/products/suntek-handheld-pos-terminal-sm6/">
        <img src="https://raw.githubusercontent.com/SUNTEK-Official/.github/main/profile/assets/prod-sm6.webp" alt="SUNTEK SM6 Smart POS" height="145">
      </a>
    </td>
    <td>
      <h3>SUNTEK SM6 Flash Wizard v2.0.0 (macOS Universal 2)</h3>
      <p>Download the signed disk image and checksum manifest directly from the <a href="https://github.com/SUNTEK-Official/suntek-sm6-flash-wizard/releases/latest"><b>Latest GitHub Release</b></a>.</p>
      <ul>
        <li><code>SUNTEK-SM6-Flash-Wizard-2.0.0.dmg</code> &mdash; Signed macOS 12.0+ Universal 2 installer (Apple Silicon + Intel)</li>
        <li><code>SHA256SUMS.txt</code> &mdash; Official SHA-256 verification digest</li>
      </ul>
    </td>
  </tr>
</table>

Always verify the downloaded `.dmg` checksum in macOS Terminal before installation:

```bash
shasum -a 256 -c SHA256SUMS.txt
```

### Installation

1. Double-click `SUNTEK-SM6-Flash-Wizard-2.0.0.dmg` to mount the disk image.
2. Drag **SUNTEK SM6 Flash Wizard.app** into your **Applications** folder.
3. Launch **SUNTEK SM6 Flash Wizard** from **Applications** (the interface automatically matches your macOS system language, or click the gear icon to choose any of the 14 built-in languages).

---

## Quick Start Guide

1. **Step 1 — Environment Check**: Confirm bundled components pass self-check and close any USB-holding tools (`Android Studio`, `Parallels`, `VMware`, `Android File Transfer`, `scrcpy`). Plug the USB cable directly into a Mac port rather than an unpowered USB hub.
2. **Step 2 — Select Firmware & Mode**: Drag and drop your official SUNTEK SM6 factory firmware `.zip` (or extracted folder). Choose **Upgrade System (Keep Data)** or **Factory Reset / Clean Reinstall**.
3. **Step 3 — Read-Only Compatibility Check**:
   - Unplug USB from the POS and confirm the screen stays off for at least 5 seconds.
   - Click the blue **Wait & Check Device Compatibility (Read-Only)** button **first**.
   - Without holding any buttons on the POS, plug the USB cable into your Mac.
   - When the check succeeds, **unplug the USB cable** so the POS powers off completely.
4. **Step 4 — Prepare & Flash**: Run **Prepare Files**, optionally inspect **Preview Plan**, then click **Start Wire Flash**, confirm `FLASH-SM6` **before** plugging in the powered-off POS, and wait until writing finishes (`100%`). Do **not** unplug USB or sleep your Mac during writing.
5. **Step 5 — Boot & Post-Flash Verification**: Unplug the USB cable, press the Power button briefly to boot into Android (first boot takes 1–3 minutes), enable **USB Debugging** if desired, and run **Verify Booted POS** to confirm system integrity and cellular baseband health.

---

## Troubleshooting & FAQ

<details>
<summary><b>The POS only shows a charging battery icon or does not respond when plugged in</b></summary>
<p>Ensure you click the blue/red wait button on Mac <b>before</b> connecting USB, and verify the POS was unplugged and completely powered off for at least 5 seconds. If it still enters charging mode, unplug the cable, hold <b>Vol-</b> (or both <b>Vol+ &amp; Vol-</b>), and reconnect USB while the wizard is waiting.</p>
</details>

<details>
<summary><b>The POS screen stays black after an interrupted connection</b></summary>
<p>Unplug the USB cable first (critical so USB power does not keep the power controller latched), click <b>15s Reset</b> in the top toolbar, hold the POS <b>Power</b> button continuously for 15 seconds, pause 1 second, and press Power normally to boot or retry flashing.</p>
</details>

<details>
<summary><b>Why did the wizard block my device or firmware package?</b></summary>
<p>For hardware safety, SUNTEK SM6 Flash Wizard enforces strict read-only device and firmware compatibility checks. OTA update archives, mismatched models, or locked/custom configurations are blocked before any write occurs. Contact SUNTEK Support for the matching factory package.</p>
</details>

<details>
<summary><b>macOS warns about opening an app downloaded from the Internet</b></summary>
<p>Always verify the `.dmg` with `shasum -a 256 -c SHA256SUMS.txt`. The application is Developer-ID signed; if macOS prompts on first launch from Downloads, copy it to <b>Applications</b> first and open it via Control-click -&gt; <b>Open</b>.</p>
</details>

---

## Support

- **Technical Support & Service**: [support@suntekai.com](mailto:support@suntekai.com)
- **Official Website**: [www.suntekai.com](https://www.suntekai.com)

---

<div align="center">
  <img src="https://raw.githubusercontent.com/SUNTEK-Official/.github/main/profile/assets/banner-about-factory.webp" alt="SUNTEK Smart Manufacturing Facility" width="100%">
  <br><br>
  <strong>SUNTEK Technology Co., Ltd.</strong> &mdash; <em>Smart Commercial Terminal Hardware Manufacturer Since 2010</em><br>
  <sub>80+ Export Countries &middot; 5,000,000+ Terminals Shipped &middot; ISO 9001 / ISO 27001 / CE / RoHS</sub>
</div>
