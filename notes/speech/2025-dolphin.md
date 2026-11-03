# Efficient Audio-Visual Speech Separation with Discrete Lip Semantics and Multi-Scale Global-Local Attention

[返回专题：语音](../../topics/speech.md#av-separation) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2025 |
| 研究方向 | 视听语音分离与目标说话人提取 |
| 原文 | [arXiv](https://arxiv.org/abs/2509.23610) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | ICLR 2026 会议版（索引按 arXiv 首次提交年 2025 排列） |

> **一句话读懂：** 同时压缩视觉前端和音频分离器：把唇动变成紧凑语义 token，再用单轮全局与局部建模减少推理开销。

## 研究问题

视听分离能否在提升质量的同时，降低大视觉骨干和反复迭代造成的成本？

## 核心设计与贡献

- DP-LipCoder 使用双路径视觉编码、向量量化及 AV-HuBERT 蒸馏，保留结构信息并学习与音频对齐的离散唇语语义，替代昂贵的视觉前端。
- 轻量编码器—解码器分离器以 GLA 模块结合全局上下文和局部结构，单轮完成多尺度处理；贡献是将表征压缩与分离架构一起优化，并统计视觉前端成本。

## 关键结果

作者在 LRS2、LRS3、VoxCeleb2 上报告优于比较方法的分离指标，并相对 IIANet 报告参数减少超过 50%、GPU 推理提速超过 6 倍。效率数值对应论文的硬件、输入长度及是否计入视觉前端的口径，并非任意设备的通用加速比。

## 不足与适用边界

- 【作者指出】仍依赖较干净、同步的唇部视频；大姿态变化、遮挡、极端光照和极低资源设备尚有挑战。
- 【作者指出】离散化可能丢失细粒度发音线索。【分析判断】更小模型不等于已经验证了持续流式处理与完整的终端延迟。

## 阅读重点与下一步

关注效率时优先读；分别比较替换视觉编码器与替换分离器的消融，检查离散表示的质量损失是否值得计算收益。

**原文定位：** §3（DP-LipCoder / GLA），§4–5（设置与结果），§6 的 Limitations；PDF 第 2–10 页。 [查看原文](https://arxiv.org/abs/2509.23610)

**关联阅读：** [IIANet: An Intra- and Inter-Modality Attention Network for Audio-Visual Speech Separation](2024-iianet.md) · [Learning Audio-Visual Speech Representation by Masked Multimodal Cluster Prediction](2022-av-hubert.md)
