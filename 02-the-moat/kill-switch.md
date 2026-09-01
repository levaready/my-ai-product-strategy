# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|--------------|------------|---------------|
| **Provider** | OpenAI Direct API calls | H | Freeze new OpenAI-specific development, identify the most business-critical calls, and select a secondary provider for emergency migration testing. |
| **Abstraction** | Limited Provider Abstraction, still relatively coupled to OpenAI-specific models, prompts, APIs, and structured outputs. | H | Create a basic internal AI service/interface that separates BluRok application logic from vendor-specific API calls. |
| **Routing** | No mature multi-model routing or automatic failover layer. | H | Add manual routing for the highest-volume and lowest-risk workloads so traffic can be moved between providers without changing the product UI. |
| **Eval** | BluRok-specific model evaluation exists conceptually but is not yet a mature automated benchmark covering cultivation reasoning, image analysis, recommendations, latency, cost, and output reliability. | M | Build a small critical-path evaluation set from real BluRok use cases and benchmark OpenAI against at least one alternative model before migration. |

## Portability Score
Partial

## If OpenAI doubles pricing tomorrow:
Stop nonessential high-token AI workloads and identify the API calls responsible for the largest percentage of model spending.

Preserve OpenAI for high-value tasks such as complex cultivation reasoning and move simpler workloads such as classification, summarization, formatting, and routine recommendations to lower-cost models.

Benchmark a secondary provider against BluRok's critical evaluation set.

Introduce usage limits, caching, prompt optimization, and model-tier routing to reduce token consumption immediately.

Calculate the impact on unit economics and determine whether pricing, usage limits, or product packaging need to change. 

## If OpenAI ships a competing product:
That accumulated operational intelligence becomes significantly harder for a foundation-model provider to reproduce because the value comes from BluRok's proprietary data and workflow history, not just access to a powerful model.
