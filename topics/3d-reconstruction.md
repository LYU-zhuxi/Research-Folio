# 三维重建

[返回总目录](../README.md)

本专题收录 **25 篇**论文。按研究小方向组织，每组按索引年份升序排列，同年按题目排序。

> 年份口径：arXiv 链接取首次提交年份；会议或出版社原文链接取对应发表年份。索引年份不一定等于最终会议年份。

> 分类依据论文的主要研究问题及本地阅读上下文；“研究切入点”是导航说明，个人阅读笔记正文暂留空。

## 专题目录

1. [几何基础与多视图重建](#geometry) · 4 篇
2. [高斯场景表示与渲染](#gaussian) · 1 篇
3. [前馈重建与重建大模型](#feed-forward) · 4 篇
4. [语义与实例感知的前馈重建](#semantic-reconstruction) · 6 篇
5. [高斯语义表示与对象分割](#gaussian-segmentation) · 4 篇
6. [点云骨干与三维、四维理解](#point-cloud) · 3 篇
7. [生成式三维重建](#generative) · 1 篇
8. [三维空间推理与评估](#spatial-reasoning) · 1 篇
9. [航拍定位与相关基准](#aerial-localization) · 1 篇

<a id="geometry"></a>

## 01 · 几何基础与多视图重建

相机位姿、点图、深度及多视图几何，是后续场景重建的基础。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2016 | Structure-from-Motion Revisited | 增量式 SfM 与相机位姿、稀疏结构恢复 | [原文](https://openaccess.thecvf.com/content_cvpr_2016/html/Schonberger_Structure-From-Motion_Revisited_CVPR_2016_paper.html) | [Notes · 待补](../notes/3d-reconstruction/2016-sfm-revisited.md) |
| 2023 | DUSt3R: Geometric 3D Vision Made Easy | 无相机先验的点图预测与稠密重建 | [arXiv](https://arxiv.org/abs/2312.14132) | [Notes · 待补](../notes/3d-reconstruction/2023-dust3r.md) |
| 2023 | Visual Geometry Grounded Deep Structure From Motion | 可微分的深度 SfM 流程 | [arXiv](https://arxiv.org/abs/2312.04563) | [Notes · 待补](../notes/3d-reconstruction/2023-vggsfm.md) |
| 2025 | VGGT: Visual Geometry Grounded Transformer | 联合预测相机、深度、点图与点轨迹 | [arXiv](https://arxiv.org/abs/2503.11651) | [Notes · 待补](../notes/3d-reconstruction/2025-vggt.md) |

<a id="gaussian"></a>

## 02 · 高斯场景表示与渲染

关注三维场景如何表示，以及如何通过可微渲染完成重建。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2023 | 3D Gaussian Splatting for Real-Time Radiance Field Rendering | 显式高斯场景表示与可微实时渲染 | [arXiv](https://arxiv.org/abs/2308.04079) | [Notes · 待补](../notes/3d-reconstruction/2023-3dgs.md) |

<a id="feed-forward"></a>

## 03 · 前馈重建与重建大模型

关注从单图、多视图或长序列图像直接预测三维表示。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2023 | LRM: Large Reconstruction Model for Single Image to 3D | 单图到三维的规模化前馈重建 | [arXiv](https://arxiv.org/abs/2311.04400) | [Notes · 待补](../notes/3d-reconstruction/2023-lrm.md) |
| 2024 | DepthSplat: Connecting Gaussian Splatting and Depth | 多视图深度估计与高斯重建的相互促进 | [arXiv](https://arxiv.org/abs/2410.13862) | [Notes · 待补](../notes/3d-reconstruction/2024-depthsplat.md) |
| 2024 | Long-LRM: Long-sequence Large Reconstruction Model for Wide-coverage Gaussian Splats | 长图像序列与大范围场景高斯重建 | [arXiv](https://arxiv.org/abs/2410.12781) | [Notes · 待补](../notes/3d-reconstruction/2024-long-lrm.md) |
| 2026 | TokenGS: Decoupling 3D Gaussian Prediction from Pixels with Learnable Tokens | 用可学习 token 解耦高斯预测与输入像素 | [arXiv](https://arxiv.org/abs/2604.15239) | [Notes · 待补](../notes/3d-reconstruction/2026-tokengs.md) |

<a id="semantic-reconstruction"></a>

## 04 · 语义与实例感知的前馈重建

关注在重建过程中联合学习语义、对象结构和语言查询能力。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2024 | Large Spatial Model: End-to-end Unposed Images to Semantic 3D | 从无位姿图像联合恢复几何、外观与语义 | [arXiv](https://arxiv.org/abs/2410.18956) | [Notes · 待补](../notes/3d-reconstruction/2024-large-spatial-model.md) |
| 2025 | FLEG: Feed-Forward Language Embedded Gaussian Splatting from Any Views via Compact Semantic Representation | 任意视图输入与紧凑语言语义高斯表示 | [arXiv](https://arxiv.org/abs/2512.17541) | [Notes · 待补](../notes/3d-reconstruction/2025-fleg.md) |
| 2025 | SIU3R: Simultaneous Scene Understanding and 3D Reconstruction Beyond Feature Alignment | 统一重建与多类场景分割任务 | [arXiv](https://arxiv.org/abs/2507.02705) | [Notes · 待补](../notes/3d-reconstruction/2025-siu3r.md) |
| 2025 | Uni3R: Unified 3D Reconstruction and Semantic Understanding via Generalizable Gaussian Splatting from Unposed Multi-View Images | 可泛化高斯表示中的重建与开放词汇语义 | [arXiv](https://arxiv.org/abs/2508.03643) | [Notes · 待补](../notes/3d-reconstruction/2025-uni3r.md) |
| 2026 | GroupForward: Building Referable 3D Scenes via Instance-Grouped Feed-Forward Gaussian Splatting | 实例分组的前馈高斯重建与指代表达查询 | [arXiv](https://arxiv.org/abs/2608.17535) | [Notes · 待补](../notes/3d-reconstruction/2026-groupforward.md) |
| 2026 | Scenes as Objects, Not Primitives: Instance-Structured 3D Tokenization from Unposed Views | 从无位姿图像构建以实例为单位的三维 token | [arXiv](https://arxiv.org/abs/2606.29513) | [Notes · 待补](../notes/3d-reconstruction/2026-instok3d.md) |

<a id="gaussian-segmentation"></a>

## 05 · 高斯语义表示与对象分割

关注高斯场景中的语义一致性、实例归属及紧凑表示。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2024 | InstanceGaussian: Appearance-Semantic Joint Gaussian Representation for 3D Instance-Level Perception | 外观与语义联合学习及自底向上的实例聚合 | [arXiv](https://arxiv.org/abs/2411.19235) | [Notes · 待补](../notes/3d-reconstruction/2024-instancegaussian.md) |
| 2026 | ChildSplat: Anchor-Child Semantic Gaussian Representation for 3D Object Segmentation | 锚点与子高斯的层次语义表示和对象分割 | [原文](https://diglib.eg.org/items/50518de3-f40c-44bb-8955-4bcd566d0b34) | [Notes · 待补](../notes/3d-reconstruction/2026-childsplat.md) |
| 2026 | CSGaussian: Progressive Rate-Distortion Compression and Segmentation for 3D Gaussian Splatting | 联合高斯压缩、语义学习与分割 | [arXiv](https://arxiv.org/abs/2601.12814) | [Notes · 待补](../notes/3d-reconstruction/2026-csgaussian.md) |
| 2026 | Scene-Agnostic Object-Centric Representation Learning for 3D Gaussian Splatting | 跨场景的对象中心表示与实例身份学习 | [原文](https://openaccess.thecvf.com/content/CVPR2026W/3DMV/papers/Hsu_Scene-Agnostic_Object-Centric_Representation_Learning_for_3D_Gaussian_Splatting_CVPRW_2026_paper.pdf) | [Notes · 待补](../notes/3d-reconstruction/2026-scene-agnostic-object-centric.md) |

<a id="point-cloud"></a>

## 06 · 点云骨干与三维、四维理解

作为重建后的感知与分割基础，涵盖点云骨干、实例分割和动态点云。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2022 | Mask3D: Mask Transformer for 3D Semantic Instance Segmentation | 基于实例 query 的三维点云实例分割 | [arXiv](https://arxiv.org/abs/2210.03105) | [Notes · 待补](../notes/3d-reconstruction/2022-mask3d.md) |
| 2023 | Point Transformer V3: Simpler, Faster, Stronger | 可扩展点云骨干与高效局部信息建模 | [arXiv](https://arxiv.org/abs/2312.10035) | [Notes · 待补](../notes/3d-reconstruction/2023-point-transformer-v3.md) |
| 2025 | Mamba4D: Efficient 4D Point Cloud Video Understanding with Disentangled Spatial-Temporal State Space Models | 解耦时空状态空间模型与动态点云理解 | [原文](https://openaccess.thecvf.com/content/CVPR2025/papers/Liu_Mamba4D_Efficient_4D_Point_Cloud_Video_Understanding_with_Disentangled_Spatial-Temporal_CVPR_2025_paper.pdf) | [Notes · 待补](../notes/3d-reconstruction/2025-mamba4d.md) |

<a id="generative"></a>

## 07 · 生成式三维重建

关注扩散模型如何从二维监督中学习三维生成。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2024 | A Lesson in Splats: Teacher-Guided Diffusion for 3D Gaussian Splats Generation with 2D Supervision | 二维监督下的教师引导三维高斯扩散生成 | [arXiv](https://arxiv.org/abs/2412.00623) | [Notes · 待补](../notes/3d-reconstruction/2024-a-lesson-in-splats.md) |

<a id="spatial-reasoning"></a>

## 08 · 三维空间推理与评估

作为相关研究，关注模型是否真正利用三维信息进行空间推理。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2026 | Do 3D Large Language Models Really Understand 3D Spatial Relationships? | 三维空间关系推理与评估中的语言捷径 | [arXiv](https://arxiv.org/abs/2603.23523) | [Notes · 待补](../notes/3d-reconstruction/2026-real-3dqa.md) |

<a id="aerial-localization"></a>

## 09 · 航拍定位与相关基准

作为重建的关联方向，关注无人机场景中的定位与城市几何对齐。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2026 | LoD-Loc v3: Generalized Aerial Localization in Dense Cities using Instance Silhouette Alignment | 利用实例轮廓对齐进行城市航拍定位 | [arXiv](https://arxiv.org/abs/2603.19609) | [Notes · 待补](../notes/3d-reconstruction/2026-lod-loc-v3.md) |

---

[返回专题目录](#专题目录) · [返回总目录](../README.md)
