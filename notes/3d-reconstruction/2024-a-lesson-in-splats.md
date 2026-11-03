# A Lesson in Splats: Teacher-Guided Diffusion for 3D Gaussian Splats Generation with 2D Supervision

[返回专题：三维重建](../../topics/3d-reconstruction.md#generative) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2024 |
| 研究方向 | 生成式三维重建 |
| 原文 | [arXiv](https://arxiv.org/abs/2412.00623) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | ICCV 2025 原文 PDF |

> **一句话读懂：** 利用重建教师给出的三维高斯作为扩散学习的起点，再用二维渲染监督纠偏，使生成模型有机会超过教师。

## 研究问题

缺少真实高斯资产时，如何训练三维高斯扩散，而不把教师重建误差当成必须复制的正确答案？

## 核心设计与贡献

- **以教师分布引导训练。** 给教师预测的高斯加噪，在适当噪声区间训练去噪模型，缓和教师表示与潜在真实三维分布的差异。
- **用渲染监督而非只模仿参数。** 去噪结果通过多视图图像损失训练，使学生能修正教师在未见视角的缺陷，并学习有歧义区域的生成先验。

## 关键结果

ShapeNet-SRN 和 RealEstate10K 实验显示，学生可超过相应重建教师；RE10K 中相对 Flash3D 的多种评测设置平均提高约 0.5 dB PSNR。该结果对应所用教师和数据，并非扩散必然优于所有重建方法。

## 不足与适用边界

- 【作者指出】继承像素对齐高斯的表示限制，观察外区域可能过度平滑。
- 【分析判断】教师质量、噪声区间和采样步数共同影响结果；生成的合理背面也未必是真实几何，推理成本应计入扩散采样。

## 阅读重点与下一步

先理解为何无需精确模仿教师仍能训练，再看教师类型、噪声范围和采样步数消融。对比学生与教师时保持相同输入条件。

**原文定位：** PDF 第 3–5 页教师引导扩散；第 6–8 页比较、消融和局限。 [查看原文](https://arxiv.org/abs/2412.00623)

**关联阅读：** [LRM: Large Reconstruction Model for Single Image to 3D](2023-lrm.md) · [TokenGS: Decoupling 3D Gaussian Prediction from Pixels with Learnable Tokens](2026-tokengs.md)
