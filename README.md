# YumyHook

**English** · [简体中文](https://github.com/Xposed-Modules-Repo/com.yumito.yumyhook/blob/main/README-zh-CN.md)

A system-level device-spoofing module for Android, built on **LSPosed / libxposed**. By hooking
`android.os.Build`, `SystemProperties`, `getprop` and the Native property readers, it returns
configurable fake values to any app inside the LSPosed scope, with a full set of anti-detection
capabilities on top.

> Built on the **modern libxposed API 102** — LSPosed no longer flags the module as using
> deprecated APIs.

> ⚠️ **Root is required.** YumyHook's companion app needs Superuser access. In your root manager
> — **Magisk** (or KernelSU / APatch) — grant **Superuser permission to YumyHook**. Without it the
> home screen stays locked and the app cannot force-stop scoped apps or read Root / LSPosed /
> framework status. (LSPosed itself also requires root.)

## Features

- **Per-app property spoofing (four channels)** — `android.os.Build` static fields, Java
  `SystemProperties`, `getprop`, and Native `__system_property_get`, kept mutually consistent.
- **SIM card spoofing & customization** — carrier MCC/MNC, operator name, ISO country, SIM state.
- **Device identifier spoofing** — IMEI / IMSI / phone number / Android ID (partial or full).
- **Custom location** — spoof GPS / network / fused location (lat/lng/altitude/accuracy).
- **Other identity** — Wi-Fi info, install source (Google Play), browser fingerprint (WebView UA).
- **Anti-detection** — hide Root (su/Magisk), hide LSPosed/Xposed (maps, files, module list, class
  fingerprints), hide developer options / VPN / proxy / airplane mode / Wi-Fi list / Bluetooth,
  block LAN scan; framework-scope (system_server) root-property hiding.
- **Multi-profile config**, per-app four-channel/native override, and auto force-stop of scoped
  apps on config change (with Root).
- **In-app language switch** (English / 中文) on the home screen; default English, cached across
  launches.

## Requirements

| Item | Requirement |
|------|-------------|
| Android | 8.0+ (minSdk 26) |
| Framework | LSPosed with **libxposed API 100+** (API 102 recommended) |
| Root | **Required** — grant Superuser to YumyHook in Magisk / KernelSU / APatch |

## Install & Use

1. Download and install the APK from this repo's Releases.
2. **Grant YumyHook Superuser permission** in Magisk (or KernelSU / APatch) — approve the root
   prompt on first launch, or add it manually in the root manager.
3. Enable **YumyHook** in LSPosed and select the target apps in its scope.
4. Open YumyHook → turn on **Enable Hook Spoofing** → edit the config.
5. Force-stop the target app and reopen it to verify.

## Disclaimer

For study and research only. Users must comply with local laws and the target apps' terms of
service. The author is not responsible for any consequences of misuse.

## License

[CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/) — Attribution, NonCommercial,
NoDerivatives. Third-party commercial use and distribution of modified builds are prohibited; the
copyright holder (Yumito) reserves the exclusive commercial right. Attribution and the
lineage fingerprint `YH-LIN-8d4e2f91-yumito` must be preserved.

Telegram: https://t.me/yumyhook
