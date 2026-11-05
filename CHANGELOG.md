# Changelog

All notable changes to **TextShot** will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [0.2.0] - 2026-11-05

### 🚀 Enhancements & Packaging Improvements

- **Three-Repository Distribution Architecture**: Decoupled engine source code from binary distribution and package management.
- **Homebrew Tap Support**: Official support for `brew install myself659/tap/textshot` with automated quarantine attribute bypass on installation.
- **Universal Binary Optimization**: Hardened cross-compilation pipeline for arm64 & x86_64.
- **Improved Release Verification**: End-to-end checksum verification and automated release pipeline.

---

## [0.1.0] - 2026-11-05

### 🎉 Initial Public Release

- **Pure Native & Zero Dependencies**: 100% written in Swift 6.0 Strict Concurrency, leveraging Apple's ScreenCaptureKit, Vision, Carbon, and AppKit.
- **Privacy-First (100% On-Device)**: All OCR processing runs locally on the Apple Neural Engine/GPU. Zero network calls, zero tracking, zero telemetry.
- **Permission Minimalism**: Global hotkey (`Ctrl+Shift+T` / `⌃⇧T`) registered via Carbon Events without requiring high-privilege Accessibility permissions.
- **Intelligent CJK Layout Reconstruction**: Built-in ReadingOrder topological matrix engine to seamlessly join Chinese, Japanese, and Korean text while preserving natural word spacing for Latin alphabets.
- **Multi-Language OCR**: Dynamic support for up to 33 languages including Simplified/Traditional/Cantonese Chinese, English, Japanese, Korean, French, German, Spanish, Portuguese, Italian, and Russian.
- **Universal Binary**: Native support for Apple Silicon (arm64, M1-M4) and Intel (x86_64) on macOS 14.0+ (Sonoma, Sequoia).
- **Recent History**: Quick clipboard recall of the last 10 recognitions directly from the menu bar.
- **UI Localization**: Auto-adaptive Chinese and English UI following macOS system preferences.
