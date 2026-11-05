# TextShot 瞬摘

<p align="center">
  <strong>轻量、纯原生的 macOS 菜单栏文字提取与屏幕 OCR 工具</strong><br>
  <em>Lightweight, pure native macOS menu bar OCR utility. Zero third-party dependencies, 100% on-device privacy.</em>
</p>

<p align="center">
  <a href="https://github.com/myself659/TextShot/releases"><img src="https://img.shields.io/github/v/release/myself659/TextShot?include_prereleases&color=blue" alt="Latest Release"></a>
  <a href="https://apple.com/macos"><img src="https://img.shields.io/badge/Platform-macOS%2014.0%2B-lightgrey?logo=apple" alt="macOS 14.0+"></a>
  <a href="https://apple.com/macos"><img src="https://img.shields.io/badge/Arch-Universal%20(Apple%20Silicon%20%7C%20Intel)-orange" alt="Universal Binary"></a>
  <a href="https://swift.org"><img src="https://img.shields.io/badge/Swift-6.0-F05138?logo=swift&logoColor=white" alt="Swift 6.0"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License: MIT"></a>
  <a href="#"><img src="https://img.shields.io/badge/Dependencies-0-brightgreen" alt="Dependencies: Zero"></a>
</p>

<p align="center">
  <a href="README.md">English</a> | 简体中文
</p>

---

## 💡 简介 (Overview)

**TextShot** 是一款专为 macOS 打造的高性能菜单栏文字提取工具。只需按下全局快捷键 **Ctrl+Shift+T（⌃⇧T）**，框选屏幕任意区域，松开鼠标即可毫秒级将多语言识别结果静默复制到系统剪贴板。

- ⚡️ **纯原生零依赖**：全代码基于 Swift 6.0 编写，完全采用 Apple 官方框架（ScreenCaptureKit、Vision、AppKit、Carbon），无任何第三方 Pods/SPM 依赖。
- 🔒 **100% 本地离线 (Privacy First)**：OCR 识别全部在设备本地神经引擎/GPU 运行，绝不连接任何云端 API，无网络请求，无埋点追踪。
- ⌨️ **免辅助功能权限**：基于 Carbon 注册全局热键，避免向系统申请高敏感的“辅助功能（Accessibility）”控制权限，企业合规友好。
- 🌍 **全语言 OCR 识别扩充**：动态优先匹配 macOS 系统语言设置，启用 Vision 自动语言检测，原生支持中（简/繁/粤）、英、日、韩、法、德、西、俄、葡、意等多达 33 种语言的高精度识别。
- 📐 **智能 CJK 阅读顺序重构**：内置几何拓扑算法，彻底解决中英文混排、多栏文本断行与多余空格问题。
- 🖥️ **多显示器与视网膜适配**：原生支持多屏异构分辨率、Retina 缩放倍率对齐、负坐标副屏及屏幕旋转。
- 📜 **最近历史回溯**：本地自动保存最近 10 条识别记录，支持菜单栏一键重拷与清空。

---

## 🚀 下载与安装 (Installation)

### 方式一：下载预编译发布包 (Recommended)

在 [Releases](https://github.com/myself659/TextShot/releases) 下载最新版本的 Universal 通用发布包：

📦 **[下载 TextShot v0.1.0 (macOS Universal)](https://github.com/myself659/TextShot/releases/download/v0.1.0/TextShot-0.1.0-macos-universal.zip)**

解压并将 `TextShot.app` 拖入系统 **“应用程序”**（`/Applications`）文件夹中即可使用。

> [!NOTE]
> 正式发布包同时包含 Apple Silicon (M1/M2/M3/M4) 与 Intel (x86_64) 原生架构。
> 若初次打开提示“无法打开，因为无法验证开发者”，请在终端执行：
> ```sh
> xattr -cr /Applications/TextShot.app
> ```
> 或前往 macOS **“系统设置” → “隐私与安全性”** 中点击 **“仍要打开”**。

### 方式二：通过 Homebrew 安装

```sh
brew install myself659/tap/textshot
```

---

## 📖 使用指南 (Usage)

1. **截取文字**：按默认快捷键 **Ctrl+Shift+T（⌃⇧T）**，屏幕将显示半透明遮罩。在任意屏幕上按住鼠标左键并拖拽框选文字，松开鼠标即自动开始静默 OCR 识别并写入剪贴板。
2. **取消选区**：框选过程中按键盘 **Esc** 键或点击鼠标右键即可取消，原有剪贴板内容不受任何影响。
3. **自定义快捷键**：点击菜单栏图标 → **“快捷键设置…”**，按下新的组合键（包含 ⌃、⌥ 或 ⌘），系统会自动校验是否与 macOS 系统内置热键冲突。
4. **历史记录**：菜单栏内置“最近识别”列表（最多保留 10 条），点击即可再次复制。

---

## 🔐 首次权限配置 (Screen Recording Permission)

TextShot **仅需要且仅申请“屏幕录制”权限**，不需要辅助功能或自动化权限。

1. 打开应用后，按快捷键 **Ctrl+Shift+T** 或点击菜单栏图标 → **“截取文字”**。
2. 尚未授权时，应用会弹出说明窗口。点击 **“允许屏幕录制…”**，系统将弹出授权提示，点击允许。
3. 若系统未直接弹窗，点击窗口中的 **“打开系统设置…”**，在系统设置 **“隐私与安全性” → “屏幕录制”** 中勾选 **TextShot**。
4. 授权完成后切换回 TextShot 会自动检测就绪；若系统权限缓存延迟，点击窗口中的 **“重新启动”** 即可立即生效。

> [!TIP]
> 正常使用中请勿随意运行全局 `tccutil reset`。若遇到极端权限缓存问题，可定向执行：
> ```sh
> tccutil reset ScreenCapture local.TextShot
> ```

---

## 🛡️ 校验发布包完整性 (Checksum Verification)

每个发布版本的 SHA256 校验和均归档在 [`releases/`](releases/) 目录中：

```sh
# 验证 v0.1.0 发布包
shasum -a 256 -c releases/v0.1.0/SHA256SUMS.txt
```

---

## 📄 开源许可证 (License)

本项目遵循 [MIT License](LICENSE) 开源协议。
