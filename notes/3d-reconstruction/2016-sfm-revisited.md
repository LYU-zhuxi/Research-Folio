# Structure-from-Motion Revisited

[返回专题：三维重建](../../topics/3d-reconstruction.md#geometry) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2016 |
| 研究方向 | 几何基础与多视图重建 |
| 原文 | [原文](https://openaccess.thecvf.com/content_cvpr_2016/html/Schonberger_Structure-From-Motion_Revisited_CVPR_2016_paper.html) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | CVPR 2016 原文 PDF |

> **一句话读懂：** COLMAP 的经典 SfM 工作：逐环节提升匹配验证、选图、三角化和束调整的可靠性，让更多照片稳定进入同一个稀疏重建。

## 研究问题

增量式 SfM 容易因错误匹配、糟糕的初始视图和累积漂移中断；怎样兼顾重建完整性、精度与耗时？

## 核心设计与贡献

- **稳住几何入口。** 用多模型几何验证区分一般运动、平面及退化情况，结合更可靠的初始化和下一视图选择，减少错误注册。
- **不断修复重建。** 鲁棒三角化、补充三角化、外点过滤与束调整（BA）交替执行；冗余视图筛选减少全局 BA 的计算量。贡献来自完整流程的协同改进。

## 关键结果

在论文的无序图像集合上，方法恢复的相机和观测轨迹更完整，尤其适用于较大集合。冗余视图实验还展示了在相近重投影误差下缩短总耗时的可能；论文并未证明它在所有数据上运行最快。

## 不足与适用边界

- 【实验边界】输出主要是相机与稀疏点结构；完整稠密表面或新视角渲染仍需要后续模块。
- 【分析判断】依赖可重复匹配的纹理、足够重叠及静态场景假设。弱纹理、反光、重复结构或动态对象仍可能引入缺失与错误。

## 阅读重点与下一步

先理解“注册失败后如何补救”的闭环。评估时同时看注册相机数、轨迹长度、重投影误差和总耗时，单看点数不能代表几何质量。

**原文定位：** PDF 第 3–6 页方法；第 7–8 页组件与完整系统实验。 [查看原文](https://openaccess.thecvf.com/content_cvpr_2016/html/Schonberger_Structure-From-Motion_Revisited_CVPR_2016_paper.html)

**关联阅读：** [Visual Geometry Grounded Deep Structure From Motion](2023-vggsfm.md) · [DUSt3R: Geometric 3D Vision Made Easy](2023-dust3r.md)
