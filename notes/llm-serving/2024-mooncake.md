# Mooncake: A KVCache-centric Disaggregated Architecture for LLM Serving

[返回专题：大模型推理与服务系统](../../topics/llm-serving.md#disaggregated) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2024 |
| 发表信息 | arXiv:2407.00079（2024 年首次提交） |
| 研究方向 | Prefill/Decode 分离与分布式 KV cache |
| 原文 | [arXiv](https://arxiv.org/abs/2407.00079) |
| 代码 | [Mooncake](https://github.com/kvcache-ai/Mooncake) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | arXiv:2407.00079v5（2026-10-08） |
| 阅读日期 | 2026-11-03 |

> **一句话读懂：** 把 KV cache 当作集群级共享资源，联合决定缓存放哪里、请求去哪里，以及过载时哪些请求应尽早拒绝。

## 研究问题

长上下文服务中，分离 Prefill／Decode 后仍有大量 KV 搬运、重复计算和过载浪费，怎样按缓存与负载共同调度？

## 核心设计与贡献

- **以 KV cache 为中心分离资源。** 利用 GPU 集群中的 CPU、DRAM、SSD 和高速网络构建缓存层；按层传输并重叠计算，使两阶段及缓存可以协同运行。
- **缓存感知调度与早拒绝。** Conductor 权衡前缀复用、传输开销和实例负载，复制热点缓存；预测后续 Decode 压力，尽量在浪费 Prefill 计算前拒绝无法完成的请求。

## 关键结果

论文报告真实业务负载下可处理约多 75% 的请求，并另列特定模拟场景结果。其有效吞吐只计完整完成且满足目标的请求，需要连同拒绝情况、延迟目标和负载条件一起理解。

## 不足与适用边界

- 【实验边界】收益与可复用前缀、上下文长度和网络条件有关；真实业务与模拟实验的增益不能互换。
- 【分析判断】早拒绝提高资源利用，也带来请求接纳与公平性权衡；预测误差可能造成无效计算或误拒绝。不能只看被接纳请求的平均延迟。

## 阅读重点与下一步

沿一次请求追踪“缓存命中—传输—补算—Decode—拒绝判断”。评估需同时给出总到达率、完成率、拒绝率及尾延迟，区分缓存复用和两阶段分离的收益。

**原文定位：** PDF 第 2–6 页架构及请求流程；第 7–13 页传输、调度和过载策略；实验见后续评测章节。 [查看原文](https://arxiv.org/abs/2407.00079)

**关联阅读：** [Efficient Memory Management for Large Language Model Serving with PagedAttention](2023-pagedattention.md) · [DistServe: Disaggregating Prefill and Decoding for Goodput-optimized Large Language Model Serving](2024-distserve.md)
