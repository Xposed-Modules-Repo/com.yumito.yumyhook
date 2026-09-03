# YumyHook

基于 LSPosed / Xposed 的 Android 系统层设备伪装模块。通过 Hook `android.os.Build`、`SystemProperties`、`getprop` 及 Native 属性读取，对作用域内 App 返回可配置的伪装参数，并附带多项反检测能力。

## 功能

- **四通道属性对齐**：Build 静态字段、Java `SystemProperties`、`getprop`、Native `__system_property_get`
- **多配置档案**：多 Tab 配置、分区保存 Build / SIM 参数
- **反检测**：隐藏 Root / LSPosed、过滤 `/proc/maps`、屏蔽 shell 探测等
- **稳定性**：配置变更后可自动强停作用域内 App；可按 App 单独关闭四通道

## 环境要求

| 项 | 要求 |
|----|------|
| Android | 7.0+（minSdk 24） |
| 框架 | LSPosed（或兼容 Xposed API 54+） |
| Root | 可选（强停作用域 App、读取 LSPosed 配置） |

## 安装与使用

1. 下载本仓库 Releases 中的 APK 并安装
2. 在 LSPosed 中启用 **YumyHook**，勾选目标 App 作用域
3. 打开 YumyHook → 开启 **Hook 伪装** → 编辑配置
4. 强停目标 App 后重新打开验证

## 免责声明

本工具仅供学习与研究。使用者须遵守当地法律法规及目标应用的服务条款。作者不对滥用造成的任何后果负责。

## 许可

[CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)（署名-非商业性使用）

Telegram: https://t.me/yumyhook
