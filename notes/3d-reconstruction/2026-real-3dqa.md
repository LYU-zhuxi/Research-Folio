# Do 3D Large Language Models Really Understand 3D Spatial Relationships?

[返回专题：三维重建](../../topics/3d-reconstruction.md#spatial-reasoning) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2026 |
| 研究方向 | 三维空间推理与评估 |
| 原文 | [arXiv](https://arxiv.org/abs/2603.23523) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | ICLR 2026 原文 PDF |

> **一句话读懂：** 通过遮掉三维输入、旋转观察方向和重加权训练，检验三维问答模型是否真正依赖空间信息。

## 研究问题

三维问答高分可能来自语言共现和数据偏差，怎样把“猜对常识”与“使用三维关系”区分开？

## 核心设计与贡献

- **构建更强调几何依赖的评测。** 用完整模型与盲模型的表现筛查语言捷径，并生成 90°、180°、270° 的视角变体，通过 VRS 评估旋转后的回答稳定性。
- **让训练更关注三维信息。** 3DR-FT 比较盲模型与当前模型对正确答案 token 的惊讶程度，提高仅凭文本难猜的部分的训练权重。

## 关键结果

五类三维语言模型从 SQA3D 转到 Real-3DQA 后，问答分数明显下降；要求多个旋转视角都答对时进一步退化，暴露了原始平均准确率掩盖的空间推理弱点。

## 不足与适用边界

- 【实验边界】筛选结果依赖所用盲模型和题目分布；旋转评测只覆盖指定变换，不能视为完整空间理解的充分证明。
- 【分析判断】文本答案匹配仍可能受同义表达影响。需要结合单题几何证据，才能区分语言形式错误与真实空间推理失败。

## 阅读重点与下一步

做三维语言任务时同时报告完整输入、盲输入和旋转一致性，而非只报问答平均分；训练收益也应检查是否伴随三维依赖增强。

**原文定位：** PDF 第 3–6 页偏差分析、评测与旋转指标；第 7–8 页重加权训练及结果。 [查看原文](https://arxiv.org/abs/2603.23523)

**关联阅读：** [GroupForward: Building Referable 3D Scenes via Instance-Grouped Feed-Forward Gaussian Splatting](2026-groupforward.md) · [Scenes as Objects, Not Primitives: Instance-Structured 3D Tokenization from Unposed Views](2026-instok3d.md)
