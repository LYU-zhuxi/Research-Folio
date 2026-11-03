# CSGaussian: Progressive Rate-Distortion Compression and Segmentation for 3D Gaussian Splatting

[返回专题：三维重建](../../topics/3d-reconstruction.md#gaussian-segmentation) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2026 |
| 研究方向 | 高斯语义表示与对象分割 |
| 原文 | [arXiv](https://arxiv.org/abs/2601.12814) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | arXiv:2601.12814v1（2026-01-19） |

> **一句话读懂：** 将高斯压缩与分割一起优化，让接收端拿到的紧凑场景既能渲染，也保留可用的语义结构。

## 研究问题

只压缩颜色和几何可能损伤语义，事后再学语义又增加开销；能否联合控制文件大小、画质与分割质量？

## 核心设计与贡献

- **把语义纳入码率—失真优化。** 用轻量隐式网络超先验对颜色与语义属性建模并进行熵编码，目标不只是减少参数数目，而是压缩实际传输表示。
- **针对压缩误差学习语义。** 量化感知训练维护特征可分性，并通过质量感知权重抑制低质量高斯的干扰，让分割适应解码后表示。

## 关键结果

论文用压缩率、渲染质量和语义分割联合评估，并通过量化感知与质量权重消融展示分割收益。其贡献是三项目标的协同权衡，不能只用某一个压缩倍数评价整体效果。

## 不足与适用边界

- 【实验边界】语义训练利用发送端原始图像产生的掩码；不能假定接收端只靠有损渲染图就能恢复相同监督质量。
- 【分析判断】量化强度、质量阈值和场景结构共同决定边界损失，小物体尤其值得检查；逐场景压缩训练成本也应计入部署。

## 阅读重点与下一步

画出文件大小—画质—mIoU 的对应关系，并计入超先验等辅助信息。对比相同码率下的质量，比只比高斯数量更有意义。

**原文定位：** PDF 第 3–5 页压缩及语义学习；第 6–8 页码率实验、发送端监督与消融。 [查看原文](https://arxiv.org/abs/2601.12814)

**关联阅读：** [InstanceGaussian: Appearance-Semantic Joint Gaussian Representation for 3D Instance-Level Perception](2024-instancegaussian.md) · [FLEG: Feed-Forward Language Embedded Gaussian Splatting from Any Views via Compact Semantic Representation](2025-fleg.md)
