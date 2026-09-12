# Compounding System Design

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Farm records, images, sensor data, AI recommendations, user corrections, actions taken, and verified biological and financial outcomes. | Better farm-specific diagnoses, confidence estimates, recommendations, and predictions based on what previously worked for that operation. | Y | Broken BluRok can collect parts of the input, but the full loop is not closed until every recommendation is connected to the user’s action, eventual outcome, and validated correction.|
| Cross-Domain Transfer | Genetics, environmental conditions, plant health, cultivation practices, labor, yield, quality, production costs, sales, and customer demand. | Recommendations that connect operational decisions to biological and financial results, including disease-risk alerts, quality predictions, and what-to-produce-next rankings. | Y | Broken The domains are defined, but the shared data model, cross-domain joins, and validated relationships are not yet mature enough to consistently improve adjacent workflows. |
| Network Intelligence | Privacy-safe, anonymized outcomes from multiple producers, production cycles, crops, facilities, climates, interventions, and markets.
 | Peer benchmarks, regional trends, stronger confidence calibration, transferable best practices, and better recommendations for similar operations.
 | Y | Missing BluRok does not yet have enough active producers, standardized outcome data, or consented aggregation to create a genuine network effect. |
| Producer-to-Market Feedback | Product attributes, cultivar and production history, quality measurements, prices, customer preferences, purchases, repeat purchases, and sell-through. | Better consumer recommendations and better producer decisions about what to grow, how to position it, and which product characteristics generate the strongest margins. | Y | Missing This could become BluRok’s strongest differentiator, but it does not exist until producer records are reliably connected to downstream product performance and consumer behavior. |

**Broken loop identified by partner:**
Recursive Learning

BluRok is leaking its most valuable signal: the connection between what the AI recommended, what the producer did, and what happened afterward. Without that connection, every cultivation cycle generates activity but not defensible learning.

**Fix plan:**
Define one structured event chain:
Recommendation → User response → Action taken → Outcome → Correction

Add four controls to every material recommendation:
  Accept
  Modify
  Reject
  Need expert review
Require a reason when an output is modified or rejected.
Schedule outcome checks based on the decision type—for example, 24 hours after an environmental intervention or at harvest for a production recommendation.
Connect every event using stable farm, facility, room, crop, batch, cultivar, and recommendation IDs.
Send low-confidence, disputed, or high-consequence cases into the human-review queue.
Review corrections and confirmed outcomes weekly, then add validated cases to the farm memory and evaluation gold set.

## Context Connectivity
How knowledge flows across teams and domains: Farm records, sensor data, images, SOPs, research evidence, labor, costs, quality results, sales, and customer signals enter a shared evidence layer. BluRok connects that information to a specific operation and production cycle, generates a recommendation, records the producer’s decision, measures the outcome, and returns the validated learning to farm memory, model evaluation, future recommendations, and privacy-safe benchmarking.

Where knowledge silos: Sensor platforms, spreadsheets, photos, compliance systems, inventory, and financial records use different identifiers and formats.
Recommendations are not consistently linked to actions and outcomes.
User corrections remain unstructured or trapped in conversations.
Cultivation, quality, labor, cost, sales, and customer data are analyzed separately.
Producer and consumer datasets are not connected at the product or batch level.
Units, crop terminology, cultivar names, timestamps, and production stages are not standardized.
Data ownership, consent, and anonymization rules can prevent network learning.
Research evidence may inform an answer without being connected to measured farm outcomes.

## Governance Policy

**Scope:**
This policy applies to BluRok Vision’s AI-generated:
Crop-health and contamination assessments
Cultivation and environmental recommendations
Image-based plant, mushroom, pest, disease, and quality analysis
Yield, quality, cost, and profitability forecasts
“What should I produce next?” recommendations
Alerts, summaries, SOP drafts, and employee task drafts
Consumer product recommendations
Model routing, confidence scoring, corrections, and human review
Use of farm, sensor, image, financial, employee, and consumer data
Agents that retrieve evidence, draft actions, or monitor outcomes
What it excludes
Autonomous control of irrigation, fertigation, HVAC, lighting, machinery, or environmental equipment
Automatic pesticide or chemical application
Legal or regulatory certification
Medical or therapeutic advice
Hiring, firing, discipline, compensation, or worker-performance decisions
Automatic purchases, sales, payments, crop destruction, recalls, or regulatory submissions
Rokko’s internal product-management workflows, which require a separate internal governance policy

**Autonomy boundaries:**
| Decision                                                                                   | Boundary              | Rule                                                                                                                                |
| ------------------------------------------------------------------------------------------ | --------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Summarize journals, sensor trends, and existing records                                    | 🟢 **Auto**           | May summarize source data but must preserve conflicts, missing values, units, and provenance.                                       |
| Detect threshold violations and generate alerts                                            | 🟢 **Auto**           | Detection must be rules-based where possible. AI may explain the alert but cannot execute corrective actions.                       |
| Draft recommendations, SOPs, schedules, or employee tasks                                  | 🟢 **Auto**           | Must be labeled as AI-generated drafts with confidence, evidence, and assumptions.                                                  |
| Change environmental setpoints, irrigation, fertigation, lighting, or production schedules | 🟡 **Human approval** | Requires approval from the farm manager or authorized cultivation lead, even at high confidence.                                    |
| Approve a crop-health diagnosis or treatment plan                                          | 🟡 **Human approval** | Requires review when treatment could affect crop safety, compliance, marketability, or worker exposure.                             |
| Make production or profitability decisions                                                 | 🟡 **Human approval** | AI may rank options and model scenarios; an authorized producer approves the final decision.                                        |
| Recommend a pesticide or plant-growth regulator                                            | 🟡 **Human approval** | Must verify crop, jurisdiction, registration status, label directions, application restrictions, PPE, and pre-harvest requirements. |
| Apply chemicals, operate machinery, or control equipment                                   | 🔴 **Never auto**     | BluRok remains advisory unless a separately certified control system and safety policy are approved.                                |
| Destroy, quarantine, recall, or release a crop or product                                  | 🔴 **Never auto**     | Requires an authorized human and documented evidence.                                                                               |
| File compliance reports or certify regulatory accuracy                                     | 🔴 **Never auto**     | AI may prepare a draft, but a licensed or authorized person must verify and submit it.                                              |
| Make employment, disciplinary, credit, insurance, or legal decisions about a person        | 🔴 **Never auto**     | Outside BluRok’s approved purpose.                                                                                                  |
| Share identifiable farm, employee, or consumer data externally                             | 🔴 **Never auto**     | Requires authorization, a valid legal basis, and applicable consent or contract controls.                                           |

**Escalation triggers:**
A case routes to a human every time when:
Confidence is below 50% for any material recommendation.
Confidence is below 90% for a safety-, compliance-, chemical-, crop-destruction-, or financially consequential decision.
The projected impact exceeds $500 or 5% of the affected batch’s estimated value, whichever is lower, until each customer sets an approved threshold.
Two or more sensors conflict beyond their documented tolerance, or a reading falls outside a physically plausible range.
The AI cannot identify an authoritative source, approved SOP, product label, or farm record supporting a regulated recommendation.
A pesticide is not confirmed as registered for the crop and jurisdiction or the proposed use conflicts with its label.
The user rejects, materially modifies, or disputes the same recommendation twice.
A recommendation conflicts with an approved SOP, laboratory result, compliance record, or authorized manager instruction.
The request involves crop destruction, recall, quarantine, employee safety, regulatory submission, or suspected contamination.
Personally identifiable or sensitive employee or consumer information appears in a workflow that does not require it.
Weekly accuracy falls below 88%, high-impact diagnostic accuracy falls below 90%, or hallucination rate reaches 1%.
A model, retrieval, or provider failure prevents BluRok from showing its supporting evidence or confidence.
The crop, disease, cultivation method, region, or operating condition is outside the validated evaluation set.

**Audit cadence:**
| Cadence       | Audit                                                                                                              | Named Owner                           |
| ------------- | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------- |
| **Real-time** | Latency, provider failures, missing citations, safety triggers, unauthorized tool calls, and high-risk escalations | **ML Operations Lead**                |
| **Daily**     | Human-review queue, unresolved high-impact cases, user disputes, and critical incidents                            | **Product Operations Manager**        |
| **Weekly**    | Gold-set accuracy, hallucinations, confidence calibration, corrections, routing performance, and subgroup failures | **AI Quality Lead**                   |
| **Monthly**   | Access logs, consent, data retention, deletion requests, vendor use, security exceptions, and privacy incidents    | **Data Protection and Security Lead** |
| **Quarterly** | Regulatory classification, autonomy boundaries, impact assessment, model/vendor changes, and policy approval       | **Chief Product Officer**             |

**Regulatory exposure (EU AI Act / other):**
Regimes that apply or may apply

EU AI Act when BluRok is offered or used in the EU. Interactive and generative systems can carry transparency obligations, while workplace or employment decision systems may trigger substantially higher requirements. Article 50 transparency obligations have applied since August 2, 2026. European Commission AI Act overview, Article 50 transparency guidance
GDPR when BluRok processes personal data involving people in the EU. Relevant principles include lawful and transparent processing, purpose limitation, data minimization, accuracy, storage limitation, security, and accountability. European Commission GDPR principles
FTC Act and U.S. state privacy laws for truthful AI claims, privacy promises, data security, and consumer protection. The FTC has specifically warned that AI companies must honor representations about how customer data is used. FTC guidance
FIFRA and EPA pesticide-label requirements. It is generally unlawful to use a registered pesticide inconsistently with its labeling. EPA pesticide-label guidance
State agriculture, pesticide, food-safety, and cannabis regulations in every operating jurisdiction. In New Mexico, the Cannabis Control Division regulates commercial cannabis operations, and NMDA maintains the applicable cannabis pesticide-registration information. New Mexico Cannabis Control Division, NMDA cannabis pesticide list
NIST AI Risk Management Framework as the voluntary governance framework for mapping, measuring, managing, and governing AI risk. NIST AI RMF

That assessment depends on BluRok remaining a transparent advisory and decision-support product. It must be reassessed before adding autonomous equipment control, worker evaluation, employment decisions, credit or insurance decisions, biometric monitoring, or safety-critical infrastructure functions.

Controls required for launch

Disclose clearly when users are interacting with AI.
Label AI-generated recommendations, drafts, images, and reports.
Display confidence, supporting evidence, assumptions, and material limitations.
Maintain human approval for consequential decisions regardless of confidence.
Keep immutable logs of inputs, model/version, retrieved evidence, output, approval, correction, and outcome.
Apply role-based access, encryption, data minimization, retention schedules, and deletion/export workflows.
Obtain explicit permission before using customer data for shared-model training or network benchmarking.
Separate farm-specific memory from anonymized network intelligence.
Maintain crop-, region-, and workflow-specific evaluation sets.
Verify pesticide recommendations against current product labels and jurisdictional registration data.
Conduct privacy and AI-impact assessments before entering new jurisdictions or materially expanding autonomy.
Maintain provider abstraction, tested rollback, and manual operating procedures.

Current-state warning: These are required policy controls; they should not be described as fully “in place” until engineering implementation, ownership, testing, and audit evidence exist.

## Agent Topology
Observation Agent: Can ingest images, sensor data, and records and identify anomalies. Cannot alter equipment or declare a final diagnosis. Approval owner: Farm Manager.
Diagnosis Agent: Can rank possible causes, display confidence, and request additional evidence. Cannot authorize treatment, pesticide use, crop release, or destruction. Approval owner: Cultivation Lead.
Workflow Agent: Can draft SOPs, schedules, alerts, and employee tasks. Cannot assign regulated work, change approved SOPs, or execute equipment commands. Approval owner: Operations Manager.
Profitability Agent: Can model scenarios and rank production choices. Cannot make purchases, sales, payments, or binding production commitments. Approval owner: Business Owner or Finance Lead.
Consumer Recommendation Agent: Can rank products using disclosed preferences and product data. Cannot provide medical advice or guarantee effects, safety, or outcomes. Approval owner: Product Owner, with user control over preferences.
Evidence Agent: Can retrieve and summarize approved sources. Cannot invent citations, silently replace contradictory evidence, or treat weak sources as verified facts. Approval owner: AI Quality Lead.

## Shadow AI Audit
| Tool                                                                 | Owner                       | Risk Level | Decision |
| -------------------------------------------------------------------- | --------------------------- | :--------: | -------- |
| ChatGPT, Gemini, and Google Lens for crop-image diagnosis            | Cultivation Lead            |      H     | govern   |
| Spreadsheets plus ChatGPT for production and profitability analysis  | Farm Manager / Finance Lead |      H     | govern   |
| ChatGPT or Claude for SOPs, sanitation procedures, and crop plans    | Operations Manager          |      H     | govern   |
| GrowerOS, Metrc, LeafLink, QuickBooks, POS, and spreadsheet workflow | Compliance / Finance Lead   |      H     | govern   |
| Reddit, Facebook, Discord, consultants, and peer second opinions     | Cultivation Lead            |      M     | govern   |
| Zapier or Make for sensor and operational alerts                     | Operations / Technical Lead |      M     | govern   |
| Generic AI for unverified pesticide or treatment recommendations     | Cultivation Lead            |      H     | kill     |
| Generic AI for marketing copy and product descriptions               | Marketing Lead              |      L     | keep     |

Total tools/workaround groups found: 8
Tools after triage: 7
Estimated hidden spend: $50–$100/month normally; $200+ during problem months
“Kill” applies specifically to using unverified generic AI for pesticide or treatment decisions—not necessarily removing the underlying AI tool from every approved use.
