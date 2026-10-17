# 第三方资源

MIST 的基础镜面、纹理、图标和环境音在页面中绘制或生成。可选体感模式会按需从外部地址加载以下组件和模型，仓库不包含这些组件或模型的二进制副本。

| 资源 | 固定版本 / 路径 | 用途 |
| --- | --- | --- |
| MediaPipe Tasks Vision | `@mediapipe/tasks-vision@0.10.21` | JavaScript 与 WebAssembly 手部识别运行时 |
| Hand Landmarker 模型 | `hand_landmarker/hand_landmarker/float16/1/hand_landmarker.task` | 手部关键点检测 |

## 来源

- MediaPipe 项目：https://github.com/google-ai-edge/mediapipe
- 项目许可证：https://github.com/google-ai-edge/mediapipe/blob/master/LICENSE
- Hand Landmarker 官方说明：https://ai.google.dev/edge/mediapipe/solutions/vision/hand_landmarker
- Web 使用说明：https://ai.google.dev/edge/mediapipe/solutions/vision/hand_landmarker/web_js
- JavaScript：https://cdn.jsdelivr.net/npm/@mediapipe/tasks-vision@0.10.21/vision_bundle.mjs
- WebAssembly 目录：https://cdn.jsdelivr.net/npm/@mediapipe/tasks-vision@0.10.21/wasm
- 模型：https://storage.googleapis.com/mediapipe-models/hand_landmarker/hand_landmarker/float16/1/hand_landmarker.task

本仓库的 MIT 许可证适用于本项目原创内容，不重新许可上述第三方资源。使用、修改或再分发第三方组件与模型时，请查看其上游许可及适用条款；将资源改为自行托管时也应保留相应许可信息。
