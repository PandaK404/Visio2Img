# 常见问题 (FAQ)

## 安装问题

### Q: 安装后看不到插件选项卡？
A:
1. 确保以管理员身份运行了 `install.bat`
2. 确认 Visio 是 64 位版本
3. 检查 Visio 选项 → 加载项 → COM 加载项

### Q: 安装时报错 "regasm.exe not found"？
A:
1. 确保安装了 .NET Framework 4.8
2. 运行 `check_environment.bat` 检查环境

---

## 导出问题

### Q: 导出 PDF 失败？
A:
1. 确保安装了 [ImageMagick](https://imagemagick.org/script/download.php)
2. 安装时勾选 "Add application directory to your system path"
3. 运行 `check_environment.bat` 检查

### Q: 导出的图片模糊？
A: 尝试增大 DPI 值，印刷质量建议 300 DPI 以上。

### Q: 导出的图片有白边？
A: 这是正常的。导出时会自动裁剪到选中图形的边界，但会保留少量边距。

---

## 配色问题

### Q: 屏幕取色没有反应？
A:
1. 确保先点击了颜色块选中要修改的颜色
2. 取色时会显示悬浮窗口跟随鼠标，左键确认，右键或 ESC 取消

### Q: 一键导入颜色失败？
A:
1. 检查格式是否正确：`#RRGGBB` 用逗号分隔
2. 示例：`#237B9F, #71BFB2, #AD0B08`
3. 最多导入 5 个颜色

---

## 其他问题

### Q: 快捷键不起作用？
A:
1. 快捷键默认关闭，需要在设置中启用
2. 修改快捷键后需要重启 Visio 生效
3. 检查是否与其他软件快捷键冲突

### Q: 如何卸载？
A: 以管理员身份运行 `uninstall.bat`

