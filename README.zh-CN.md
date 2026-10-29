# DT-Router

[English](README.md) | 简体中文

**兼顾回答质量与推理成本的大模型路由。**

DTRouter 是 **蚂蚁数科（Ant Digital Technologies）** 研发的闭源大模型路由方法。

蚂蚁数科围绕模型服务和任务交付提供两款产品：**[DTMaaS](https://maas.antdigital.com/)** 通过统一 API 接入多种大模型，为开发者构建 AI 应用提供模型服务；**[AiWork](https://aiwork.dtagi.cn/home)** 将编码与办公结合在共享上下文的工作流中，通过自主规划、执行和校验推进任务交付。

**DTRouter 则探索模型服务与智能体工作流共同面对的模型选择问题**：如何根据不同请求的能力需求和成本约束，选择合适的模型，平衡回答质量与推理开销。本仓库介绍这项路由工作，并提供两款产品的使用入口。

**[访问 MaaS](https://maas.antdigital.com/) · [体验 AiWork](https://aiwork.dtagi.cn/home) · [MaaS 产品文档](https://maas.antdigital.com/docs/intro)**

## 1. 为什么需要模型路由？

不同模型在能力、响应时间和价格上各有特点。按请求选择模型，为开发者管理 AI 应用的回答质量和使用成本提供了另一种方式。

DTRouter 通过请求级模型选择探索这种权衡，希望让模型能力用在能带来价值的地方，同时关注推理开销。


## 2. 使用蚂蚁数科 MaaS 构建应用

如果你希望在应用中使用多种模型，可以了解 **DTMaaS**，即蚂蚁数科面向企业的模型即服务（Model-as-a-Service）平台。

MaaS 提供统一 API，支持访问 LingDT、Qwen、DeepSeek 等模型。

| 能力 | 对开发者的价值 |
| --- | --- |
| 统一模型接入 | 使用兼容 OpenAI 的接口，通过请求参数切换平台支持的模型。 |
| 服务调度与故障切换 | 使用平台的调度及节点故障切换机制调用模型服务。 |
| 推理成本优化 | 结合平台的缓存和路由优化能力，提高模型使用效率。 |
| 统一计费 | 在统一服务平台中管理模型消耗与费用。 |

产品详情请参阅[平台介绍](https://maas.antdigital.com/docs/intro)和[平台优势](https://maas.antdigital.com/docs/intro/advantages)。

### 2.1 快速体验 MaaS

1. 访问 [MaaS 平台](https://maas.antdigital.com/)，获取 API Key。
2. 按照[快速接入指南](https://maas.antdigital.com/docs/quick-access)，从[支持的模型](https://maas.antdigital.com/docs/intro/supported-models)中选择可用模型。
3. 通过兼容 OpenAI 的端点发起第一个请求。

以下示例演示如何调用 MaaS 上的指定模型。

```bash
curl https://maas-api.antdigital.com/v1/chat/completions \
  -H "Authorization: Bearer ${MAAS_API_KEY}" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "qwen3.6-plus",
    "messages": [
      {"role": "user", "content": "请解释模型路由在 AI 应用中的作用。"}
    ]
  }'
```

模型接入和产品集成请从 [MaaS 文档](https://maas.antdigital.com/docs/intro)开始。

## 3. AiWork：编码与办公协同交付

**Agent Team is Ready.**

[AiWork](https://aiwork.dtagi.cn/home) 将编码与办公结合在同一工作流中。两种模式共享上下文，自主完成规划、执行和校验，让任务逐步收敛到可检查的交付成果。

| 模式 | AiWork 可以帮助你完成的工作 |
| --- | --- |
| 编码 | 关注代码的可维护性、架构判断和工程质量；对照目标检查进展，定位问题、修复重验，并从规划、代码和整体三个层面审查质量。 |
| 办公 | 覆盖文档读写、转换与汇总，联网研究与分析，电脑与网页操作，连接器及 MCP 服务，专家技能，以及定时自动任务六类能力。 |

**在交付过程中保持人机协同。** 执行过程中支持通过、驳回和接管；交付产物可追溯，并在交付前检查验证证据。

开发者接入模型 API，可以从 **MaaS** 开始；希望 AI 在共享上下文的工作流中协助编码与办公，可以从 **AiWork** 开始。产品介绍见 [AiWork 官网](https://aiwork.dtagi.cn/home)。

**[体验 AiWork →](https://aiwork.dtagi.cn/home) · [下载 AiWork](https://aiwork.dtagi.cn/download)**
