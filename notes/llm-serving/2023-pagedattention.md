# Efficient Memory Management for Large Language Model Serving with PagedAttention

[返回专题：大模型推理与服务系统](../../topics/llm-serving.md#kv-cache) · [总目录](../../README.md)

| 项目 | 信息 |
| --- | --- |
| 索引年份 | 2023 |
| 发表信息 | SOSP 2023 |
| 研究方向 | KV cache 管理与内存效率 |
| 原文 | [arXiv](https://arxiv.org/abs/2309.06180) |
| 代码 | [vLLM](https://github.com/vllm-project/vllm) |
| 笔记状态 | 已整理 · 精简总结 |
| 阅读版本 | arXiv:2309.06180v1（2023-09-12） |
| 阅读日期 | 2026-11-03 |

> **一句话读懂：** 把 KV cache 像操作系统内存一样分页管理，减少预留、碎片与重复拷贝，让同一显存能同时承载更多请求。

## 研究问题

自回归生成的长度不确定，连续显存预分配会浪费大量 KV cache 空间，怎样提高批处理容量且保持准确输出？

## 核心设计与贡献

- **逻辑连续、物理分块。** KV cache 按固定 token 块按需分配，块表把逻辑位置映射到非连续显存，专门的注意力内核读取这些块。
- **共享与调度协同。** 对公共前缀及分支生成共享块，修改时写时复制；结合块级回收、抢占与请求调度，在 vLLM 中形成完整系统。

## 关键结果

论文相对当时的 FasterTransformer、Orca 等系统，在相近延迟下报告约 2–4 倍吞吐提升，长序列及复杂解码时收益更明显。主要收益来自更高并发和共享效率，并非每次注意力运算都更快。

## 不足与适用边界

- 【作者指出】块表访问和分支带来内核开销，其实验注意力内核延迟比 FasterTransformer 高约 20–26%，端到端仍可因批量增大获益。
- 【分析判断】分页消除的是管理浪费，不能消除 KV cache 随上下文增长的实际容量需求；低并发或无共享时收益可能缩小。

## 阅读重点与下一步

画清 token、逻辑块、物理块与引用计数的关系。评估时同时看显存利用、可容纳请求数和端到端延迟，历史结果不能直接代表当前软件版本。

**原文定位：** PDF 第 5–9 页分页、共享与实现；第 10–12 页实验及内核开销。 [查看原文](https://arxiv.org/abs/2309.06180)

**关联阅读：** [Taming Throughput-Latency Tradeoff in LLM Inference with Sarathi-Serve](2024-sarathi-serve.md) · [Mooncake: A KVCache-centric Disaggregated Architecture for LLM Serving](2024-mooncake.md)
