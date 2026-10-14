# Compositor 1.5.2 简体中文版云端构建

基于官方最新 v1.5.2 应用源码，提供简体中文与英文切换。用户电脑无需安装 Xcode。

已成功构建修复版并运行 4 项本地化测试；Release 启动验证通过。修复版也已在 Apple Silicon、macOS 27 的用户电脑上成功打开。第一轮产物存在 Sparkle 启动崩溃，请使用含 `fixes/startup-fix.patch` 的新构建。

## 下载及安装

1. 打开 Actions 中最新成功的 **Build Chinese Compositor**。
2. 下载 `Compositor-1.5.2-zh-Hans-arm64` 附件。
3. 解压外层附件，再解压内部 `Compositor-1.5.2-zh-Hans-arm64.zip`。
4. 保存工程并退出旧版，将 `Compositor.app` 拖入“应用程序”。

需要 Apple Silicon 与 macOS 26 或更新版本。应用采用临时本地签名，未做 Developer ID 签名及 Apple 公证。

菜单 **Compositor → 语言… / Language…** 可选择简体中文、English 或跟随系统；保存工程并重启后生效。

## 再次构建

Actions → **Build Chinese Compositor → Run workflow**。运行器为 macos-26 Apple Silicon，Xcode 26.6。流程依次应用官方固定源码、`compositor-zh-Hans.patch` 与 `fixes/startup-fix.patch`；通过独立中英文资源检查、完整 Release 构建、15 秒实际启动检查、4 项 XCTest、签名与资源检查后才上传应用。

官方基线：`43d691b67995e924965bcd520f8b300f96b7d5b8`。最终汉化源码提交：`eec15ee00ac2ba67498f1f1cdc115e71f0ce5713`。

初次启动崩溃源于 Sparkle 的加载与签名限制。修复删除已停用的 Sparkle 依赖，保留沙盒与 hardened runtime。自动安装官方更新停用，避免更新覆盖汉化；“检查更新…”提供官方 Releases 页面。

提供 1,275 条中英文资源。已有用户内容、内部存储标识、快捷键、PSD 字段、品牌与标准缩写保留原样。未做官方全部测试与每个编辑器窗口的人工检查。

MIT 许可证与原项目版权保留。本仓库未向官方仓库提交 PR。
