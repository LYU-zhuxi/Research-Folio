# Mamba4D: Efficient 4D Point Cloud Video Understanding with Disentangled Spatial-Temporal State Space Models

[返回专题：三维重建](../../topics/3d-reconstruction.md#point-cloud) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2025 |
| 研究方向 | 点云骨干与三维、四维理解 |
| 原文 | [原文](https://openaccess.thecvf.com/content/CVPR2025/papers/Liu_Mamba4D_Efficient_4D_Point_Cloud_Video_Understanding_with_Disentangled_Spatial-Temporal_CVPR_2025_paper.pdf) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | CVPR 2025 原文 PDF |

> **一句话读懂：** 将点云视频的空间结构与时间变化解耦，用两类 Mamba 模块高效连接局部几何和长程动态。

## 研究问题

点云跨帧没有固定像素对应，长序列全注意力又昂贵；如何高效建立四维时空联系？

## 核心设计与贡献

- **先局部空间，后长期时间。** 帧内 Spatial Mamba 与时间池化编码局部几何及短期变化，再由跨帧 Temporal Mamba 建模更长时间依赖。
- **设计时空扫描顺序。** 将不规则点云 token 整理为可扫描序列，用状态空间模型传递信息，降低长序列相关性建模的成本。

## 关键结果

论文在 MSR-Action3D 动作识别、HOI4D 动作分割和 Synthia4D 语义分割中展示竞争力；相对 P4Transformer，较长序列下的识别与效率优势更明显。不同任务的增益口径不能互换。

## 不足与适用边界

- 【实验边界】线性复杂度主要描述状态空间序列处理，不能据此断言采样、邻域构建和整条系统均为线性。
- 【分析判断】扫描顺序与时空下采样会影响哪些关系被保留；快速运动、小目标及跨帧严重遮挡仍需单独验证。

## 阅读重点与下一步

重点看空间／时间解耦和扫描策略各自的消融。增加帧数时同时观察准确率、预处理耗时及峰值显存。

**原文定位：** PDF 第 3–4 页时空模块；第 5–7 页任务比较、效率与消融。 [查看原文](https://openaccess.thecvf.com/content/CVPR2025/papers/Liu_Mamba4D_Efficient_4D_Point_Cloud_Video_Understanding_with_Disentangled_Spatial-Temporal_CVPR_2025_paper.pdf)

**关联阅读：** [Point Transformer V3: Simpler, Faster, Stronger](2023-point-transformer-v3.md) · [VGGT: Visual Geometry Grounded Transformer](2025-vggt.md)
