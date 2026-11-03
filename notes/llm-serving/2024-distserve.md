# DistServe: Disaggregating Prefill and Decoding for Goodput-optimized Large Language Model Serving

[返回专题：大模型推理与服务系统](../../topics/llm-serving.md#disaggregated) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2024 |
| 发表信息 | OSDI 2024 |
| 研究方向 | Prefill/Decode 分离与服务性能 |
| 原文 | [arXiv](https://arxiv.org/abs/2401.09670) |
| 代码 | [DistServe](https://github.com/LLMServe/DistServe) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | arXiv:2401.09670v3（2024-06-06） |
| 阅读日期 | 2026-11-03 |

> **一句话读懂：** 把 Prefill 和 Decode 放到不同 GPU，分别配置资源与并行策略，以每张 GPU 满足延迟目标的有效请求率优化成本。

## 研究问题

Prefill 偏计算密集、Decode 偏访存密集，混合部署会互相干扰；如何在首 token 和后续 token 延迟都达标时提高服务能力？

## 核心设计与贡献

- **按阶段独立配置。** 分离两阶段，分别选择 GPU 数量与张量／流水并行策略，再按流量扩副本，避免用同一配置同时迁就两种瓶颈。
- **带宽感知放置。** 将 KV cache 从 Prefill 传到 Decode，结合节点内外带宽安排实例位置。优化指标是 per-GPU goodput，即满足服务目标的有效请求率。

## 关键结果

在多模型、负载与延迟设置下，相对论文基线报告最高约 7.4 倍请求容量，或支持约 12.6 倍更严格的延迟目标，并要求超过 90% 请求达标。这是不同实验口径，不能把两个最大值当成同时获得。

## 不足与适用边界

- 【作者指出】KV 传输会占用显著带宽，跨节点带宽不足时必须借助放置约束，不能假设分离通信总可忽略。
- 【分析判断】独立实例增加资源配置和运维复杂度；收益取决于模型、输入输出长度、负载及网络，不适合直接外推到单 GPU 或低负载。

## 阅读重点与下一步

先明确 TTFT（首 token 时间）、TPOT（每个输出 token 时间）与达标比例，再看资源搜索和放置算法；比较必须统一 GPU 总预算。

**原文定位：** PDF 第 4–7 页干扰分析、通信与部署优化；第 8–12 页 goodput 实验。 [查看原文](https://arxiv.org/abs/2401.09670)

**关联阅读：** [Taming Throughput-Latency Tradeoff in LLM Inference with Sarathi-Serve](2024-sarathi-serve.md) · [Mooncake: A KVCache-centric Disaggregated Architecture for LLM Serving](2024-mooncake.md)
