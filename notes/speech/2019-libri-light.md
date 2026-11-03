# Libri-Light: A Benchmark for ASR with Limited or No Supervision

[返回专题：语音](../../topics/speech.md#datasets-metrics) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2019 |
| 研究方向 | 数据集、基准与质量评价 |
| 原文 | [arXiv](https://arxiv.org/abs/1912.07875) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | ICASSP 2020 论文（索引按 arXiv 首次提交年 2019 排列） |

> **一句话读懂：** 贡献主要是一套可比较的低标注语音研究基础设施：约 6 万小时未标注英语音频，加上明确的标注预算与评测协议。

## 研究问题

怎样公平比较“少量标注＋大量未标注语音”的方法，而不让数据量和额外文本资源掩盖算法差别？

## 核心设计与贡献

- 从 LibriVox 英语有声书构建大规模未标注语音，提供语音活动区间、说话人等元信息及不同规模子集，排除与 LibriSpeech 开发、测试集重合的说话人。
- 规定 10 分钟、1 小时、10 小时标注预算，区分无监督、半监督和使用额外未对齐文本的远监督设置，分别使用 ABX、音素或字符错误率、词错误率评估。

## 关键结果

论文用对比预测编码及伪标签等基线展示：未标注预训练通常有帮助，但伪标签只有在生成模型和微调模型已有一定质量时才带来收益。它建立比较坐标与可复用资源，并非提出一个包办所有设置的识别模型。

## 不足与适用边界

- 【数据边界】英语有声书以朗读语音为主，不能代表多语言、自然对话、多人重叠或构音障碍语音。
- 【分析判断】少标注不等于少资源：预训练音频、算力与外部文本仍可非常大；比较方法需同时报告这些预算。

## 阅读重点与下一步

使用 Libri-Light 预训练时先读数据划分与协议；优先核对标注、未标注及外部文本是否在同一资源口径下。

**原文定位：** §3（数据与协议），§4–5（基线与结果）；PDF 第 2–4 页。 [查看原文](https://arxiv.org/abs/1912.07875)

**关联阅读：** [Learning Audio-Visual Speech Representation by Masked Multimodal Cluster Prediction](2022-av-hubert.md) · [NaturalSpeech 3: Zero-Shot Speech Synthesis with Factorized Codec and Diffusion Models](2024-naturalspeech-3.md)
