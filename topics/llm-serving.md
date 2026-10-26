# 大模型推理与服务系统

[返回总目录](../README.md)

本专题收录 **4 篇**论文。按研究小方向组织，每组按索引年份升序排列，同年按题目排序。

> 年份口径：arXiv 链接取首次提交年份；会议或出版社原文链接取对应发表年份。索引年份不一定等于最终会议年份。

> “研究切入点”用于论文导航；个人阅读笔记正文按实际阅读进度补充。

## 专题目录

1. [KV cache 管理与内存效率](#kv-cache) · 1 篇
2. [Prefill 与 Decode 的推理调度](#scheduling) · 1 篇
3. [Prefill/Decode 分离与分布式缓存](#disaggregated) · 2 篇

<a id="kv-cache"></a>

## 01 · KV cache 管理与内存效率

关注推理过程中 KV cache 的分配、共享与显存利用。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2023 | Efficient Memory Management for Large Language Model Serving with PagedAttention | 分页式 KV cache 管理与共享 | [arXiv](https://arxiv.org/abs/2309.06180) | [Notes · 待补](../notes/llm-serving/2023-pagedattention.md) |

<a id="scheduling"></a>

## 02 · Prefill 与 Decode 的推理调度

关注如何安排不同请求的 Prefill 和 Decode，以兼顾吞吐与延迟。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2024 | Taming Throughput-Latency Tradeoff in LLM Inference with Sarathi-Serve | 分块 Prefill 与无停顿批处理 | [arXiv](https://arxiv.org/abs/2403.02310) | [Notes · 待补](../notes/llm-serving/2024-sarathi-serve.md) |

<a id="disaggregated"></a>

## 03 · Prefill/Decode 分离与分布式缓存

关注两阶段分离部署，以及跨节点的 KV cache 管理。

| 年份 | 论文题目 | 研究切入点 | 原文 | 笔记 |
| --- | --- | --- | --- | --- |
| 2024 | DistServe: Disaggregating Prefill and Decoding for Goodput-optimized Large Language Model Serving | 分离 Prefill 与 Decode，并按延迟目标配置资源 | [arXiv](https://arxiv.org/abs/2401.09670) | [Notes · 待补](../notes/llm-serving/2024-distserve.md) |
| 2024 | Mooncake: A KVCache-centric Disaggregated Architecture for LLM Serving | 分离两阶段并构建分布式 KV cache | [arXiv](https://arxiv.org/abs/2407.00079) | [Notes · 待补](../notes/llm-serving/2024-mooncake.md) |

---

[返回专题目录](#专题目录) · [返回总目录](../README.md)