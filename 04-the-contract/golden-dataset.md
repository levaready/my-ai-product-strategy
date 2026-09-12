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
Users can confirm, reject, correct, or mark an output as uncertain; select an alternative diagnosis; explain an override; attach supporting images or test results; and record the eventual outcome.

## Reliability Contract

| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | 92% weekly accuracy on the validated BluRok gold set | Weekly evaluation against labeled cultivation, image-diagnosis, recommendation, extraction, and profitability test cases. Results are segmented by crop, species, model, confidence level, and task type. Production corrections and confirmed outcomes supplement the gold-set evaluation. | Below 88% overall, below 90% for high-impact diagnoses, or a decline greater than three percentage points in any crop, region, or workflow segment |
| Hallucination rate | Below 1% | Weekly claim-level review of the gold set plus a risk-weighted sample of production responses. Claims are checked against retrieved sources, farm records, product labels, regulations, and approved SOPs. | 1% or higher, or any confidently fabricated safety, compliance, chemical-treatment, financial, or source claim |
| Latency (p95) | First response or token: Below 750 ms
Standard recommendation: Below 2 seconds
Image diagnosis or complex agent workflow: Below 5 seconds | Continuous monitoring through OpenTelemetry and Datadog, segmented by model, provider, feature, device, and region | Standard responses exceed 5 seconds or complex workflows exceed 10 seconds for 10 consecutive minutes |
| Drift velocity | Less than 0.5 percentage-point quality decline over four weeks | Compare the current rolling four-week gold-set score with the previous validated four-week baseline. Segment results to prevent strong performance in common cases from hiding degradation in smaller agricultural categories. | Greater than 1 percentage point over four weeks, or greater than three percentage points within a specific crop, disease, region, season, or user segment |

## HITL Architecture
Trigger — when does a human enter?
Confidence falls below 50%
Confidence is between 50% and 90% for a high-consequence decision
AI evidence conflicts with farm records, sensor data, or approved SOPs
The user disputes or overrides the output
The recommendation involves pesticides, worker safety, compliance, destructive crop action, or significant financial exposure
The case involves an unfamiliar crop, disease, region, or operating condition
Hallucination or accuracy thresholds are breached

Reviewer — who reviews?
Farm supervisor or designated cultivation manager for operation-specific decisions
BluRok cultivation-quality lead for model-output validation
Approved agronomist, plant pathologist, mycologist, compliance specialist, or financial reviewer for specialized escalations

Feedback loop: Yes. Corrections enter a structured review queue and capture the original output, confidence, evidence, reviewer decision, action taken, and eventual outcome. Validated corrections are added to the farm’s memory and the appropriate gold-set segment.
