# YumyHook

A system-level device-spoofing module for Android, built on **LSPosed / libxposed**. By hooking
`android.os.Build`, `SystemProperties`, `getprop` and the Native property readers, it returns
configurable fake values to any app inside the LSPosed scope, with a full set of anti-detection
capabilities on top.

> Built on the **modern libxposed API 102** — LSPosed no longer flags the module as using
> deprecated APIs.

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
| Root | Optional (force-stop scoped apps, read the LSPosed config) |

## Install & Use

1. Download and install the APK from this repo's Releases.
2. Enable **YumyHook** in LSPosed and select the target apps in its scope.
3. Open YumyHook → turn on **Enable Hook Spoofing** → edit the config.
4. Force-stop the target app and reopen it to verify.

## Disclaimer

For study and research only. Users must comply with local laws and the target apps' terms of
service. The author is not responsible for any consequences of misuse.

## License

[CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/) — Attribution, NonCommercial,
NoDerivatives. Third-party commercial use and distribution of modified builds are prohibited; the
copyright holder (Yumito) reserves the exclusive commercial right. Attribution and the
lineage fingerprint `YH-LIN-8d4e2f91-yumito` must be preserved.

Telegram: https://t.me/yumyhook

---

# YumyHook（简体中文）

基于 **LSPosed / libxposed** 的 Android 系统层设备伪装模块。通过 Hook `android.os.Build`、
`SystemProperties`、`getprop` 及 Native 属性读取，对作用域内 App 返回可配置的伪装参数，并附带多项
反检测能力。

> 已采用**现代 libxposed API 102**——LSPosed 不再提示模块使用已废弃 API。

## 功能

- **按 App 属性伪装（四通道）**：`android.os.Build` 静态字段、Java `SystemProperties`、`getprop`、
  Native `__system_property_get`，四者保持一致。
- **SIM 卡伪装与自定义**：运营商 MCC/MNC、运营商名称、ISO 国家、SIM 状态。
- **设备标识伪装**：IMEI / IMSI / 手机号 / Android ID（部分或完整）。
- **自定义位置定位**：伪装 GPS / 网络 / Fused 定位（纬度/经度/海拔/精度）。
- **其它身份**：Wi-Fi 信息、安装来源（Google Play）、浏览器指纹（WebView UA）。
- **反检测**：隐藏 Root（su/Magisk）、隐藏 LSPosed/Xposed（maps、特征文件、模块列表、Java 类指纹）、
  隐藏开发者选项 / VPN / 代理 / 飞行模式 / Wi-Fi 列表 / 蓝牙、阻止局域网扫描；系统框架作用域
  （system_server）Root 属性隐藏。
- **多配置档案**、按 App 单独覆盖四通道/Native、配置变更后（有 Root）自动强停作用域内 App。
- **App 内语言切换**（English / 中文）位于主页；默认英文，长期缓存。

## 环境要求

| 项 | 要求 |
|----|------|
| Android | 8.0+（minSdk 26） |
| 框架 | LSPosed，支持 **libxposed API 100+**（推荐 102） |
| Root | 可选（强停作用域 App、读取 LSPosed 配置） |

## 安装与使用

1. 下载本仓库 Releases 中的 APK 并安装
2. 在 LSPosed 中启用 **YumyHook**，勾选目标 App 作用域
3. 打开 YumyHook → 开启 **Hook 伪装** → 编辑配置
4. 强停目标 App 后重新打开验证

## 免责声明

本工具仅供学习与研究。使用者须遵守当地法律法规及目标应用的服务条款。作者不对滥用造成的任何后果负责。

## 许可

[CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/)（署名-非商业性使用-禁止演绎）。
第三方禁止商用与分发修改版；版权人（Yumito）保留独占商用权。须保留署名与谱系指纹
`YH-LIN-8d4e2f91-yumito`。

Telegram: https://t.me/yumyhook
