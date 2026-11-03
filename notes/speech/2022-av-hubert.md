# Learning Audio-Visual Speech Representation by Masked Multimodal Cluster Prediction

[返回专题：语音](../../topics/speech.md#representation) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2022 |
| 研究方向 | 视听自监督表征学习 |
| 原文 | [arXiv](https://arxiv.org/abs/2201.02184) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | ICLR 2022 会议版 |

> **一句话读懂：** 用音视频共同产生的离散聚类标签做掩码预测，让未标注的唇动视频也能学到语音内容；模态 dropout 防止模型只听不看。

## 研究问题

缺少大量转写标签时，怎样从同步音视频中学到可用于唇读和语音识别的表征？

## 核心设计与贡献

- 先用声学特征聚类产生离散目标，再交替训练和重聚类，让目标逐步包含视听共同信息；网络预测被遮挡位置的聚类标签，而非直接重建像素或波形。
- 以整段模态 dropout 训练视觉、音频或联合输入，缓解强音频模态压制视觉；用同一视频的其他连续片段替换遮挡区域，增加视觉预测难度。

## 关键结果

作者使用约 1,759 小时未标注数据预训练，只用 30 小时标注数据微调，在 LRS3 唇读上达到 32.5% 词错误率；使用完整标注数据并结合自训练可达 26.9%。这些数值对应不同训练条件，不能把后者归因于只有 30 小时标注。

## 不足与适用边界

- 【实验观察】跨语言预训练并非总有收益：当目标语言数据充分时，加入其他语言可能因域偏移降低效果。
- 【分析判断】仍需要同步音视频与多轮聚类训练；好的识别表征不自动等于适合噪声增强或分离，作为下游前端需检验噪声与视觉缺失下的稳健性。

## 阅读重点与下一步

视听研究的基础阅读；重点看模态 dropout 为什么必要。用于下游时先比较冻结前端与适配前端，而非默认预训练特征一定稳健。

**原文定位：** §3（聚类、模态 dropout 与掩码），§4.2–4.4（唇读与跨语言）；PDF 第 4–8 页。 [查看原文](https://arxiv.org/abs/2201.02184)

**关联阅读：** [IIANet: An Intra- and Inter-Modality Attention Network for Audio-Visual Speech Separation](2024-iianet.md) · [Efficient Audio-Visual Speech Separation with Discrete Lip Semantics and Multi-Scale Global-Local Attention](2025-dolphin.md)
