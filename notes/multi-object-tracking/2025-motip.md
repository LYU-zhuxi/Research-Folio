# Multiple Object Tracking as ID Prediction

[返回专题：多目标跟踪](../../topics/multi-object-tracking.md#tracking) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2025 |
| 发表信息 | CVPR 2025 |
| 方法简称 | MOTIP |
| 研究方向 | 多目标跟踪方法 · 上下文 ID 预测与身份关联 |
| 原文 | [会议原文](https://openaccess.thecvf.com/content/CVPR2025/html/Gao_Multiple_Object_Tracking_as_ID_Prediction_CVPR_2025_paper.html) |
| 代码 | [MOTIP](https://github.com/MCG-NJU/MOTIP) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | CVPR 2025 原文 PDF |

> **一句话读懂：** 保留检测与关联的职责划分，但把关联改为“参考历史轨迹，为当前对象预测 ID”，从手工匹配规则转向上下文学习。

## 研究问题

传统关联依赖人工设计的相似度和运动规则，而统一检测／轨迹查询又可能产生任务冲突；能否将检测和关联分开建模，同时保持端到端可训练？

## 核心设计与贡献

- **ID 是上下文标签。** Deformable DETR 输出目标框及对象特征；历史特征附上可学习的 ID 嵌入，ID Decoder 据此为当前对象预测已有身份或新生标记。ID 槽位可回收，不是训练集中固定的人物类别，因此能处理未见对象。
- **让当前对象联合判断。** 解码器通过交叉注意力读取历史、通过自注意力交换当前对象信息，再以分类损失学习关联，默认推理不依赖匈牙利匹配。
- **训练中模拟不可靠历史。** 随机丢弃轨迹 token 模拟遮挡，交换部分 ID token 模拟身份错误，缩小训练时真实轨迹与测试时预测轨迹之间的差距。

## 关键结果

论文在 DanceTrack、SportsMOT 和鸟类跟踪 BFT 上验证方法。在 DanceTrack 所列比较中，以 Deformable DETR／ResNet-50 为平台，相对 CO-MOT 提高 **4.3 个百分点 HOTA**（综合跟踪指标）和 **6.9 个百分点 AssA**（关联准确率），支持其在相似外观、复杂运动下学习关联的价值。

## 不足与适用边界

- 【作者指出】ID 字典容量 K 在拥挤场景可能不足；默认 K=50，需按实际并发目标规模调整。仅用对象特征，也留下引入运动、深度及更强轨迹建模的空间。
- 【分析判断】依赖检测召回和历史轨迹质量，漏检或错误 ID 仍可能向后传播。推理保留置信度、新生目标判定等规则，可学习关联并不保证长遮挡后一定恢复原身份。

## 阅读重点与下一步

先理解“临时 ID 字典”为什么能泛化到未见对象，再看历史增强和解码器自注意力的消融。应用时固定检测器，分别测试遮挡长度、ID 错误累积及目标数量，判断关联模块的真实收益。

**原文定位：** PDF 第 3–5 页上下文 ID、训练增强与推理；第 6–8 页比较、消融及局限。 [查看原文](https://openaccess.thecvf.com/content/CVPR2025/html/Gao_Multiple_Object_Tracking_as_ID_Prediction_CVPR_2025_paper.html)

**关联阅读：** [End-to-End Object Detection with Transformers](2020-detr.md) · [TrackFormer: Multi-Object Tracking With Transformers](2022-trackformer.md)
