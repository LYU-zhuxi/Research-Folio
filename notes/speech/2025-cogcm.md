# CogCM: Cognition-Inspired Contextual Modeling for Audio-Visual Speech Enhancement

[返回专题：语音](../../topics/speech.md#av-enhancement) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2025 |
| 研究方向 | 视听语音增强 |
| 原文 | [原文](https://openaccess.thecvf.com/content/ICCV2025/papers/Wang_CogCM_Cognition-Inspired_Contextual_Modeling_for_Audio-Visual_Speech_Enhancement_ICCV_2025_paper.pdf) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | ICCV 2025 会议版 |

> **一句话读懂：** 让高层语音语义指导低层声学恢复，并让视觉线索同时影响时间与频率方向的建模，而不只沿时间轴融合。

## 研究问题

噪声遮住局部语音时，怎样用较完整的语义上下文与视觉信息恢复声学细节？

## 核心设计与贡献

- SeCM 提取语义上下文，SiCM 建模细粒度时频信号；在 GAN（生成对抗网络）框架中明确分离两种粒度的信息。
- SSGM 将低分辨率语义特征对齐到时频声学特征，借助通道交换与门控指导恢复。关键贡献是“语义指导信号”的分层路径，以及视觉对频率建模的作用。

## 关键结果

作者在七种组合数据设置、不同信噪比及消融实验中报告增强收益。移除语义上下文或频率指导会影响结果，支持两类设计的作用；这属于语音增强实验，不能单凭效果提升证明模型复现了人脑认知机制。

## 不足与适用边界

- 【实验边界】主要噪声设置由语音与噪声混合构造；多数据集表现不等于已经解决真实远场混响、视觉失效和未知录音设备带来的偏移。
- 【分析判断】高层语义可能帮助恢复，也可能在证据很弱时引入内容偏差。语音听感或质量指标变好，仍需单独核对原话和说话人是否保真。

## 阅读重点与下一步

重点读 SSGM 和语义模块变体；迁移时同时观察增强质量与转写错误，检验“恢复得更好”是否也“说得没变”。

**原文定位：** §3.1–3.4（SeCM / SiCM / SSGM），§4（对比与消融）；PDF 第 3–8 页。 [查看原文](https://openaccess.thecvf.com/content/ICCV2025/papers/Wang_CogCM_Cognition-Inspired_Contextual_Modeling_for_Audio-Visual_Speech_Enhancement_ICCV_2025_paper.pdf)

**关联阅读：** [Learning Audio-Visual Speech Representation by Masked Multimodal Cluster Prediction](2022-av-hubert.md) · [GenSE: Generative Speech Enhancement via Language Models using Hierarchical Modeling](2025-gense.md)
