# RAVSS: Robust Audio-Visual Speech Separation in Multi-Speaker Scenarios with Missing Visual Cues

[返回专题：语音](../../topics/speech.md#av-separation) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2024 |
| 研究方向 | 视听语音分离与目标说话人提取 |
| 原文 | [原文](https://doi.org/10.1145/3664647.3681261) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | ACM Multimedia 2024 |

> **一句话读懂：** 让多个说话人的分离过程相互配合：可见说话人的线索，也能帮助区分缺少视频的其他声源。

## 研究问题

说话人变多、部分人不在画面中或视频帧缺失时，如何保持视听分离的完整性？

## 核心设计与贡献

- 联合维护多个说话人的音频表示，结合局部、全局内容建模和说话人间交互，一次协同输出多个声源，避免把各目标当作互不相关的独立提取任务。
- 在只有部分视觉线索时，分别处理有视觉引导与无视觉引导的分支，再通过跨说话人交互传递区分信息；创新重点是联合分离及视觉缺失适应机制。

## 关键结果

作者在 VoxCeleb2、LRS3 构造的 2–5 人混音上，比较完整视频、部分说话人无视频及随机帧置零三类设置，报告较强的分离表现及较小的性能下降。证据直接对应“多说话人”和“缺失线索”，而非仅在标准双人混音上提升。

## 不足与适用边界

- 【实验边界】随机帧置零与整段视觉缺失是可控模拟，不能完全代表遮挡、错误人脸跟踪、音画错位和模态信息相互矛盾。
- 【分析判断】方法以 N 个待分离说话人的表示组织输出；现有结果不能直接说明可自动估计任意未知人数，联合交互的开销也需随人数评估。

## 阅读重点与下一步

研究视觉缺失或多人分离时值得优先读。下一步宜把随机丢帧替换为连续遮挡，检查联合交互是否仍能补偿。

**原文定位：** §3（联合分离与说话人交互），§4（2–5 人及视觉缺失实验）；PDF 第 3、5、7、11–14 页。 [查看原文](https://doi.org/10.1145/3664647.3681261)

**关联阅读：** [IIANet: An Intra- and Inter-Modality Attention Network for Audio-Visual Speech Separation](2024-iianet.md) · [Efficient Audio-Visual Speech Separation with Discrete Lip Semantics and Multi-Scale Global-Local Attention](2025-dolphin.md)
