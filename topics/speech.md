# 语音

[返回总目录](../README.md)

本专题收录 **17 篇**论文。按研究小方向组织，每组按索引年份升序排列，同年按题目排序。

> 年份口径：arXiv 链接取首次提交年份；会议或出版社原文链接取对应发表年份。索引年份不一定等于最终会议年份。

> 分类依据论文的主要研究问题及本地阅读上下文；“研究切入点”是导航说明，个人阅读笔记正文暂留空。

## 专题目录

1. [视听语音分离与目标说话人提取](#av-separation) · 4 篇
2. [视听语音增强](#av-enhancement) · 1 篇
3. [生成式语音增强](#generative-enhancement) · 1 篇
4. [视听自监督表征学习](#representation) · 1 篇
5. [语音合成与生成](#synthesis) · 1 篇
6. [视听实例分割与发声对象理解](#av-segmentation) · 1 篇
7. [视听分割的视觉基础](#vision-foundations) · 2 篇
8. [构音障碍与语音可懂度评估](#dysarthria) · 2 篇
9. [数据集、基准与质量评价](#datasets-metrics) · 2 篇
10. [音频理解与多模态大模型](#audio-models) · 2 篇

<a id="av-separation"></a>

## 01 · 视听语音分离与目标说话人提取

关注如何利用唇动等视觉线索，从混合音频中分离目标语音。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2019 | Time Domain Audio Visual Speech Separation | 时域视听融合与目标说话人语音提取 | [arXiv](https://arxiv.org/abs/1904.03760) | [Notes · 待补](../notes/speech/2019-av-convtasnet.md) |
| 2024 | IIANet: An Intra- and Inter-Modality Attention Network for Audio-Visual Speech Separation | 模态内与模态间注意力及多尺度视听融合 | [原文](https://proceedings.mlr.press/v235/li24cf.html) | [Notes · 待补](../notes/speech/2024-iianet.md) |
| 2024 | RAVSS: Robust Audio-Visual Speech Separation in Multi-Speaker Scenarios with Missing Visual Cues | 多说话人与视觉线索缺失条件下的鲁棒分离 | [原文](https://doi.org/10.1145/3664647.3681261) | [Notes · 待补](../notes/speech/2024-ravss.md) |
| 2025 | Efficient Audio-Visual Speech Separation with Discrete Lip Semantics and Multi-Scale Global-Local Attention | 离散唇语语义与高效全局、局部注意力 | [arXiv](https://arxiv.org/abs/2509.23610) | [Notes · 待补](../notes/speech/2025-dolphin.md) |

<a id="av-enhancement"></a>

## 02 · 视听语音增强

关注利用视听上下文恢复被噪声破坏的语音。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2025 | CogCM: Cognition-Inspired Contextual Modeling for Audio-Visual Speech Enhancement | 语义与信号上下文协同的视听语音增强 | [原文](https://openaccess.thecvf.com/content/ICCV2025/papers/Wang_CogCM_Cognition-Inspired_Contextual_Modeling_for_Audio-Visual_Speech_Enhancement_ICCV_2025_paper.pdf) | [Notes · 待补](../notes/speech/2025-cogcm.md) |

<a id="generative-enhancement"></a>

## 03 · 生成式语音增强

关注基于语言模型和离散 token 的语音恢复。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2025 | GenSE: Generative Speech Enhancement via Language Models using Hierarchical Modeling | 通过分层语义与声学 token 建模增强语音 | [arXiv](https://arxiv.org/abs/2502.02942) | [Notes · 待补](../notes/speech/2025-gense.md) |

<a id="representation"></a>

## 04 · 视听自监督表征学习

关注音频与唇动的联合预训练及其对下游语音任务的支持。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2022 | Learning Audio-Visual Speech Representation by Masked Multimodal Cluster Prediction | 掩码多模态聚类预测与视听自监督表征 | [arXiv](https://arxiv.org/abs/2201.02184) | [Notes · 待补](../notes/speech/2022-av-hubert.md) |

<a id="synthesis"></a>

## 05 · 语音合成与生成

关注编解码表示、零样本合成与扩散生成。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2024 | NaturalSpeech 3: Zero-Shot Speech Synthesis with Factorized Codec and Diffusion Models | 因子化语音编解码与扩散式零样本语音合成 | [arXiv](https://arxiv.org/abs/2403.03100) | [Notes · 待补](../notes/speech/2024-naturalspeech-3.md) |

<a id="av-segmentation"></a>

## 06 · 视听实例分割与发声对象理解

关注音频与场景对象之间的对应、定位及跟踪。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2025 | Audio-Visual Instance Segmentation | 发声对象实例的识别、分割与跟踪 | [原文](https://openaccess.thecvf.com/content/CVPR2025/html/Guo_Audio-Visual_Instance_Segmentation_CVPR_2025_paper.html) | [Notes · 待补](../notes/speech/2025-avis.md) |

<a id="vision-foundations"></a>

## 07 · 视听分割的视觉基础

以下为阅读视听实例分割时关联的纯视觉论文，并非语音方法。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2021 | Masked-attention Mask Transformer for Universal Image Segmentation | 统一图像分割；作为视听实例分割的视觉基础 | [arXiv](https://arxiv.org/abs/2112.01527) | [Notes · 待补](../notes/speech/2021-mask2former.md) |
| 2022 | VITA: Video Instance Segmentation via Object Token Association | 对象 token 关联；作为视频实例建模的视觉基础 | [arXiv](https://arxiv.org/abs/2206.04403) | [Notes · 待补](../notes/speech/2022-vita.md) |

<a id="dysarthria"></a>

## 08 · 构音障碍与语音可懂度评估

关注异常发音、跨语言音系差异与自动可懂度评估。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2023 | Speech Intelligibility Assessment of Dysarthric Speech by using Goodness of Pronunciation with Uncertainty Quantification | 结合发音良好度与不确定性的可懂度评估 | [arXiv](https://arxiv.org/abs/2305.18392) | [Notes · 待补](../notes/speech/2023-gop-uncertainty.md) |
| 2026 | Multilingual Dysarthric Speech Assessment Using Universal Phone Recognition and Language-Specific Phonemic Contrast Modeling | 通用音素识别与语言特定音系对比评估 | [arXiv](https://arxiv.org/abs/2601.21205) | [Notes · 待补](../notes/speech/2026-multilingual-dysarthric-assessment.md) |

<a id="datasets-metrics"></a>

## 09 · 数据集、基准与质量评价

收录语音研究中使用或关注的数据资源与评价方法。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2019 | Libri-Light: A Benchmark for ASR with Limited or No Supervision | 少监督与无监督语音识别数据和基准 | [arXiv](https://arxiv.org/abs/1912.07875) | [Notes · 待补](../notes/speech/2019-libri-light.md) |
| 2020 | DNSMOS: A Non-Intrusive Perceptual Objective Speech Quality Metric to Evaluate Noise Suppressors | 无需参考干净语音的感知质量评价 | [arXiv](https://arxiv.org/abs/2010.15258) | [Notes · 待补](../notes/speech/2020-dnsmos.md) |

<a id="audio-models"></a>

## 10 · 音频理解与多模态大模型

仅收录与音频研究直接相关的大模型工作，作为本专题的关联阅读。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2025 | Qwen3-Omni Technical Report | 面向音频理解与生成的全模态模型相关工作 | [arXiv](https://arxiv.org/abs/2509.17765) | [Notes · 待补](../notes/speech/2025-qwen3-omni.md) |
| 2026 | DIFFA-2: A Practical Diffusion Large Language Model for General Audio Understanding | 面向通用音频理解的扩散大语言模型 | [arXiv](https://arxiv.org/abs/2601.23161) | [Notes · 待补](../notes/speech/2026-diffa-2.md) |

---

[返回专题目录](#专题目录) · [返回总目录](../README.md)
