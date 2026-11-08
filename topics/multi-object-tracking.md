# 多目标跟踪

[返回总目录](../README.md)

本专题收录 **3 篇**论文，围绕目标定位、跨帧关联与身份保持展开，按“目标检测基础”和“多目标跟踪方法”组织。每组按年份从早到晚排列。

> 年份口径：本专题当前采用会议原文链接，索引年份取对应发表年。

> 每篇 Notes 概括核心思路、创新贡献、关键结果与适用边界。

## 专题目录

1. [目标检测基础](#detection) · 1 篇
2. [多目标跟踪方法](#tracking) · 2 篇

<a id="detection"></a>

## 01 · 目标检测基础

关注单帧中的目标定位与类别预测。DETR 的集合预测与 object query 为后续 Transformer 跟踪方法提供基础。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2020 | End-to-End Object Detection with Transformers | 将目标检测建模为集合预测，以 object query 与二分匹配学习目标定位 | [原文](https://www.ecva.net/papers/eccv_2020/papers_ECCV/html/832_ECCV_2020_paper.php) | [Notes](../notes/multi-object-tracking/2020-detr.md) |

<a id="tracking"></a>

## 02 · 多目标跟踪方法

关注视频中多个对象的连续定位、轨迹建立与身份保持，当前收录基于 Transformer 的可学习关联方法。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2022 | TrackFormer: Multi-Object Tracking With Transformers | 通过跨帧传递的 track query 和注意力机制维持目标身份 | [原文](https://openaccess.thecvf.com/content/CVPR2022/html/Meinhardt_TrackFormer_Multi-Object_Tracking_With_Transformers_CVPR_2022_paper.html) | [Notes](../notes/multi-object-tracking/2022-trackformer.md) |
| 2025 | Multiple Object Tracking as ID Prediction | 利用历史轨迹上下文预测当前检测对象的 ID，将关联转化为可学习的身份预测 | [原文](https://openaccess.thecvf.com/content/CVPR2025/html/Gao_Multiple_Object_Tracking_as_ID_Prediction_CVPR_2025_paper.html) | [Notes](../notes/multi-object-tracking/2025-motip.md) |

---

[返回专题目录](#专题目录) · [返回总目录](../README.md)
