# 🌌 ZMK-Config for Charybdis 

![ZMK Build](https://img.shields.io/github/actions/workflow/status/HeeTuic/zmk-for-charybdis/build.yml?label=ZMK%20Build&style=for-the-badge&color=2ac3de)
![Keymap Draw](https://img.shields.io/github/actions/workflow/status/HeeTuic/zmk-for-charybdis/draw-keymaps.yml?label=Keymap%20Draw&style=for-the-badge&color=bb9af7)

该库为"MiaoMiao"定制的无线 Charybdis人体工程学键盘提供ZMK固件，同时确保兼容官方焊接版本。

---

## 🗺️ 键位布局


![Charybdis Keymap](keymap-drawer/charybdis.svg)

*每次提交 `.keymap` 文件，本图均由 GitHub Actions 自动生成并更新。*

---

## 🛠️ 图形化改键

### 1. ZMK Studio (实时动态配置)
通过 ZMK 官方协议直接对键盘进行免刷机实时改键，更改即刻生效。
*   **如何使用**：使用受支持的 Chromium 内核浏览器（如 Chrome / Edge），打开并连接 [ZMK Studio](https://zmk.studio/)，亦可使用其桌面客户端。
*   **核心优势**：**即时通讯**。通过 Web Serial (USB) 或 Web Bluetooth 直接与硬件交互，无需等待 GitHub Actions 编译及手动烧录，最适合日常快速微调基础键位。

### 2. Keymap Editor (云端全域编译)
社区最成熟的可视化网页编辑器，深度集成 GitHub 工作流，适合对键盘布局进行全方位的架构大修。
*   **如何使用**：Fork 本仓库后，在 GitHub Actions 页面进行首次固件编译。随后访问 [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/)，授权登录并选择你的 `zmk-for-charybdis` 仓库。
*   **核心优势**：**全能编辑**。在直观的图形界面中拖拽修改键位，完美支持 Combos（组合键）、Macros（宏）以及各类复杂行为（Behaviors）的深度编辑。保存后自动向 GitHub 提交代码并触发云端编译。

---

## 🚀 固件烧录指南 (Flashing Guide)

请通过以下标准化流程获取并更新你的键盘固件：

1. **固件编译**：在网页端修改配置后，GitHub Actions 会自动触发编译。请前往当前仓库的 **Actions** 页面获取最新的构建产物。
2. **下载固件**：编译完成后，在构建任务的 artifacts 列表中下载 `firmware.zip` 压缩包。
3. **解压文件**：解压该压缩包，获得对应左手和右手的 `left.uf2` 与 `right.uf2` 固件文件。
4. **触发模式**：使用 USB 数据线将键盘连接至电脑，连续按下两次复位按键（Reset），使主控进入 Bootloader 模式（此时电脑会识别出名为 `NICENANO` 的 U 盘）。
5. **拖入升级**：将对应的 `.uf2` 文件分别拖入左右手主控对应的虚拟 U 盘中，设备会自动重启并完成固件烧录。

> **⚠️ 注意：** 
> * 左右手固件需要分别独立烧录。
> * 如果你使用的是 **ZMK Studio** 进行的实时键位微调，则无需执行上述任何烧录步骤。
