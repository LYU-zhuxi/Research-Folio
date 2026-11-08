# TrackFormer: Multi-Object Tracking With Transformers

[返回专题：多目标跟踪](../../topics/multi-object-tracking.md#tracking) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2022 |
| 发表信息 | CVPR 2022 |
| 方法简称 | TrackFormer |
| 研究方向 | 多目标跟踪方法 · 轨迹 query 与注意力关联 |
| 原文 | [会议原文](https://openaccess.thecvf.com/content/CVPR2022/html/Meinhardt_TrackFormer_Multi-Object_Tracking_With_Transformers_CVPR_2022_paper.html) |
| 代码 | [TrackFormer](https://github.com/timmeinhardt/trackformer) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | CVPR 2022 原文 PDF |

> **一句话读懂：** 将上一帧对象的解码特征变成下一帧的轨迹查询，让注意力同时完成新目标检测与已有目标的身份延续。

## 研究问题

检测后再用运动模型、外观相似度或图优化关联，往往需要独立模块；能否在同一个网络内直接延续每个对象的轨迹？

## 核心设计与贡献

- **两类 query 各司其职。** 固定 object query 发现新对象，随视频更新的 track query（轨迹查询）携带已有对象信息；两者共同关注当前帧，并通过查询间交互减少身份混淆。
- **把关联放进注意力。** 跨帧传递解码特征，结合身份约束训练及漏检、误检、帧间隔增强，学习维持或终止轨迹；失活查询短期保留，支持遮挡后恢复，无需独立的外观重识别网络。

## 关键结果

论文在 MOT17 跟踪和 MOTS20 跟踪分割中展示竞争力，组件消融表明轨迹查询及跨帧增强对身份保持很重要。短期查询恢复带来约 **1.4 个百分点的 IDF1** 改善，但这是组件消融结果；主结果仍需区分公共／私有检测及额外训练数据。

## 不足与适用边界

- 【作者指出】轨迹查询包含空间信息，难以应对长期遮挡后发生大幅位移的对象，短期恢复不能等同于长期重识别。
- 【实验边界】推理仍有置信度阈值、轨迹保留窗口及清理高度重叠重复框的 NMS。端到端可训练不代表完全取消轨迹管理规则。

## 阅读重点与下一步

重点看检测查询如何转成轨迹查询，以及遮挡后何时恢复、何时新建身份。评估时同时观察检测覆盖与 IDF1（身份保持指标），并按遮挡时长检查身份切换。

**原文定位：** PDF 第 3–5 页查询传播、轨迹管理与训练；第 6–8 页评测设置、结果及消融。 [查看原文](https://openaccess.thecvf.com/content/CVPR2022/html/Meinhardt_TrackFormer_Multi-Object_Tracking_With_Transformers_CVPR_2022_paper.html)

**关联阅读：** [End-to-End Object Detection with Transformers](2020-detr.md) · [Multiple Object Tracking as ID Prediction](2025-motip.md)
