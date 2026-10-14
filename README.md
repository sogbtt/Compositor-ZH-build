# 云端编译 Compositor 简体中文版

在 GitHub 的 macos-26 Apple Silicon 标准运行器上，使用 Xcode 26.6 构建。
此仓库只需保存构建流程与汉化补丁；工作流下载固定官方源码后应用补丁。
用户电脑不需要安装 Xcode。

已准备流程，尚未运行成功，不能把本目录当作已构建的应用。

1. 将本目录完整上传到一个新的 GitHub 仓库（包括隐藏的 `.github` 目录）。
2. 打开仓库的 Actions → Build Chinese Compositor → Run workflow。
3. 完成后下载 `Compositor-1.5.2-zh-Hans-arm64` 构建附件。
4. 解压 GitHub 附件，再解压内部的 `Compositor-1.5.2-zh-Hans-arm64.zip`，得到 Compositor.app。
5. 拖到“应用程序”。运行需要 Apple Silicon、macOS 26 或更新版本。

应用使用临时本地签名，没有开发者证书公证；macOS 可能要求通过系统设置的“隐私与安全性”明确允许运行。
工作流只有构建和测试都通过才上传应用；失败时可下载诊断日志，修复后重新运行。
官方标准运行器用于公开仓库免费；私有仓库使用账号额度，额度耗尽后可能计费。
本流程没有向官方 Compositor 仓库提交代码，也没有发布安装包。
