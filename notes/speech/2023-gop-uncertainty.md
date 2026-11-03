# Speech Intelligibility Assessment of Dysarthric Speech by using Goodness of Pronunciation with Uncertainty Quantification

[返回专题：语音](../../topics/speech.md#dysarthria) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2023 |
| 研究方向 | 构音障碍与语音可懂度评估 |
| 原文 | [arXiv](https://arxiv.org/abs/2305.18392) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | Interspeech 2023 会议版 |

> **一句话读懂：** 构音障碍语音偏离健康语音分布，识别器的高置信度可能不可信；改进发音评分的置信表达，比直接使用 softmax 概率更有效。

## 研究问题

如何减少神经声学模型过度自信对 GoP（发音良好度）评分的影响，让分数更贴近人工可懂度评价？

## 核心设计与贡献

- 在同一声学模型输出上比较熵、margin、最大 logit 等评分，并引入缩放与先验归一化，检验不同置信表达对异常发音评价的影响。
- 先验归一化的 MaxLogit 表现较好；进一步按音素分析相关性，为定位具体发音困难提供比整句单一评分更细的信息。创新重点是评分校正，而非新建一个诊断模型。

## 关键结果

在英语、韩语、泰米尔语数据上，作者报告最佳评分与可懂度严重程度的 Kendall 秩相关系数分别为 −0.2165、−0.5442、−0.5788。看绝对值衡量相关强弱；负号对应发音分数与严重程度方向相反，不是模型表现为负。

## 不足与适用边界

- 【实验边界】评价需要规范音素及对齐；部分对齐经人工修正，现实中自动对齐的错误可能影响评分。三套数据的任务与人工量表也不同。
- 【分析判断】英语上的相关性仍弱；相关性改善不是识别准确率提升，也不能据此认定具备患者诊断或治疗有效性。

## 阅读重点与下一步

适合研究可解释发音评价；优先看归一化与原始 logit 的对照。下一步先排查音素对齐误差是否主导相关性。

**原文定位：** §2（不确定性与评分），§3（数据、模型和对齐），§4（Kendall 相关性）；PDF 第 2–4 页。 [查看原文](https://arxiv.org/abs/2305.18392)

**关联阅读：** [Multilingual Dysarthric Speech Assessment Using Universal Phone Recognition and Language-Specific Phonemic Contrast Modeling](2026-multilingual-dysarthric-assessment.md)
