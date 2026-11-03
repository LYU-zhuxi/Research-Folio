# GenSE: Generative Speech Enhancement via Language Models using Hierarchical Modeling

[返回专题：语音](../../topics/speech.md#generative-enhancement) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2025 |
| 研究方向 | 生成式语音增强 |
| 原文 | [arXiv](https://arxiv.org/abs/2502.02942) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | ICLR 2025 会议版 |

> **一句话读懂：** 先从噪声语音预测干净的语义 token，再据此生成声学 token；用输入中的音色线索约束生成，避免只顾去噪而换了声音。

## 研究问题

能否把语音增强改写为语言模型的条件生成任务，同时恢复内容并保留说话人特征？

## 核心设计与贡献

- N2S 把噪声语音映射为干净语义 token，S2S 再预测干净声学 token，分开处理内容恢复与声音重建，降低一次生成所有信息的难度。
- SimCodec 用单量化器及码本重组减少待预测 token；token chain prompt 组合噪声语义、预测的干净语义和噪声声学 token，为生成保留音色依据。

## 关键结果

作者在 DNS 测试集报告较好的质量与说话人相似度；在域外 CHiME-4 上，转写词错误率由噪声输入的 37.9% 降到 28.4%。该结果支持内容与听感的联合改善，但不表示每个质量指标或每个样本都优于所有基线。

## 不足与适用边界

- 【作者指出】自回归 token 生成仍是速度瓶颈，论文讨论的流式预测改进属于后续方向，不能当作已经实现的实时系统。
- 【分析判断】前级语义预测错误可能传到后级；更自然的重建不保证逐字保真，编解码的量化也带来失真。需区分感知质量、内容准确性与波形相似度。

## 阅读重点与下一步

重点看两阶段分工与 token chain 消融；若用于语音增强，优先联合检查词错误率、音色和延迟，避免只优化质量预测分数。

**原文定位：** §3（SimCodec 与分层生成），§4.2（DNS / CHiME-4），附录 Inference efficiency；PDF 第 4–8、21 页。 [查看原文](https://arxiv.org/abs/2502.02942)

**关联阅读：** [CogCM: Cognition-Inspired Contextual Modeling for Audio-Visual Speech Enhancement](2025-cogcm.md) · [DNSMOS: A Non-Intrusive Perceptual Objective Speech Quality Metric to Evaluate Noise Suppressors](2020-dnsmos.md)
