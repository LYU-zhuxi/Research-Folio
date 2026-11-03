# Long-LRM: Long-sequence Large Reconstruction Model for Wide-coverage Gaussian Splats

[返回专题：三维重建](../../topics/3d-reconstruction.md#feed-forward) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2024 |
| 研究方向 | 前馈重建与重建大模型 |
| 原文 | [arXiv](https://arxiv.org/abs/2410.12781) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | arXiv:2410.12781v2（2025-08-01） |

> **一句话读懂：** 用 Mamba 与 Transformer 混合处理长序列，再压缩 token 和高斯，让前馈重建从少量局部视图扩展到更广的场景覆盖。

## 研究问题

随着图像数和分辨率增长，普通 Transformer 的计算及逐像素高斯数量迅速膨胀，如何高效整合长序列？

## 核心设计与贡献

- **兼顾长序列与跨视图交互。** 混合 Mamba2 和 Transformer，以较低成本传播长程信息，同时保留注意力建立视图联系的能力。
- **逐步控制表示规模。** token 合并降低后续序列长度，高斯裁剪减少冗余；输出也可再做少量场景优化，提升细节。

## 关键结果

在 DL3DV 与 Tanks & Temples 的实验中，可对 32 张 960×540 图像在 A100 上约 1 秒预测场景，质量接近所比较的逐场景优化方法。继续优化可提高 PSNR，但部分优化方法的 LPIPS 仍更好。

## 不足与适用边界

- 【作者指出】固定视场角训练限制了跨相机泛化；增加到更长输入序列的收益也会递减。
- 【实验边界】纯前馈与附加优化是不同配置，后者的质量不能配上前者的耗时。宽覆盖结果也不能直接外推为无限长视频重建。

## 阅读重点与下一步

重点看序列压缩发生在哪里，以及压缩会丢失哪些细节。比较方法时对齐输入视图数、总耗时和 PSNR／LPIPS。

**原文定位：** PDF 第 3–5 页方法；第 6–8 页实验；第 14 页扩展实验和泛化讨论。 [查看原文](https://arxiv.org/abs/2410.12781)

**关联阅读：** [LRM: Large Reconstruction Model for Single Image to 3D](2023-lrm.md) · [TokenGS: Decoupling 3D Gaussian Prediction from Pixels with Learnable Tokens](2026-tokengs.md)
