# Leaflet Geoman 高级剪切与选择性导出工具

这是一个基于 Leaflet.js、Leaflet-Geoman 和 Turf.js 构建的交互式 WebGIS 工具。它在 Leaflet-Geoman 提供的标准绘图和编辑功能之上，增强了“剪切 (Cut)”和“导出”两大核心功能。

---

## ✨ 核心功能

- **交互式地图**: 基于 Leaflet 构建，界面流畅。
- **全功能绘图与编辑**: 集成 Leaflet-Geoman，支持点、线、多边形的绘制、移动、缩放和顶点编辑。
- **GeoJSON 导入**: 轻松从本地加载 GeoJSON 文件到地图上，并使其立即可编辑。
- **高级剪切 (Advanced Cut)**:
    - 使用剪切工具后，原始图层会被智能地分割为 **“剩余部分”** 和 **“剪除部分”**。
    - 这两个部分会成为两个**独立、可编辑、可命名**的新图层，并保留在地图上。
- **选择性导出 (Selective Export)**:
    - 点击导出时，会弹出一个包含地图上所有图层的列表。
    - 用户可以**自由勾选一个或多个图层**。
    - 将选中的图层合并导出一个干净的 GeoJSON 文件。

## 🚀 如何使用

本项目是一个纯前端应用，无需复杂的环境配置。

1.  **下载**: 克隆本仓库或直接下载 `index.html` 文件。
2.  **运行**: 在您的现代网页浏览器中直接打开 `index.html` 文件。
3.  **开始使用**:
    * 使用左上角的 Geoman 工具栏在地图上绘制图形。
    * 使用右上角的控制面板导入或导出数据。

## 🛠️ 功能详解

### 高级剪切

这是对 Geoman 默认剪切功能的改进。

1.  **绘制一个基础图形**: 例如，在地图上绘制一个大的矩形。
2.  **激活剪切工具**: 点击 Geoman 工具栏上的“剪切图层”按钮。
3.  **执行剪切**: 在基础图形上绘制一个剪切路径。
4.  **查看结果**: 操作完成后，您会发现原有的矩形消失了，取而代之的是两个新的图层：
    * 一个是被剪切后**剩余的部分**。
    * 另一个是**被剪除的部分**。
    * 这两个新图层都有自己随机生成的名称（以 Tooltip 形式显示），并且可以被独立地编辑、移动或删除。

这个功能的核心是利用了 `pm:cut` 事件和 [Turf.js](https://turfjs.org/) 的 `turf.difference()` 方法来实现的。

### 选择性导出

解决了传统工具只能“导出剩余部分”的痛点。

1.  **点击导出**: 当您完成编辑后，点击右上角的“导出 GeoJSON”按钮。
2.  **选择图层**: 屏幕上会弹出一个模态窗口，其中列出了当前地图上所有可编辑图层的名称。
3.  **勾选**: 勾选您想要包含在导出文件中的一个或多个图层。
4.  **确认下载**: 点击“确认导出”，浏览器将自动下载一个名为 `export_xxxxxxxx.geojson` 的文件。该文件是一个标准的 `FeatureCollection`，仅包含您所选择的图层。

## 🧩 依赖库

本项目依赖以下优秀的开源库，通过 CDN 引入：

-   [Leaflet.js](https://leafletjs.com/) - 业界领先的交互式地图 JavaScript 库。
-   [Leaflet-Geoman](https://geoman.io/) - Leaflet 最强大的绘图与编辑插件。
-   [Turf.js](https://turfjs.org/) - 用于高级地理空间分析的 JavaScript 库。
-   [Tailwind CSS](https://tailwindcss.com/) - 用于快速构建 UI 界面。

## 🤖 关于本项目 (About This Project)

这是一个 **"Vibe Coding"** 项目，其核心功能和代码是通过与 Google 的 **Gemini** 模型和Kimi-K2进行多轮对话、迭代和协作完成的。您可以根据文件名称选择对应模型生成的代码。

## 📄 许可证 (License)

本项目采用 **MIT 许可证**。

<details>
<summary>点击查看 MIT 许可证全文</summary>


MIT License

Copyright (c) 2025 [Aryous]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

</details>