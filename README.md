<div align="center">
  <img src="https://cdn.phototourl.com/free/2026-04-18-fc4b93c1-a011-4c2d-b426-56f1661b9f11.jpg" width="120" alt="HwBOS Logo">
  <h1>HwBOS 桌面系统</h1>
  <p><strong>开箱即用的智能桌面环境 | 基于 NW.js 的完整操作系统模拟</strong></p>
  
  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
  [![NW.js](https://img.shields.io/badge/NW.js-0.90.0+-blue)](https://nwjs.io/)
  [![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)](https://github.com/)
</div>

---

## ✨ 特性

- 🖥️ **完整桌面体验** - 任务栏、开始菜单、桌面图标、窗口管理
- 🎨 **现代 UI 设计** - Windows 11 风格，支持深色/浅色主题
- 🪟 **多窗口管理** - 拖动、调整大小、最大化/最小化、动画效果
- 🔧 **系统托盘** - 音量调节、网络状态、电池指示、输入法切换
- 📦 **应用管理** - 添加/编辑/删除自定义应用，支持自定义图标
- 🌐 **内置浏览器** - 书签、历史记录、前进后退
- 💾 **数据持久化** - 所有设置、壁纸、应用列表自动保存
- 🚀 **即开即用** - 无需编译、无需安装、无需后端服务器

---

## 📦 打包说明

> **重要提示：本版本是“无需编译”的绿色发行版**

### 文件结构
```
HwBOS/
├── nw.exe                    # NW.js 主程序
├── nw.dll                    # NW.js 核心库
├── package.json              # 应用配置
├── index.html                # 主界面
├── style.css                 # 样式文件
├── app.js                    # 核心逻辑
└── (你添加的软件)            # 放在同一目录，HwBOS 可直接调用
```

### 使用步骤
1. **下载 NW.js SDK** 从 [nwjs.io](https://nwjs.io)（选择 SDK 版本以获得开发者工具）
2. 将本项目的所有文件（`index.html`, `style.css`, `app.js`, `package.json`）放入 NW.js 根目录
3. **把你想要集成的软件（如微信、QQ、游戏等）也放入该目录**
4. 双击 `nw.exe` 即可运行 HwBOS 桌面系统
5. 在桌面右键 → **添加应用**，填写软件名称和可执行文件路径（支持相对路径，如 `./QQ.exe`）

> 💡 **提示**：你可以将任何绿色软件、单文件程序放入 HwBOS 文件夹，系统会直接调用它们，就像真正的操作系统一样！

---

## 🎯 核心功能展示

### 桌面环境
- **图标拖拽**：长按拖动图标到任意位置，位置自动保存
- **框选多选**：鼠标在桌面空白处拖动可框选多个图标
- **右键菜单**：刷新桌面、添加应用、个性化、分辨率设置
- **任务栏**：开始菜单、应用切换、时钟、显示桌面

### 应用启动
- **系统应用**：自动调用 `notepad.exe`、`calc.exe` 等 Windows 内置程序
- **自定义应用**：支持任何 `.exe` 文件，可设置启动参数
- **内置浏览器**：完整的网页浏览体验，支持书签和历史记录

### 个性化设置
- **主题**：深色/浅色模式，一键切换
- **壁纸**：支持 PNG/JPG 图片，自动适应屏幕
- **登录背景**：自定义登录界面背景
- **主题色**：8 种预设颜色可选

### 系统工具
- **音量控制**：滑块调节，支持静音
- **网络状态**：模拟网络连接显示（可扩展）
- **电池指示**：模拟电量消耗和充电动画
- **输入法切换**：中/英/日/韩文切换演示

---

## 🔧 技术栈

| 技术 | 用途 |
|------|------|
| **NW.js** | 跨平台桌面应用框架（Node.js + Chromium） |
| **HTML5/CSS3** | 界面结构与样式 |
| **原生 JavaScript** | 核心逻辑、窗口管理、事件处理 |
| **Node.js (child_process)** | 调用系统外部程序 |
| **localStorage / fs** | 数据持久化 |

---

## 📸 截图预览

| 登录界面 | 桌面环境 | 设置面板 |
|---------|---------|---------|
| 毛玻璃效果登录卡片 | 完整任务栏 + 桌面图标 | 深色/浅色主题切换 |

---

## 🛠️ 开发与扩展

### 添加新的系统应用
在 `app.js` 的 `DEFAULT_APPS` 数组中添加：

{
    id: '4',
    name: '你的应用',
    icon: '🚀',
    iconPath: null,              // 或 './icon.png'
    executable: './your_app.exe', // 支持相对路径
    args: '',
    type: 'system',
    width: null,
    height: null,
    x: 12,
    y: 12 + (appsList.length % 4) * 85
}
```

### 修改主题色
在 `style.css` 中搜索 `--theme-color` 变量，或通过设置面板直接选择。

### 数据存储位置
- Windows: `C:\Users\用户名\HwBOS_Data\`
- macOS/Linux: `~/HwBOS_Data/`

---

## 📜 开源协议

本项目采用 **MIT 协议**，你可以自由使用、修改、分发，但需保留版权声明。

```
MIT License

Copyright (c) 2026 SYSTEM-WINOS-RE, 4795_Tester

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

---

## 🤝 贡献与支持

- 🐛 发现 Bug？请提交 [Issue](https://github.com/your-repo/issues)
- 💡 有新想法？欢迎 Fork 并提交 Pull Request
- ⭐ 如果喜欢这个项目，请给个 Star 支持一下！

---

## 🙏 致谢

- [NW.js](https://nwjs.io/) - 强大的桌面应用框架
- [Microsoft](https://www.microsoft.com/) - Windows 11 设计灵感
- 所有参与测试和提出建议的朋友

---

<div align="center">
  <sub>Built with ❤️ by SYSTEM-WINOS-RE & 4795_Tester</sub><br>
  <sub>© 2026 HwBOS - 自研操作系统</sub>
</div>
```
