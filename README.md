# Visio2Img

将 Microsoft Visio 选中图形导出为高质量图片的插件。

> 📦 **v1.3.1** | [下载](https://github.com/PandaK404/Visio2Img/releases) | [更新日志](CHANGELOG.md)

![Ribbon 界面 ](fig/ribbon-ui.png)

![ 配色管理 ](fig/palette-manager.png)

## 为什么开发这个插件？

在 Visio 中导出图片一直是一件令人头疼的事情：

- 每次导出都要重复 " 选择文件夹 → 输入文件名 → 选择格式 " 的繁琐操作
- 修改图形后想覆盖原文件，又要重新走一遍完整流程
- Visio 不支持直接导出为 PDF 格式
- 批量导出多个图形时，需要逐个手动操作
- **Visio 不支持自定义保存配色方案**，每次都要手动输入颜色值

作为一名经常（其实也不怎么经常）需要在论文中插入 Visio 图形的用户，作者深受其苦，早就想开发一个插件来解决这些问题。奈何早年苦于不会 C# 语言，这个想法一直无法实现。近来 AI 编程助手大行其道，借助 AI 的帮助，终于将这个多年的想法变成了现实。于是便有了 **Visio2Img**，让导出图片变得简单高效。

## ✨ 功能特性

- ⚡ **快速导出**：一键导出，告别繁琐操作
- 🔄 **上次导出**：一键覆盖上次文件，无需重选路径
- 🎨 **一键配色**：内置配色方案，支持屏幕取色、批量导入
- 📦 **批量导出**：多图形分别导出为单独文件
- 🖼️ **多格式**： TIFF、 PNG、 JPEG、 EMF、 SVG、 PDF
- ⌨️ **快捷键**：可配置全局快捷键

## 📥 快速安装

### 预编译版（推荐）

1. [ 下载最新版本 ](https://github.com/PandaK404/Visio2Img/releases)
2. 解压后 **右键** `install.bat` → **以管理员身份运行**
3. 启动 Visio，查看 **Visio2Img** 选项卡

### 从源码编译

> 🚧 源码正在整理中，稍后开放。目前请使用预编译版本。

## 📖 文档

- [ 使用指南 ](docs/usage.md) - 详细功能说明
- [ 常见问题 ](docs/faq.md) - FAQ

## 🎨 配色推荐

推荐使用 [ 学术期刊配色推荐器 ](http://lcpmgh.com/colors/) 获取 Science、 Nature 等顶刊配色方案，然后使用 " 一键导入 " 功能快速导入！

## 💻 系统要求

- Windows 10/11 64 位
- Microsoft Visio 2016+ (64 位 )
- .NET Framework 4.8
- [ImageMagick](https://imagemagick.org/script/download.php)（导出 PDF 需要）

## 📜 许可证

MIT License

---

**作者**：[PandaK404](https://github.com/PandaK404) | 觉得好用？给个 ⭐ Star！
