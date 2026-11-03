# InstanceGaussian: Appearance-Semantic Joint Gaussian Representation for 3D Instance-Level Perception

[返回专题：三维重建](../../topics/3d-reconstruction.md#gaussian-segmentation) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2024 |
| 研究方向 | 高斯语义表示与对象分割 |
| 原文 | [arXiv](https://arxiv.org/abs/2411.19235) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | CVPR 2025 原文 PDF |

> **一句话读懂：** 让高斯的外观与语义在同一锚点结构中协调学习，再自底向上聚合实例，减少对象被切碎或混在一起的问题。

## 研究问题

二维掩码提升到三维时，外观边界、语义边界与高斯覆盖范围并不一致，怎样获得稳定的三维对象归属？

## 核心设计与贡献

- **协调外观与语义的粒度。** Semantic-Scaffold-GS 让同一锚点支持不同外观而共享语义，并采用渐进联合训练，降低两类属性相互冲突。
- **从局部到实例。** 基于语义与空间关系进行自底向上聚合，结合采样和连通结构形成类无关实例，避免完全依赖预设聚类数。

## 关键结果

ScanNet 的语义、实例及文本查询实验支持联合表示和渐进训练的作用。不同任务的领先方法并不相同：论文也报告深度辅助的 MaskClustering 在类无关实例分割中更强。

## 不足与适用边界

- 【作者指出】依赖较高质量的二维掩码；MLP 外观建模带来额外训练和渲染成本。
- 【分析判断】几何缺失或同物体内部语义不连续仍可能使聚合出错；逐场景学习的效率不能与泛化前馈重建直接混为一谈。

## 阅读重点与下一步

先看共享锚点究竟解决了什么外观／语义冲突，再看聚合策略的消融。分割精度和训练、渲染开销应同时报告。

**原文定位：** PDF 第 3–5 页联合表示与聚合；第 6–8 页实验、消融及局限。 [查看原文](https://arxiv.org/abs/2411.19235)

**关联阅读：** [ChildSplat: Anchor-Child Semantic Gaussian Representation for 3D Object Segmentation](2026-childsplat.md) · [CSGaussian: Progressive Rate-Distortion Compression and Segmentation for 3D Gaussian Splatting](2026-csgaussian.md)
