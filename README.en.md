# OmniSense

> 中文说明: [README.md](README.md)

A **DualSense / DualShock 4 companion for Windows** that brings adaptive triggers, telemetry-driven effects, profiles, a virtual gamepad and device hiding together in one clean, focused desktop app. Free to download and use (closed source). This repository is the official **download and auto-update channel**.

## What it does

- **Adaptive trigger workbench** — 12 firmware-grade trigger effects (feedback resistance, weapon, bow, machine gun, multi-position and more), independently editable on both sides, with quick presets, mirroring and one-click release. Effects persist and are restored automatically when the controller reconnects.
- **Racing telemetry effects** — reads the official Data Out stream from the Forza series and drives trigger resistance, throttle weight, drift pulses, lightbar and rumble from live telemetry. No third-party mods required — just enable Data Out in the game.
- **More game telemetry** — a built-in League of Legends Live Client adapter turns in-game events (kills and more) into controller feedback with zero in-game setup; a local HTTP bridge lets you feed custom telemetry for any game.
- **Native game rumble, side by side** — the virtual gamepad passes native game rumble through while telemetry and haptic effects are mixed per motor, never fighting each other.
- **Lightbar & audio passthrough** — set the lightbar color freely; route system audio to the controller speaker and haptic channels (USB).
- **Profiles** — one setup per game: lightbar, triggers, button mapping, mods and rumble all follow the profile; bind an executable and profiles switch automatically.
- **Button mapping** — remap any controller button to another controller button, or straight to a keyboard / mouse key (replace-style: the mapped button stops emitting a controller signal; no macros).
- **Touchpad to mouse** — use the DualSense touchpad as a mouse: one-finger tap-and-drag, two-finger scroll, toggleable anytime.
- **Virtual gamepad** — exposes X360 / DS4 virtual shapes (hot-switchable) for games that do not support DualSense directly.
- **Device guard** — one click hides the physical controller behind HidHide so only OmniSense can use it, ending multi-app contention; coexists automatically with DualSenseY (auto-yield).
- **MOD instruction channel** — receives community DSX-ecosystem mods that send instructions to the local port 6969 (zero setup on the mod side); in-house manifest mods get visual configuration cards.
- **Bilingual UI (Chinese / English)** and **in-app auto-update** — new versions install straight from the app.

## Download & install

Get the latest build from the [Releases](https://github.com/mysoul12138/omnisense-releases/releases/latest) page:

| Download | Purpose |
| --- | --- |
| **OmniSense_<version>_x64-setup.exe** | **Installer (recommended)**: Start-menu / tray integration, auto-update, standard uninstall |
| **OmniSense_<version>_x64.exe** | **Portable**: single file, no installation, just run it |

On first launch the built-in **driver wizard** detects the two open-source drivers the app needs (ViGEmBus, HidHide) and guides you through installing them. Driver installation asks for administrator approval (UAC); day-to-day use of the app does **not** require admin rights.

> Requirements: Windows 10 / 11 x64; DualSense or DualShock 4 controller (USB or Bluetooth).

## Updates

The installed build updates itself: it fetches a signed manifest (latest.json, ed25519 signature plus SHA-256 hashes) from this repository, then swaps in the new version and restarts. Anything that fails verification is refused. You can also download a new version here manually at any time.

## Signing & security

- Every update is cryptographically verified: manifest signature and installer hash must both match.
- The installers are not commercially code-signed, so Windows SmartScreen may show an "unknown publisher" prompt on first run — confirm the file came from this repository's Releases page and choose "Run anyway".
- Licenses for bundled third-party components and drivers are listed in the **NOTICE.md** shipped with every release.
- All configuration and data stay on your machine (%APPDATA%\\OmniSense); the app opens no outbound connections except the update check.

## FAQ

- **Controller does nothing after connecting?** Open the app and check the driver status card under Settings: the virtual gamepad and device guard depend on the ViGEmBus / HidHide drivers — install them from there if missing.
- **Does it conflict with DualSenseY?** No manual handling needed — when DualSenseY is running, OmniSense automatically pauses its output to the controller (enabled by default, can be turned off).
- **How do I uninstall completely?** Settings → Apps → OmniSense → Uninstall (or uninstall.exe in the install folder). Configuration lives in %APPDATA%\\OmniSense — delete it for a full clean.

---

© 2026 OmniSense. This repository is the release channel only; the source code is not public.
