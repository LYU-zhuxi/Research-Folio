# TokenGS: Decoupling 3D Gaussian Prediction from Pixels with Learnable Tokens

[返回专题：三维重建](../../topics/3d-reconstruction.md#feed-forward) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2026 |
| 研究方向 | 前馈重建与重建大模型 |
| 原文 | [arXiv](https://arxiv.org/abs/2604.15239) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | arXiv:2604.15239v1（2026-04-16） |

> **一句话读懂：** 用可学习的高斯 token 直接预测三维基元，把高斯数量和位置从输入像素网格中解放出来。

## 研究问题

逐像素预测会制造重复高斯，并把三维位置绑在相机射线上；怎样获得更紧凑、更自由的场景表示？

## 核心设计与贡献

- **token 解码三维高斯。** 一组可学习 token 汇聚图像信息，直接预测高斯位置和属性，表示容量可以独立于图像分辨率及视图数配置。
- **保留低维适配入口。** 使用渲染监督学习表示，并在测试时优化 token，利用已学先验改善单个场景，减少直接优化大量高斯参数的自由度。

## 关键结果

在 RE10K 两视图实验中，基础配置用约一半高斯达到与所比较基线相近的质量；增加 token 及后续 token 优化可继续改善结果。不同高斯预算对应不同配置，不能视为同一模型同时获得全部收益。

## 不足与适用边界

- 【作者指出】大环境与精细几何仍有困难；token 优化增加了推理后的迭代成本。
- 【分析判断】固定 token 预算会限制复杂场景容量。摆脱像素绑定提高表达自由度，也需要额外检查高斯是否覆盖小物体和遮挡边界。

## 阅读重点与下一步

重点比较同等高斯数下的质量，而非只比较默认配置。将纯前馈和 token 优化的时间、显存与细节分别记录。

**原文定位：** PDF 第 3–5 页表示与 token 优化；第 6–8 页预算实验和局限。 [查看原文](https://arxiv.org/abs/2604.15239)

**关联阅读：** [Long-LRM: Long-sequence Large Reconstruction Model for Wide-coverage Gaussian Splats](2024-long-lrm.md) · [Scenes as Objects, Not Primitives: Instance-Structured 3D Tokenization from Unposed Views](2026-instok3d.md)
