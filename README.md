# OmniSense 发布通道 · Release channel

**OmniSense（万象手柄）** 的官方下载与自动更新通道。

## 下载 / Download

到 [Releases](https://github.com/mysoul12138/omnisense-releases/releases/latest) 页面下载：

- **安装版**：`OmniSense_<版本>_x64-setup.exe`（首次安装用）
- **便携版**：`OmniSense_<版本>_x64.exe`（免安装直接运行）

应用内的自动更新直接从本仓库读取 `latest.json`（ed25519 签名 + 安装包 SHA-256 双重校验）。

> 系统要求：Windows 10 / 11 x64。

The in-app updater reads the signed `latest.json` from this channel and
verifies both the ed25519 signature and the payload SHA-256 before applying.
Third-party driver notices and licences ship with each release as `NOTICE.md`.
