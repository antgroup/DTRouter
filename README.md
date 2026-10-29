# DT-Router

English | [简体中文](README.zh-CN.md)

**Quality-aware LLM routing, with cost in mind.**

DTRouter is a proprietary LLM routing method developed by **Ant Digital Technologies (蚂蚁数科)**.

Ant Digital offers two products for model services and task delivery: **[DTMaaS](https://maas.antdigital.com/)** gives developers unified API access to multiple models for building AI applications; **[AiWork](https://aiwork.dtagi.cn/home)** brings coding and office work into a workflow with shared context, autonomous planning, execution, and verification.

**DTRouter explores the model-selection problem relevant to both model services and agent workflows:** choosing a suitable model for each request's capability requirements and cost constraints, while balancing answer quality and inference spending. This repository presents that routing work and provides entry points to both products.

**[Explore MaaS](https://maas.antdigital.com/) · [Try AiWork](https://aiwork.dtagi.cn/home) · [MaaS documentation](https://maas.antdigital.com/docs/intro)**

## 1. Why model routing?

Different models offer different strengths, response times, and prices. Choosing a model for each request gives developers another way to manage the quality and cost of an AI application.

DTRouter explores this trade-off through request-level model selection. Its goal is to use model capabilities where they add value while keeping inference spending in view.

## 2. Build with Ant Digital MaaS

Interested in using multiple models in your applications? Explore **DTMaaS**, Ant Digital's enterprise Model-as-a-Service platform.

MaaS provides a unified API for accessing supported models, including LingDT, Qwen, and DeepSeek.

| Capability | What it means for developers |
| --- | --- |
| Unified model access | Use OpenAI-compatible interfaces and switch supported models through request parameters. |
| Service scheduling and failover | Use the platform's scheduling and node failover mechanisms for model serving. |
| Inference cost optimization | Benefit from the platform's caching and routing optimizations. |
| Unified billing | Manage model consumption through a common service platform. |

See the [platform introduction](https://maas.antdigital.com/docs/intro) and [platform advantages](https://maas.antdigital.com/docs/intro/advantages) for product details.

### 2.1 Try MaaS

1. Visit the [MaaS platform](https://maas.antdigital.com/) and obtain an API key.
2. Follow the [quick access guide](https://maas.antdigital.com/docs/quick-access) and choose an available model from the [supported models](https://maas.antdigital.com/docs/intro/supported-models).
3. Send your first request through the OpenAI-compatible endpoint.

The example below shows how to call a specific model through MaaS.

```bash
curl https://maas-api.antdigital.com/v1/chat/completions \
  -H "Authorization: Bearer ${MAAS_API_KEY}" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "qwen3.6-plus",
    "messages": [
      {"role": "user", "content": "Explain the role of model routing in AI applications."}
    ]
  }'
```

For model access and product integration, start with the [MaaS documentation](https://maas.antdigital.com/docs/intro).

## 3. AiWork: coding and office work together

**Agent Team is Ready.**

[AiWork](https://aiwork.dtagi.cn/home) brings coding and office work into one workflow. Both modes share context, with autonomous planning, execution, and verification to move tasks toward deliverables you can inspect.

| Mode | What AiWork helps you do |
| --- | --- |
| Coding | Develop maintainable code with attention to architecture and engineering quality. Check progress against the goal, diagnose issues, repair and revalidate, with reviews covering the plan, code, and overall result. |
| Office work | Read, convert, and summarize documents; research and analyze online data; operate your computer and web pages; connect tools through connectors and MCP; use expert skills; and schedule unattended tasks. |

**Stay involved throughout delivery.** Users can approve, reject, or take over work while it runs. Outputs are traceable, and delivery is checked against verification evidence.

Use **MaaS** for model API access, and explore **AiWork** for coding and office tasks with shared context. See the [AiWork homepage](https://aiwork.dtagi.cn/home) for the product overview.

**[Explore AiWork →](https://aiwork.dtagi.cn/home) · [Download AiWork](https://aiwork.dtagi.cn/download)**
