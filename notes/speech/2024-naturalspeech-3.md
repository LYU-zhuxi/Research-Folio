# NaturalSpeech 3: Zero-Shot Speech Synthesis with Factorized Codec and Diffusion Models

[返回专题：语音](../../topics/speech.md#synthesis) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2024 |
| 研究方向 | 语音合成与生成 |
| 原文 | [arXiv](https://arxiv.org/abs/2403.03100) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | arXiv:2403.03100v3 |

> **一句话读懂：** 把语音的内容、韵律、音色和声学细节拆开表示，再分别生成，让零样本合成更自然，也更可控。

## 研究问题

只给一段新说话人的短语音提示，怎样既复现音色，又生成自然、准确并具有合适韵律的语音？

## 核心设计与贡献

- FACodec 通过因子化向量量化，把内容、韵律、声学细节与音色分开，结合信息瓶颈、辅助监督和对抗约束减少不同属性的混杂。
- 因子化扩散分别生成时长、韵律、内容和细节，音色由提示提供；不同属性可使用不同提示。贡献在于可解释的属性分工，而非仅增大统一生成模型。

## 关键结果

作者在 LibriSpeech test-clean 与 RAVDESS 上报告较好的相似度、可懂度和韵律。在所用主观测试中，LibriSpeech test-clean 的比较平均意见分 CMOS 相对真实录音为 −0.08。它支持该评测下接近真实录音的听感，不等于所有场景达到“人类水平”。

## 不足与适用边界

- 【作者指出】训练主要来自英语有声书，未支持多语言 TTS，也未充分覆盖现实声音多样性；内容解耦依赖音素转写监督，解耦的下游验证主要限于 TTS。
- 【分析判断】分阶段、多步扩散仍有计算成本，非自回归不等于天然流式；主观测试样本有限，推广“与真人无差别”需更广评测。

## 阅读重点与下一步

研究语音表征或可控生成时优先看 FACodec；先检查更换音色或韵律提示时，其他属性是否真的保持不变。

**原文定位：** §3（FACodec 与因子化扩散），§4.2、附录 A.3 / C（延迟与限制）；PDF 第 3–8、18、22 页。 [查看原文](https://arxiv.org/abs/2403.03100)

**关联阅读：** [GenSE: Generative Speech Enhancement via Language Models using Hierarchical Modeling](2025-gense.md) · [Libri-Light: A Benchmark for ASR with Limited or No Supervision](2019-libri-light.md)
