# Taming Throughput-Latency Tradeoff in LLM Inference with Sarathi-Serve

[返回专题：大模型推理与服务系统](../../topics/llm-serving.md#scheduling) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2024 |
| 发表信息 | OSDI 2024 |
| 研究方向 | 分块 Prefill 与推理调度 |
| 原文 | [arXiv](https://arxiv.org/abs/2403.02310) |
| 代码 | [Sarathi-Serve](https://github.com/microsoft/sarathi-serve) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | arXiv:2403.02310v3（2024-06-17） |
| 阅读日期 | 2026-11-03 |

> **一句话读懂：** 把长 Prefill 切成小块，优先安排正在 Decode 的请求，再利用每轮剩余 token 预算填入 Prefill，平衡吞吐与逐 token 延迟。

## 研究问题

大段 Prefill 会阻塞正在生成的请求，而只做小批量 Decode 又浪费算力，怎样让二者在同一设备上高效共存？

## 核心设计与贡献

- **分块 Prefill。** 将提示词计算拆到多轮执行，用足够大的块保持计算效率，又限制单轮对 Decode 的延迟影响。
- **按预算混合调度。** 每轮先放入运行中的 Decode，再安排未完成与新请求的 Prefill 块；接近均匀的批次还可减少流水并行的气泡。

## 关键结果

在论文的尾延迟目标下，相对当时 vLLM，Mistral-7B／单 A100 的服务容量最高约提升 2.6 倍，Yi-34B／双 A100 最高约 3.7 倍。这些是满足特定延迟约束的容量，不能当作任意负载下的生成速度。

## 不足与适用边界

- 【作者指出】分块会重复读取先前块的 KV cache，并增加部分内核开销；token 预算需结合硬件和延迟目标进行测量。
- 【分析判断】Decode 优先会影响新请求等待及首 token 时间，应同时观察 TTFT 与 token 间延迟。“无停顿”指调度不因完整 Prefill 暂停 Decode，并非延迟完全不受影响。

## 阅读重点与下一步

看清块大小的折中：太大影响交互延迟，太小降低 Prefill 效率。优先比较同一 TTFT／token 间延迟目标下的最大可服务请求率。

**原文定位：** PDF 第 6–9 页瓶颈、分块和调度；第 10–13 页容量及开销实验。 [查看原文](https://arxiv.org/abs/2403.02310)

**关联阅读：** [Efficient Memory Management for Large Language Model Serving with PagedAttention](2023-pagedattention.md) · [DistServe: Disaggregating Prefill and Decoding for Goodput-optimized Large Language Model Serving](2024-distserve.md)
