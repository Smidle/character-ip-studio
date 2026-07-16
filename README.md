# Character IP Studio

[![GitHub stars](https://img.shields.io/github/stars/Smidle/character-ip-studio?style=flat&label=Stars)](https://github.com/Smidle/character-ip-studio/stargazers)
[![Star History](https://img.shields.io/badge/Star%20history-view-ffcb47?style=flat)](https://star-history.com/#Smidle/character-ip-studio&Date)
[![Repository traffic](https://img.shields.io/badge/Repository%20traffic-view-2ea44f?style=flat)](https://github.com/Smidle/character-ip-studio/graphs/traffic)

从一张参考图出发，制作一套可复用的角色 IP 素材。它适合像素艺术、轻松卡通、现代插画和其他由用户确认的视觉方向，而不局限于任何单一角色比例或风格。

## 功能

- 先用统一的选择题确认画风、身材设定、细节、色彩、背景、记忆点与用途。
- 输出前、侧、背三视图，作为整套素材的视觉基准。
- 输出 8 张独立姿势图，可用于聊天、社媒和品牌视觉。
- 生成角色说明与逐项质量审核，用户确认后才标记为最终交付。
- 支持透明底色的贴纸制作流程。

## 使用流程

```text
创意选择 → 角色三视图 → 8 个姿势 → 质量审核 → 用户确认 → 交付
```

## 快速开始

安装技能后，上传一张人物或角色参考图，并输入：

```text
使用 $character-ip-studio，基于这张图制作一套角色 IP 素材。
```

技能会先给出 7 道选择题。你可以直接回复：

```text
1B，2C，3B，4A，5A，6A，7C
```

这代表：像素艺术、沿用参考图身材、明显方格像素、保留原配色、明亮纯色底、完整保留外观特征、用于品牌视觉资产。

## 产出文件

```text
model-sheet.png
pose-greeting.png
pose-positive.png
pose-considering.png
pose-surprise.png
pose-focus.png
pose-upset.png
pose-firm.png
pose-acknowledged.png
identity-notes.md
quality-review.md
```

所有文件会放在同一个交付目录中；除非明确要求，否则不会压缩。

## 数据面板

- [查看当前 Star 数](https://github.com/Smidle/character-ip-studio/stargazers)
- [查看 Star 历史趋势](https://star-history.com/#Smidle/character-ip-studio&Date)
- [查看仓库访问数据](https://github.com/Smidle/character-ip-studio/graphs/traffic)

GitHub 的访问面板由仓库权限控制，且原生仅展示最近 14 天的浏览与克隆数据；Star History 用于长期查看 Star 变化。

## 说明

本项目受 [DannyZZ2/q-character-generator](https://github.com/DannyZZ2/q-character-generator) 的工作流启发后进行独立二次创作。当前的交互问卷、文档结构、交付命名和提示写法均已重新设计，以服务更广泛的角色 IP 素材制作。
