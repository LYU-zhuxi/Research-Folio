# GroupForward: Building Referable 3D Scenes via Instance-Grouped Feed-Forward Gaussian Splatting

[返回专题：三维重建](../../topics/3d-reconstruction.md#semantic-reconstruction) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2026 |
| 研究方向 | 语义与实例感知的前馈重建 |
| 原文 | [arXiv](https://arxiv.org/abs/2608.17535) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | arXiv:2608.17535v1（2026-08-18） |

> **一句话读懂：** 把前馈高斯组织成稳定实例，再结合场景图与多视图视觉语言推理，让“桌子左边的椅子”这类表达能指向三维对象。

## 研究问题

类别相似度查询无法充分处理空间关系和上下文约束；如何把渲染表示连接到对象级指代推理？

## 核心设计与贡献

- **构建可引用的实例组。** 联合预测相机、高斯和紧凑实例嵌入，再聚类并聚合对象语义；坐标规范对齐的自渲染约束改善场景与预测相机的一致性。
- **从检索走向关系推理。** RSRF 用实例组构建三维场景图，先筛选候选，再结合图证据及多视图图像调用视觉语言模型，结果映射回实例掩码。

## 关键结果

ScanNet 两视图实验中，语义分割与新视角合成优于表中比较方法；另有指代表达评测，展示类别检索之外的关系理解能力。重建和完整语言推理应分别计时。

## 不足与适用边界

- 【实验边界】复杂指代需要额外的场景图处理与视觉语言模型，不能把整条查询链的效率等同于前馈重建速度。
- 【分析判断】错误分组会使候选对象缺失或合并，后续推理难以补救；复杂遮挡、关系歧义和语言模型误判仍可能导致定位错误。

## 阅读重点与下一步

把错误拆成“对象有没有建对、候选有没有选对、关系有没有推对”。分别测三维建图与每次查询的端到端延迟。

**原文定位：** PDF 第 3–6 页实例分组、自渲染和 RSRF；第 7–8 页重建及指代评测。 [查看原文](https://arxiv.org/abs/2608.17535)

**关联阅读：** [Scenes as Objects, Not Primitives: Instance-Structured 3D Tokenization from Unposed Views](2026-instok3d.md) · [Do 3D Large Language Models Really Understand 3D Spatial Relationships?](2026-real-3dqa.md)
