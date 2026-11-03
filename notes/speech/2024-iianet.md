# IIANet: An Intra- and Inter-Modality Attention Network for Audio-Visual Speech Separation

[返回专题：语音](../../topics/speech.md#av-separation) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2024 |
| 研究方向 | 视听语音分离与目标说话人提取 |
| 原文 | [原文](https://proceedings.mlr.press/v235/li24cf.html) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | ICML 2024 / PMLR 235 |

> **一句话读懂：** 融合前先在各模态内部提炼信息，再让音频和唇动在多个时间尺度上相互选择，比只做一次简单拼接更有效。

## 研究问题

视听特征的时间尺度不同，如何既保留各自的信息，又筛出真正有助于分离的跨模态线索？

## 核心设计与贡献

- IntraA（模态内注意力）处理单个模态的上下文；InterA（模态间注意力）选择另一模态中的相关信息，将两类操作分工。
- 在层次结构的顶层、中层和底层布置跨模态交互，兼顾不同时间尺度；通过减少迭代轮数得到 IIANet-fast，提供质量与计算开销的折中。

## 关键结果

作者在 LRS2、LRS3 和 VoxCeleb2 的混音基准上报告优于 CTCNet 的分离质量。正文效率比较中，标准 IIANet 的乘加运算量约为 CTCNet 的 11%，IIANet-fast 约为 7%；标准版 GPU 推理却更慢，说明低运算量不自动转化为低延迟。

## 不足与适用边界

- 【实验边界】主实验使用同步唇部视频与短语音混合；论文虽补充三、四人实验和真实视频示例，仍不足以覆盖长期遮挡、错位及连续真实对话。
- 【分析判断】多尺度、循环交互可能增加调度开销，评价部署价值需包含视觉编码器和端到端耗时，不能只比较分离网络的运算量。

## 阅读重点与下一步

适合重点读融合模块消融；先在相同视觉前端下比较 IntraA、InterA 的独立收益，再看 fast 配置的延迟。

**原文定位：** §3（IntraA / InterA），§4.3–4.5（质量、效率与消融）；PDF 第 2–9 页。 [查看原文](https://proceedings.mlr.press/v235/li24cf.html)

**关联阅读：** [Time Domain Audio Visual Speech Separation](2019-av-convtasnet.md) · [Efficient Audio-Visual Speech Separation with Discrete Lip Semantics and Multi-Scale Global-Local Attention](2025-dolphin.md)
