# Scenes as Objects, Not Primitives: Instance-Structured 3D Tokenization from Unposed Views

[返回专题：三维重建](../../topics/3d-reconstruction.md#semantic-reconstruction) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2026 |
| 研究方向 | 语义与实例感知的前馈重建 |
| 原文 | [arXiv](https://arxiv.org/abs/2606.29513) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | arXiv:2606.29513v1（2026-06-28） |

> **一句话读懂：** 先用实例 token 表达“这是哪个对象”，再用锚点 token 表达局部几何与外观，使高斯天然具有对象归属。

## 研究问题

高斯基元适合渲染，却缺乏对象结构；能否在前馈重建时直接生成可分组、可查询的对象级表示？

## 核心设计与贡献

- **层次 token 与竞争分组。** 几何主干提取多视图上下文，锚点 token 解码局部高斯，实例 token 通过竞争分配聚合锚点，形成对象结构。
- **将语义存储放到对象层。** 渲染和二维掩码共同监督，不依赖三维实例标注；对象共享语义加低维锚点残差，兼顾紧凑性和局部差异。

## 关键结果

论文联合评估新视角合成、开放词汇特征提升与类无关实例分割。两视图实验显示，对象级共享语义能显著减少特征存储，同时保留实用的语义与渲染质量。

## 不足与适用边界

- 【作者指出】主要研究有界室内静态场景，固定实例组预算会限制复杂度，单个对象语义 token 也难覆盖复杂对象内部差异。
- 【实验边界】部分语义消融仅在两视图下验证；不能直接认为相同收益已在更多视图、动态环境或机器人操作中成立。

## 阅读重点与下一步

重点看“对象分组是否稳定”与“语义残差是否必要”。按实例数、遮挡和对象尺度分组评测，更容易发现固定预算的瓶颈。

**原文定位：** PDF 第 3–5 页 token 分组及监督；第 6–10 页实验、消融和局限。 [查看原文](https://arxiv.org/abs/2606.29513)

**关联阅读：** [FLEG: Feed-Forward Language Embedded Gaussian Splatting from Any Views via Compact Semantic Representation](2025-fleg.md) · [GroupForward: Building Referable 3D Scenes via Instance-Grouped Feed-Forward Gaussian Splatting](2026-groupforward.md)
