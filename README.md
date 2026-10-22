# FnMacBypass

[![Release](https://img.shields.io/github/v/release/AlexGRDev/FnMacBypass?include_prereleases)](https://github.com/AlexGRDev/FnMacBypass/releases)
[![Platform](https://img.shields.io/badge/platform-iOS%20%7C%20macOS%20(Simulator)-blue)]()
[![License](https://img.shields.io/badge/license-MIT-green)]()

A comprehensive compatibility toolkit and hardware spoofer for Fortnite running on iOS or Mac Simulators.

## 🚀 Features
- **Hardware Spoofing**: Emulates an `iPad14,3` (iPad Air 5) running iOS 17.5, matching expected Apple hardware signatures for `sysctl` and `UIDevice`.
- **Jailbreak Bypass**: Hides Cydia paths, blocks `/var/jb` detection, and hooks `stat`/`open` syscalls to return `ENOENT`.
- **Environment Fixes**: Redirects `NSURLSession` chunk and bundle downloads to the correct `FortniteGame` directories.
- **Network Stability**: Intercepts HTTP requests to prevent matchmaking crashes and connection timeouts.
- **EAC Evasion**: Bypasses Firebase `checkExpectedBundleID` and hides injected dylibs from `dladdr`.

## 📦 Installation (Sideloading)

To install FnMacBypass on your iOS device, you will need a sideloading tool (such as **Sideloadly**, **AltStore**, or **TrollStore**) and a valid Fortnite `.ipa` file.

### Requirements:
- A decrypted `.ipa` of Fortnite (compatible with your iOS version).
- The `FnMacBypass.dylib` from the [Releases](https://github.com/AlexGRDev/FnMacBypass/releases) page.
- A sideloading tool installed on your Mac/PC (e.g., [Sideloadly](https://sideloadly.io/)).

### Steps:

1. **Download the latest `.dylib`** from the [Releases](https://github.com/AlexGRDev/FnMacBypass/releases) page.
2. Open your sideloading tool (e.g., Sideloadly).
3. Drag and drop the Fortnite `.ipa` file into the tool.
4. In the **"Dylib Injection"** or **"Advanced Options"** section, select the `FnMacBypass.dylib` you downloaded. (In Sideloadly, this is done by clicking the `+` icon under "Inject Dylibs").
5. Enter your Apple ID to sign the app.
6. Click **Start** to inject, sign, and install the modified IPA to your device.
7. Once installed, trust the developer certificate in `Settings > General > VPN & Device Management`.
8. Launch the game and enjoy!

> **Note for Jailbroken/TrollStore users:** If you are using TrollStore, you can simply install the Fortnite `.ipa` normally, and use **TrollFools** to inject the `.dylib` directly into the installed app without needing a PC.

## 🐛 Debugging & Logs

If you are using a Developer build (Debug mode), you can monitor the tweak's logs in real-time using macOS `log stream`:

```bash
sudo log stream --predicate 'subsystem == "com.alexgrdev.fnmacbypass"' --level debug
