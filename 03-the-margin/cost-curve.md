# Cost Curve & Pricing Strategy

## Cost Model

| Cost Category | Per-User/Month | Notes |
|--------------|----------------|-------|
| Inference (primary model) | $2.09 | Sol model handles approximately 22% of requests, including complex diagnosis, profitability decisions, and strategic reviews. |
| Inference (cascading/triage) | $1.17 | Luna and Terra handle approximately 78% of requests, including classification, summaries, alerts, SOPs, and bounded recommendations. |
| Infrastructure | $2.50 | Application hosting, databases, monitoring, integrations, and background processing. |
| Data/storage | $1.50 | Images, grow records, sensor history, documents, backups, and retrieval infrastructure. |
| Human-in-the-loop | $2.00 | Estimated cost for sampled quality reviews, escalations, and correction validation while not manual reviewing of every request. |
| **Total AI COGS** | $9.26 | |

## Cascading Strategy
**Triage model:** GPT-5.6 Luna
**Default reasoning model:** GPT-5.6 Terra
**Frontier model:** GPT-5.6 Sol
**Routing rule:** Use deterministic rules, databases, retrieval, and statistical processing first. Route remaining requests to the least expensive model that meets the task’s quality and risk threshold. Escalate to Sol only when the request involves high uncertainty, material crop or financial consequences, complex multimodal diagnosis, or cross-domain strategic reasoning.
**Expected cascade ratio:**. 78% non-frontier / 22% frontier
Luna: 32%
Terra: 46%
Sol: 22%

## Pricing Model

**Current pricing:** Pre-launch; no validated paid pricing
**Proposed AI pricing:** $39/month base fee + $1 per completed production decision
**Model:** hybrid

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x | Gross margin falls from 81.1% to 67.8% at current revenue and usage. | Route more work to Luna/Terra, strengthen caching and deterministic processing, reduce unnecessary context, and increase pricing if margin remains below 75%. |
| Heaviest segment doubles | Assuming 20 decisions, revenue rises to approximately $59 while AI usage doubles; estimated margin remains around 78.8%. | Preserve metered overages, introduce higher-volume farm plans, and offer prepaid decision bundles without unlimited frontier usage. |
| Model provider raises prices 50% | AI COGS rises from $3.26 to $4.89; estimated gross margin declines from 81.1% to 77.8%. | Use the provider abstraction layer to shift eligible workloads, renegotiate committed-volume pricing, and maintain OpenAI only for tasks where it materially outperforms alternatives. |

## Board One-Pager
Narrative: AI inference reduces gross margin because COGS rises with usage. The tradeoff is only worthwhile if BluRok’s recommendations produce stronger retention, measurable farm outcomes, higher willingness to pay, or expansion revenue from additional decisions, users, sites, sensors, and analytics.

**Before (traditional SaaS):** Revenue: $49/seat × 1 seat = $49/month
COGS: $6.00/user/month (mostly fixed)
Gross margin: 87.8%
**After (AI-enabled):** Revenue: $39 base + $1 × 10 completed outcomes = $49/month
COGS: $9.26/user/month (variable)
Gross margin: 81.1%
**Net margin shift:** Average margin: −6.7 percentage points
Average gross profit: −$3.26/user/month
