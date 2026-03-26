# ⚖️ 社交天平 (Social Balance)

> 由 **Torque-Logic** 构筑的本地化社交数据量化仪表盘。
> 用工程逻辑拆解社交内耗，让关系在数据下无所遁形。

![Privacy Shield](https://img.shields.io/badge/Privacy-100%25_Local-success)
![Tech Stack](https://img.shields.io/badge/Tech-React_%7C_Tailwind-blue)
![License](https://img.shields.io/badge/License-MIT-gray)

## 📌 核心理念 (Philosophy)

在现代社交中，“谁更主动”往往是一个模糊且容易引发内耗的感性问题。**社交天平** 旨在通过严谨的时间序列分析，将这种感性体验转化为可视化的客观数据。

本项目秉持 **100% 纯本地运行** 原则。所有数据解析、时序比对和 DOM 渲染均在浏览器内存中完成。没有后端，没有数据库，你的聊天记录永远不会离开你的设备。

## ⚙️ 核心机制：动态扭矩判定 (Dynamic Threshold Logic)

单纯统计“发言总数”毫无意义，因为一段对话可能有几百条附和的消息。本工具的核心算法基于**“时间间隙 (Time Gap) 判定”**：

$$T_{current} - T_{previous} > Threshold$$

* **默认阈值 (3 小时)**：完美契合现代人“早、中、晚”的生活节律。当对话中断超过 3 小时，下一次发言将被系统严谨地判定为“重新发起话题”。
* **动态滑块 (2h - 8h)**：系统提供无极调节滑块。用户可根据具体关系的紧密程度（高频互动 vs 异地长线），实时动态调节判定阈值，天平刻度会做出毫秒级重绘。

## 🚀 快速上手 (Usage)

本工具作为下游数据分析面板，需要依赖上游工具导出微信原始数据。

**Step 1：获取数据源**
建议使用开源项目 [CipherTalk](https://github.com/hangxian/CipherTalk) （或同类工具）导出微信本地加密数据库，并转换为标准 `JSON` 格式。

**Step 2：载入仪表盘**
1. 访问部署好的网页端（或直接在本地双击打开 `index.html`）。
2. 将导出的 `.json` 文件拖入解析框。

**Step 3：分析与复盘**
* 观察左侧（我方）与右侧（对方）的绝对发起次数。
* 拖动阈值滑块，观察在不同时间颗粒度下的天平倾斜率。
* 点击单侧面板，向下查阅每一次“破冰话题”的具体时间戳和首条发言内容。

## 🛠️ 技术栈 (Tech Stack)

* **Core**: React 18 (CDN 引入，无需编译环境)
* **Styling**: Tailwind CSS (Utility-first，保证 UI 工业级质感)
* **Icons**: 手写 SVG (零外部依赖，极速加载)
* **Defensive Design**: 内置时间戳强制重排、JSON 结构校验及零值异常处理。

## 📄 许可协议 (License)

MIT License. 自由分发，保持清醒。

---
*Developed by Torque-Logic. Keep it objective.*
