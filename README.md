# TextShot

<p align="center">
  <strong>Lightweight, pure native macOS menu bar OCR utility.</strong><br>
  <em>Zero third-party dependencies. 100% on-device privacy. Built for modern macOS.</em>
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
  English | <a href="README_zh.md">简体中文</a>
</p>

---

## 💡 Overview

**TextShot** is a high-performance, native macOS menu bar text extraction and optical character recognition (OCR) utility. 

Press the global hotkey **Ctrl+Shift+T (⌃⇧T)**, drag to select any region on your screen, and release the mouse. The recognized text is copied silently to your system clipboard within milliseconds.

- ⚡️ **Pure Native & Zero Dependencies**: Written 100% in Swift 6.0 Strict Concurrency, powered by Apple's native frameworks (`ScreenCaptureKit`, `Vision`, `AppKit`, `Carbon`). No Electron, no web wrappers, no third-party libraries.
- 🔒 **100% On-Device Privacy**: OCR processing runs entirely on your local Apple Neural Engine / GPU. Zero network calls, zero telemetry, zero analytics.
- ⌨️ **No Accessibility Permissions Required**: Global shortcuts are registered via lightweight Carbon Events without demanding high-privilege macOS Accessibility access. Safe and compliant for enterprise environments.
- 🌍 **Multi-Language OCR (33 Languages)**: Dynamically prioritizes your macOS system language preferences with Apple Vision automatic language detection. Natively supports Simplified/Traditional/Cantonese Chinese, English, Japanese, Korean, French, German, Spanish, Portuguese, Italian, Russian, and more.
- 📐 **Intelligent CJK Layout Reconstruction**: Built-in topological reading order engine seamlessly joins Asian characters without phantom line-breaks or awkward spaces, while preserving natural whitespace for Latin text.
- 🖥️ **Multi-Display & Retina Ready**: Flawlessly handles heterogeneous multi-monitor setups, Retina scaling ratios, negative coordinates, and display rotations.
- 📜 **Recent History**: Locally saves your last 10 recognitions for quick one-click recall directly from the menu bar.

---

## 🚀 Download & Installation

### Option 1: Direct Download (Recommended)

Download the latest precompiled Universal release package:

📦 **[Download TextShot v0.4.0 (macOS Universal)](https://github.com/myself659/TextShot/releases/download/v0.4.0/TextShot-0.4.0-macos-universal.zip)**

Extract the ZIP archive and move `TextShot.app` to your `/Applications` folder.

> [!NOTE]
> The release package includes native universal binaries for both **Apple Silicon (M1/M2/M3/M4)** and **Intel (x86_64)**.
> If macOS displays *"TextShot can't be opened because Apple cannot check it for malicious software"* (due to community ad-hoc signing), run:
> ```sh
> xattr -cr /Applications/TextShot.app
> ```
> Or open **System Settings → Privacy & Security** and click **"Open Anyway"**.

### Option 2: Install via Homebrew

```sh
brew install myself659/tap/textshot
```

---

## 📖 Usage Guide

- **Capture Text**: Press **Ctrl+Shift+T (⌃⇧T)** to display a translucent selection overlay. Drag over any text on any display, then release. The extracted text is copied to your clipboard instantly.
- **Cancel Selection**: Press **Esc** or right-click anytime during selection to abort without affecting your clipboard.
- **Custom Shortcut**:
  1. Click the menu bar icon → **"Shortcut Settings…"**.
  2. Press your desired key combination (must include Control ⌃, Option ⌥, or Command ⌘).
  3. Real-time conflict detection automatically checks against macOS system shortcuts.
  4. Manual key/modifier pickers are also available.
- **Clipboard History**: Access the "Recent History" submenu (stores up to 10 items) to recopy previous extractions or clear history.

---

## 🔐 Permissions (Screen Recording)

TextShot **only requests Screen Recording permission**. It does NOT require Accessibility, Automation, or Network permissions.

1. Press **Ctrl+Shift+T** or click the menu bar item → **"Capture Text"**.
2. If ungranted, a guidance window appears. Click **"Grant Screen Recording…"** and allow in the system prompt.
3. If no system prompt appears, click **"Open System Settings…"**, navigate to **Privacy & Security → Screen & System Audio Recording**, and enable **TextShot**.
4. Once enabled, returning to TextShot will automatically detect authorization. Click **"Restart"** if the system permission cache requires a refresh.

> [!TIP]
> In normal usage, do not run global `tccutil reset`. If you experience persistent permission caching issues after replacing binaries, reset only TextShot's entry:
> ```sh
> tccutil reset ScreenCapture local.TextShot
> ```

---

## 🛡️ Checksum Verification

Every official release archive has its SHA256 checksum tracked under the [`releases/`](releases/) directory:

```sh
# Verify v0.1.0 release archive
shasum -a 256 -c releases/v0.1.0/SHA256SUMS.txt
```

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
All native Apple frameworks and APIs used comply with standard macOS SDK terms.
