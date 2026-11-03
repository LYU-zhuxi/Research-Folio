# Scene-Agnostic Object-Centric Representation Learning for 3D Gaussian Splatting

[返回专题：三维重建](../../topics/3d-reconstruction.md#gaussian-segmentation) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2026 |
| 研究方向 | 高斯语义表示与对象分割 |
| 原文 | [原文](https://openaccess.thecvf.com/content/CVPR2026W/3DMV/papers/Hsu_Scene-Agnostic_Object-Centric_Representation_Learning_for_3D_Gaussian_Splatting_CVPRW_2026_paper.pdf) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | CVPR Workshops 2026 原文 PDF |

> **一句话读懂：** 借助跨场景学习的对象中心模型和共享码本，为高斯提供更一致的对象身份监督，减少单纯按外观碎片分组。

## 研究问题

逐视图分割掩码容易缺乏稳定对象关系，能否把对象中心学习的整体性先验用于三维高斯分组？

## 核心设计与贡献

- **共享对象表征。** 预训练 GOLD 从图像中提供无监督对象掩码，学习的全局码本为高斯身份特征提供共同参照，减少额外掩码一致性处理。
- **保留独立的场景重建。** 按视图优化场景高斯身份，并用邻域正则保持三维一致；对象发现与外观重建相对分开，避免分组失败直接拖垮图像重建。

## 关键结果

OCTA 等对象中心评测中，方法提高 ARI／AMI 等对象聚类指标，但 mIoU 并非所有比较中最高。论文将这一差异解释为对象整体性与掩码边缘锐度之间的权衡。

## 不足与适用边界

- 【作者指出】兼容对象中心学习与三维重建的数据有限，复杂场景验证仍不足；槽位与码本学习也有成本。
- 【实验边界】共享码本不代表跨场景每个真实物体都获得唯一身份，场景高斯仍需优化。部分对象指标在训练视图计算，应与未见视角表现区分。

## 阅读重点与下一步

区分对象整体性、边界精度和新场景泛化。除平均分数外，还应检查同外观对象能否分开、一个对象是否被拆成多个槽位。

**原文定位：** PDF 第 3–5 页码本及高斯身份学习；第 6–8 页指标、比较与局限。 [查看原文](https://openaccess.thecvf.com/content/CVPR2026W/3DMV/papers/Hsu_Scene-Agnostic_Object-Centric_Representation_Learning_for_3D_Gaussian_Splatting_CVPRW_2026_paper.pdf)

**关联阅读：** [InstanceGaussian: Appearance-Semantic Joint Gaussian Representation for 3D Instance-Level Perception](2024-instancegaussian.md) · [Scenes as Objects, Not Primitives: Instance-Structured 3D Tokenization from Unposed Views](2026-instok3d.md)
