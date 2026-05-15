# 🌌 ZMK Firmware for Charybdis

![ZMK Build](https://img.shields.io/github/actions/workflow/status/HeeTuic/zmk-for-charybdis/build.yml?label=ZMK%20Build&style=for-the-badge&color=2ac3de)
![Keymap Draw](https://img.shields.io/github/actions/workflow/status/HeeTuic/zmk-for-charybdis/draw-keymaps.yml?label=Keymap%20Draw&style=for-the-badge&color=bb9af7)

本项目为 **Charybdis** 分体轨迹球键盘提供开箱即用的 ZMK 固件支持。专注于无线化、热插拔与极致的人体工学体验，让你彻底告别手腕在键盘与鼠标之间的频繁切换。

---

## 🗺️ 键位布局 (Keymap Layout)

*每次提交 `.keymap` 文件，本图均由 GitHub Actions 自动生成并更新。*

![Charybdis Keymap](img/keymap.svg)

> **💡 视觉图例说明：**
> *   **基础字符**：正常点按触发的键位。
> *   **蓝色小字 (Hold)**：长按该键时触发的修饰键或层切换（如 `Ctrl`, `Shift`）。
> *   **橙色连线 (Combos)**：同时按下被连线的键位，触发橙色标识的特殊功能。
> *   **高亮底色 (Layer)**：大拇指区的切层主键。

---

## ✨ 核心特性 (Features)

*   **⚡ 专为 MiaoMiao 定制版优化**：深度适配热插拔无线版 Charybdis，优化了无线连接的稳定性和电池功耗表现。
*   **🔗 完美向下兼容**：底层设备树逻辑保持对 BastardKB 官方原版（焊接版/Soldered Version）的全面兼容。
*   **🖱️ 沉浸式轨迹球体验**：集成了精准的光标移动与自动鼠标层（Auto-Mouse Layer），包含自定义的滚轮操作与多按键点击。
*   **🎨 现代感键位可视化**：内置自动化工作流，彻底告别枯燥的代码阅读，以最高级的设计呈现你的每一处键位修改。

---

## 🛠️ 网页图形化改键 (Web GUI Editing)

告别繁琐的本地环境搭建与代码修改，本项目已完美适配**两种**最流行的零代码网页端配置工具：

### 1. ZMK Studio (次世代实时修改)
ZMK 官方力推的全新配置平台，提供现代感十足的交互界面，支持**免刷机实时修改**。
*   **如何使用**：使用受支持的 Chromium 内核浏览器（如 Chrome / Edge），打开并连接 [ZMK Studio](https://zmk.studio/)。
*   **优势**：通过 Web Serial 或 Web Bluetooth 直接与键盘通讯。修改即刻生效，无需等待 GitHub 云端编译。

### 2. Keymap Editor (经典云端编译)
社区最成熟、最易上手的网页端改键工具，适合进行全局的层级大修与复杂的 Combos 设计。
*   **如何使用**：访问 [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/)，授权登录并选择你的 `zmk-for-charybdis` 仓库。
*   **优势**：在直观的图形界面拖拽修改键位，点击 `Save` 后自动向 GitHub 提交修改并触发云端编译。

---

## 🚀 刷机与更新指南 (Flashing)

1. 在 GitHub Actions 页面或 [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/) 中触发固件编译。
2. 编译成功后，在 Actions 页面下载名为 `firmware.zip` 的产物。
3. 解压获得 `left.uf2` 与 `right.uf2` 文件。
4. 双击键盘主控上的 Reset 按钮进入 Bootloader 模式（此时电脑会识别到一个优盘）。
5. 将对应的 `.uf2` 文件分别拖入左右手的优盘即可完成升级。
