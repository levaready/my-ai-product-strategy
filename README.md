# My AI Product Strategy

A living, version-controlled strategy for transforming BluRok Vision from an agricultural AI application into a defensible operating-intelligence platform.
---

## Strategy at a Glance

| Component          | Module | Status | Key Artifact         |
| ------------------ | :----: | :----: | -------------------- |
| **The Bet**        |   M1   |   [x]  | `01-the-bet/`        |
| **The Moat**       |   M2   |   [x]  | `02-the-moat/`       |
| **The Margin**     |   M3   |   [x]  | `03-the-margin/`     |
| **The Contract**   |   M4   |   [x]  | `04-the-contract/`   |
| **The Guardrails** |   M5   |   [x]  | `05-the-guardrails/` |
| **The Pitch**      |   M6   |   [x]  | `06-the-pitch/`      |

---

## The Bet (M1)

**What we're building, for whom, why now.**

- **Product:** BluRok Vision—a web-based agricultural operating-intelligence platform that learns how each producer’s operation generates profit, then uses that context to improve efficiency, yield, quality, and decision-making.
- **AI Value Archetype:**  Decision-intelligence copilot combining recommendations, computer vision, evidence retrieval, and human-controlled workflow support.
- **Vulnerability Scores:** Moat 3.5/5 · Data 3/5 · Platform Exposure 4/5
- **Top Risk:** Mistaking replaceable AI features for a moat before BluRok captures enough proprietary operational and outcome data.
- **Confidence:** M
- **Prototype:** [[BluRok Vision](https://grower-os.replit.app/)]
- **Kill Criteria:** Stop or materially pivot if pilot users do not consistently use BluRok for operational decisions, it fails to improve yield, quality, labor efficiency, decision speed, or profitability, or customers will not pay enough to support sustainable margins after three to six months of real-world use.

→ Details: [`01-the-bet/`](01-the-bet/)

---

## The Moat (M2)

**Why this won't get copied in 6 months.**

- **Data Flywheel Score:** 10/20
- **Weakest Loop:** Recursive Learning/Correction—the connection between recommendations, producer actions, corrections, and verified outcomes.
- **Competitive Position:** Competes on workflow depth × proprietary outcome intelligence. BluRok is currently moderate on workflow depth and early on proprietary data, with a target position of high depth and high outcome intelligence.
- **Encroachment Defense:** Farm-specific memory, closed recommendation-to-outcome learning, cross-domain profitability intelligence, privacy-safe benchmarking, human-controlled workflows, and provider abstraction.
- **Vendor Portability:** Partial

→ Details: [`02-the-moat/`](02-the-moat/)

---

## The Margin (M3)
Will this make money or bleed it?
Gross Margin—traditional SaaS baseline: 87.8%
Gross Margin—AI-adjusted: 81.1%
Pricing Model: Hybrid penetration pricing—$39 monthly base + $1 per completed production decision, targeting approximately $49 ARPU
Cascading Strategy: Deterministic software first, followed by 32% small-model, 46% mid-tier, and 22% frontier-model traffic
Break-even: Not yet calculable without validated fixed monthly operating costs. Current estimated contribution is $39.74 per user/month, so:
$$ \text{Break-even users} = \frac{\text{Monthly fixed operating costs}}{\$39.74} $$
Operating guardrails:
AI inference COGS ≤ 10% of revenue
Frontier traffic ≤ 25%
Gross margin ≥ 75%
**Will this make money or bleed it?**

- **Gross Margin (current):** 87.8%
- **Gross Margin (AI-adjusted):** 81.1%
- **Pricing Model:** Hybrid penetration pricing—$39 monthly base + $1 per completed production decision, targeting approximately $49 ARPU
- **Cascading Strategy:** Deterministic software first, followed by 32% small-model, 46% mid-tier, and 22% frontier-model traffic
- **Break-even at:** Not yet calculable without validated fixed monthly operating costs. Current estimated contribution is $39.74 per user/month, so:
$$ \text{Break-even users} = \frac{\text{Monthly fixed operating costs}}{\$39.74} $$
Operating guardrails:
AI inference COGS ≤ 10% of revenue
Frontier traffic ≤ 25%
Gross margin ≥ 75%

→ Details: [`03-the-margin/`](03-the-margin/)

---

## The Contract (M4)

**Why users will trust a probabilistic system.**

- **Reliability Target:** 2% weekly gold-set accuracy, hallucinations below 1%, standard-response p95 below 2 seconds, and complex-workflow p95 below 5 seconds
- **Golden Dataset:** 12 rows, 5 adversarial
- **Confidence UX:** High Confidence above 90%, Moderate Confidence from 50–90%, and Insufficient Evidence below 50%. Exact percentages appear only after calibration.
- **HITL Architecture:** Low-confidence, disputed, conflicting, regulated, safety-related, destructive, or financially consequential decisions enter a structured human-review queue. Validated corrections feed farm memory and the evaluation dataset.
- **Failure Mode Coverage:** High for the initial scope, covering incomplete images, missing information, conflicting measurements, sensor errors, unsupported financial conclusions, model-routing errors, and weak personalization. Provider outages, prompt injection, privacy attacks, multilingual cases, and additional crops still require expanded testing.

→ Details: [`04-the-contract/`](04-the-contract/)

---

## The Guardrails (M5)

**What breaks when this scales — and what compounds.**

- **Compounding System:** Recommendations generate decisions and actions; actions produce biological, quality, operational, and financial outcomes; validated outcomes improve farm memory, cross-domain recommendations, evaluation cases, and eventually privacy-safe network benchmarks.
- **Governance Posture:** Advisory copilot with evidence disclosure, tiered confidence, measurable escalation triggers, immutable decision logs, and human approval for consequential actions.
- **Shadow AI Status:** 8 workaround groups found, 7 retained after triage
- **Agent Boundaries:** Agents may observe, retrieve, summarize, calculate, rank, recommend, and draft. They may not automatically apply chemicals, control equipment, destroy crops, submit compliance reports, transact, make employment decisions, or expose customer data.
- **Regulatory Exposure:** Limited under the current EU AI Act framing, provided BluRok remains advisory. Applicable controls may include AI transparency, GDPR/privacy requirements, FTC consumer-protection expectations, EPA/FIFRA pesticide-label restrictions, and state agriculture, food-safety, and cannabis rules.

→ Details: [`05-the-guardrails/`](05-the-guardrails/)

---

## The Pitch (M6)

**How you get this funded, shipped, and adopted.**

- **Horizon 1 (Now):** Close the recursive learning loop; launch confidence, evidence, approval, and human-review controls; add model abstraction, evaluation, cost monitoring, and rollback.
- **Horizon 2 (Next):** Connect environmental, cultivation, yield, quality, labor, cost, sales, and market data; launch profitability intelligence and priority integrations; test hybrid pricing.
- **Horizon 3 (Bet):** Build privacy-safe network intelligence, comparable-producer benchmarking, producer-to-market feedback, and approved workflow orchestration.
- **Board Narrative:** BluRok Vision will become the agricultural operating-intelligence system that learns which decisions produce the best biological, operational, quality, and financial outcomes for each farm.
- **Key Metric:** Verified Outcome Rate—the percentage of high-impact recommendations connected to a confirmed action and measurable outcome. Initial target: at least 60%.
- **Supporting Horizon 1 metric:** At least 80% of high-impact recommendations receive an accept, modify, reject, or escalate response.

→ Details: [`06-the-pitch/`](06-the-pitch/)
