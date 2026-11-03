# ChildSplat: Anchor-Child Semantic Gaussian Representation for 3D Object Segmentation

[返回专题：三维重建](../../topics/3d-reconstruction.md#gaussian-segmentation) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2026 |
| 研究方向 | 高斯语义表示与对象分割 |
| 原文 | [原文](https://diglib.eg.org/items/50518de3-f40c-44bb-8955-4bcd566d0b34) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | Pacific Graphics 2026 原文 PDF |

> **一句话读懂：** 在锚点语义上增加子高斯级修正，让同一锚点覆盖的不同对象或部件可以拥有更细的边界。

## 研究问题

锚点共享语义节省表示，却可能横跨多个对象；如何在保持已有外观重建的同时改善局部分割？

## 核心设计与贡献

- **锚点上下文加子级残差。** 冻结预训练 Scaffold-GS 的几何与外观，利用锚点特征及子高斯几何位置预测局部语义修正。
- **用可见贡献细化归属。** 多视图掩码和冻结光栅化贡献提供子高斯归属监督；在具有对象／部件标签时，加入相应层次约束。

## 关键结果

公共 LERF-Mask 评测报告 80.2 mIoU、76.4 mBIoU，显示子级建模对对象边界的价值。SAM3 辅助构建的 LERF-Obj 使用不同训练掩码，应作为补充分析，不能直接并入公共基准排名。

## 不足与适用边界

- 【作者指出】依赖基础重建及掩码质量，并增加语义训练与推理成本；层次分割的验证范围仍有限。
- 【实验边界】缓存后的查询速度不包含首次语义计算、基础场景训练及掩码生成，不能视为从原始图像到结果的总耗时。

## 阅读重点与下一步

重点看子高斯修正能否减少跨对象污染。复现时记录公共／辅助数据协议，并分开计时基础训练、语义训练、首次查询和缓存查询。

**原文定位：** PDF 第 3–7 页表示及监督；第 8–9 页结果和耗时；第 11 页局限。 [查看原文](https://diglib.eg.org/items/50518de3-f40c-44bb-8955-4bcd566d0b34)

**关联阅读：** [InstanceGaussian: Appearance-Semantic Joint Gaussian Representation for 3D Instance-Level Perception](2024-instancegaussian.md) · [CSGaussian: Progressive Rate-Distortion Compression and Segmentation for 3D Gaussian Splatting](2026-csgaussian.md)
