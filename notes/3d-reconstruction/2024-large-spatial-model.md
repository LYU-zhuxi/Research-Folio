# Large Spatial Model: End-to-end Unposed Images to Semantic 3D

[返回专题：三维重建](../../topics/3d-reconstruction.md#semantic-reconstruction) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2024 |
| 研究方向 | 语义与实例感知的前馈重建 |
| 原文 | [arXiv](https://arxiv.org/abs/2410.18956) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | NeurIPS 2024 原文 PDF |

> **一句话读懂：** 从两张无位姿图像直接生成带语义的三维高斯，让一次重建同时支持新视角显示和语言驱动的场景查询。

## 研究问题

现有流程常把相机恢复、场景优化和语义特征提升分开执行，能否联合完成几何、外观与语义预测？

## 核心设计与贡献

- **先建立共同几何。** 利用跨视图点图恢复全局结构，再通过局部点邻域聚合和多尺度融合，细化高斯的外观及语义。
- **把二维语义提升到三维。** 融合预训练二维模型特征，并用可渲染的语义高斯统一表示，使语言查询可映射到不同视图。

## 关键结果

论文在新视角合成和语义分割中验证联合预测；跨模态、多尺度融合消融显示，两类能力可以同时改善。部分语义消融采用 LSeg 预测作为参考，需要与人工真值评测区分。

## 不足与适用边界

- 【实验边界】核心设定为两张输入图，尚不能凭该实验确认任意长序列的全局一致性。
- 【分析判断】依赖几何训练监督和二维语义先验；遮挡、小目标及教师模型的语义混淆可能被带入三维表示。

## 阅读重点与下一步

看清“全局几何—局部融合—语义高斯”的信息链。复现时区分真实标签指标、教师一致性指标和新视角渲染指标。

**原文定位：** PDF 第 3–5 页结构与监督；第 6–8 页重建、语义和消融实验。 [查看原文](https://arxiv.org/abs/2410.18956)

**关联阅读：** [Uni3R: Unified 3D Reconstruction and Semantic Understanding via Generalizable Gaussian Splatting from Unposed Multi-View Images](2025-uni3r.md) · [SIU3R: Simultaneous Scene Understanding and 3D Reconstruction Beyond Feature Alignment](2025-siu3r.md)
