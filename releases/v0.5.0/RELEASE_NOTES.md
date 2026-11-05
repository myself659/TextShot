TextShot 0.5.0 — 原生 macOS 菜单栏文字提取工具。

- **系统要求：macOS 14.0 或更新版本**。
- **通用应用：Apple Silicon（arm64）与 Intel（x86_64）**。
- 下载 `TextShot-0.5.0-macos-universal.zip`，解压后将 TextShot.app 放到“应用程序”。
- 默认按 **Ctrl+Shift+T（⌃⇧T）** 拖拽提取中英文文字；首次截取时按引导开启屏幕录制权限。
- 可通过“快捷键设置…”更换组合；授权后返回应用会自动检查状态，必要时可重新启动。
- 最近 10 条识别历史保存在本机；无需辅助功能授权，无第三方运行依赖。

下载校验：`shasum -a 256 -c SHA256SUMS.txt`（校验文件和 ZIP 放在同一目录）。

此发布包为开源社区构建（Ad-hoc 签名）。若初次打开提示“无法打开，因为无法验证开发者”，请在终端执行：`xattr -cr /Applications/TextShot.app` 或在“系统设置 → 隐私与安全性”中点击“仍要打开”。
