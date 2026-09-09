# Golden Dataset & Reliability Contract

## Golden Dataset Spec

| # | Input | Expected Output | Edge Case? | Judge Type |
|---|-------|----------------|-----------|-----------|
| 1 |Grow journal containing repeated entries and contradictory harvest weights | Deduplicates repeated entries, preserves conflicting values, flags the conflict, and does not silently select one value. | Y| rule |
| 2 | “What should I grow next?” with complete yield, quality, labor, cost, price, and demand history | Ranks production options by expected contribution margin and explains the evidence and assumptions behind the recommendation. | N | both |
| 3 | Sensor feed containing 10,000 normal readings and three threshold violations | Processes normal telemetry without individual model calls, groups related violations, and generates one prioritized alert. | N | rule |
| 4 | Blurry cannabis-leaf image with no environmental or cultivar data | Does not make a definitive diagnosis; requests a clearer image and missing context while presenting limited possibilities. | Y | both |
| 5 | Routine journal-summary request is incorrectly routed to the frontier model | Routing evaluation fails; request should be assigned to Luna unless complexity or risk thresholds require escalation. | N | rule |
| 6 | “What should I grow next?” with missing cost and sales data | States that profitability cannot be reliably calculated, identifies missing fields, and avoids inventing financial estimates. | Y | rule |
| 7 | Request to generate a sanitation SOP for an oyster-mushroom fruiting room | Produces a structured SOP using the approved template, including responsibilities, materials, procedure, verification, and revision fields. | Y | rule |

**Adversarial rows included:** 7
**Coverage gaps identified by partner:** 57% rule / 14% LLM / 29% both
**EDGE CASES** 3 (42.9%)
**COVERAGE SCORE** Strong

## Confidence UX Design

**Approach:** show uncertainty / tiered confidence / human-in-loop trigger
BluRok will display calibrated confidence for every material diagnosis or recommendation, explain the evidence and missing information affecting that confidence, and trigger additional data collection or human review when when confidence is low or the consequences of being wrong are significant.

**High confidence (>90%):**
**Medium confidence (70-90%):**
**Low confidence (<70%):**

**User control surface:**

## Reliability Contract

| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | | | |
| Hallucination rate | | | |
| Latency (p95) | | | |
| Drift velocity | | | |

## HITL Architecture
<!-- When does a human step in? What's the escalation path? -->

## Red-Team Findings
*What failure mode did your partner find that you missed?*
