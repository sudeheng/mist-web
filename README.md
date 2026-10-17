# MIST 雾镜

一面会呼吸的雾镜。用鼠标、触屏或隔空手势擦开雾气，留下片刻清晰。

A small interactive fog mirror built with Canvas and vanilla JavaScript, with optional in-browser hand tracking.

**[在线体验 / Live demo](https://sudeheng.github.io/mist-web/)** · [MIT 许可证](LICENSE)

![MIST 雾镜网页预览](docs/preview.png)

## 功能

- **自由擦雾**：鼠标移动、触屏拖动或键盘操作，无需摄像头。
- **隔空体感**：通过 MediaPipe 识别双手，食指细写、张掌擦雾、握拳停笔。
- **镜面氛围**：苔光、琥珀、月白三种色调，可调节雾气浓度和回归速度。
- **留住此刻**：保存镜面 PNG，支持全屏体验和可选环境音。
- **轻量实现**：单个 HTML 文件，无构建流程、无后端；基础体验可离线使用。

## 本地运行

下载项目后，可以直接打开 `index.html` 体验基础功能。使用摄像头时建议通过本地服务器打开：

```bash
git clone https://github.com/sudeheng/mist-web.git
cd mist-web
python3 -m http.server 8080
```

访问 [http://localhost:8080/](http://localhost:8080/)。需要安装 Python 3；也可以使用其他静态文件服务器。停止服务时在终端按 `Ctrl+C`。

## 操作方式

| 模式 | 操作 | 效果 |
| --- | --- | --- |
| 鼠标 | 在镜面上移动 | 擦开雾气 |
| 鼠标 | 按住鼠标移动 | 细写 |
| 触屏 | 拖动手指 | 擦雾 |
| 键盘 | 聚焦镜面后按方向键 | 移动并擦雾 |
| 键盘 | 方向键 + Shift | 加宽擦拭 |
| 键盘 | 聚焦镜面后按 R | 重新起雾 |
| 体感 | 伸出食指 | 在雾中细写 |
| 体感 | 张开手掌 | 大面积擦雾 |
| 体感 | 握拳 | 停笔 |

点击「开启体感镜像」，允许摄像头访问并等待模型加载。站在距镜头约一臂的位置，将手放在画面中；点击「关闭体感镜像」可结束摄像头使用。

## 浏览器与网络

建议使用较新的 Chrome 或 Edge。摄像头模式需要 HTTPS 或 `localhost`；GitHub Pages 在线演示使用 HTTPS。

首次启用体感模式需要联网加载以下资源，速度取决于所在网络：

- `cdn.jsdelivr.net`：MediaPipe JavaScript 与 WebAssembly 运行时。
- `storage.googleapis.com`：手部关键点识别模型。

如果摄像头被占用、权限被拒绝或模型加载失败，页面会显示提示，仍可使用鼠标、触屏和键盘。移动设备上的摄像头、全屏与性能表现取决于浏览器和设备；目前未做完整兼容性认证。

## 隐私

- 摄像头仅在点击开启按钮并获得权限后启用，不请求麦克风权限。
- 本项目在浏览器内处理摄像头帧，没有上传影像的业务接口，也不录制视频。
- 关闭体感镜像或离开页面时会停止摄像头轨道。
- 加载第三方组件和模型会向上述资源服务发起网络请求；「浏览器内识别」不等于完全没有网络访问。
- 只有点击保存按钮才会下载镜面 PNG；体感模式下图片可能包含摄像头画面，请自行决定是否分享。
- 环境音由 Web Audio API 本地生成，默认关闭。

## 项目结构

```text
mist-web/
├── index.html          # 页面、样式、Canvas 渲染与交互
├── README.md           # 项目说明
├── LICENSE             # MIT 许可证
├── .gitignore          # 本地文件排除规则
├── .nojekyll           # 直接发布静态文件
└── docs/
    ├── THIRD_PARTY.md  # 第三方组件和模型来源
    └── preview.png     # 网页预览截图
```

## 部署到 GitHub Pages

本项目无需安装 npm 依赖或运行构建命令。

1. 将项目文件提交到仓库的 `main` 分支。
2. 打开仓库 **Settings → Pages**。
3. 在 **Build and deployment** 中选择 **Deploy from a branch**。
4. 选择 **main** 分支和 **/(root)** 目录，点击 **Save**。
5. 等待部署完成，访问 Pages 设置页显示的地址。

后续更新 `main` 分支后，GitHub Pages 会自动发布。官方说明：[配置发布来源](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)。

## 参与改进

欢迎通过 [Issues](https://github.com/sudeheng/mist-web/issues) 报告问题或提出想法，也欢迎提交 Pull Request。报告兼容性问题时，请附浏览器版本、设备类型、复现步骤，以及是否启用了体感模式。

## 许可与致谢

本项目原创代码以 [MIT License](LICENSE) 发布，Copyright © 2026 [sudeheng](https://github.com/sudeheng)。第三方组件和模型保留其各自的许可与使用条款，详见 [第三方资源说明](docs/THIRD_PARTY.md)。
