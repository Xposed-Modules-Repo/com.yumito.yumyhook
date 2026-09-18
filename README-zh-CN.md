# YumyHook（简体中文）

[English](https://github.com/Xposed-Modules-Repo/com.yumito.yumyhook/blob/main/README.md) · **简体中文**

基于 **LSPosed / libxposed** 的 Android 系统层设备伪装模块。通过 Hook `android.os.Build`、
`SystemProperties`、`getprop` 及 Native 属性读取，对作用域内 App 返回可配置的伪装参数，并附带多项
反检测能力。

> 已采用**现代 libxposed API 102**——LSPosed 不再提示模块使用已废弃 API。

> ⚠️ **必须授予 Root 权限。** YumyHook 的配套 App 需要超级用户权限。请在你的 Root 管理器
> ——**Magisk**（或 KernelSU / APatch）——中给 **YumyHook 授予超级用户（Root）权限**。否则主界面
> 会保持锁定，App 无法强停作用域内 App，也无法读取 Root / LSPosed / 框架状态。（LSPosed 本身也
> 需要 Root。）

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
| Root | **必需** —— 在 Magisk / KernelSU / APatch 中给 YumyHook 授予超级用户权限 |

## 安装与使用

1. 下载本仓库 Releases 中的 APK 并安装。
2. **给 YumyHook 授予超级用户权限**：在 Magisk（或 KernelSU / APatch）中，首启时点允许 Root 请求，
   或到 Root 管理器里手动添加。
3. 在 LSPosed 中启用 **YumyHook**，勾选目标 App 作用域。
4. 打开 YumyHook → 开启 **Hook 伪装** → 编辑配置。
5. 强停目标 App 后重新打开验证。

## 免责声明

本工具仅供学习与研究。使用者须遵守当地法律法规及目标应用的服务条款。作者不对滥用造成的任何后果负责。

## 许可

[CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/)（署名-非商业性使用-禁止演绎）。
第三方禁止商用与分发修改版；版权人（Yumito）保留独占商用权。须保留署名与谱系指纹
`YH-LIN-8d4e2f91-yumito`。

Telegram: https://t.me/yumyhook
