# Data Flywheel Map

> Score each loop 1-5. Your weakest loop is where competitors attack first.
> The four loops below are the M2 starting point - adapt if your product has 2 or 6 loops instead of 4.

## Flywheel Loops

| Loop | What It Measures | Score 1 | Score 5 | Score |
|------|------------------|---------|---------|-------|
| **Correction** | Do users fix AI outputs? Is that signal captured and reused? | No capture | Automated retraining | __/5 |
| **Preference** | Does the product learn individual / team preferences over time? | Stateless | Deep personalization | __/5 |
| **Domain Context** | Does usage in one area improve quality in adjacent areas? | Siloed | Cross-domain transfer | __/5 |
| **Network** | Does each new user / team make the product better for everyone? | Isolated | Strong network effects | __/5 |

### Correction Loop - 2/5
**What you capture today:** User inputs, cultivation records, images, environmental information, genetics, outcomes, and user feedback on recommendations. However, explicit corrections to AI-generated diagnoses or recommendations are not yet systematically captured as structured learning signals.
**How it compounds:** When users correct a plant diagnosis, quality assessment, recommendation, cultivar identification, or predicted outcome, BluRok can associate that correction with the underlying images, environmental conditions, genetics, and eventual results. Over time, these corrections can improve future recommendations for both that operation and similar operations.

### Preference Loop - 3/5
**What you capture today:** Grow style, genetics/cultivars, environmental conditions, production methods, historical results, operational goals, and eventually customer preferences and purchasing behavior.
**How it compounds:** Each grow or production cycle gives BluRok additional information about what works for that specific operation. Automated sensor data can accelerate the loop by continuously adding environmental and operational context rather than relying only on manual entries.

### Domain Context Loop - 3/5
**What you capture today:** Cultivation data, environmental conditions, genetics, plant imagery, yield, quality, operational practices, and eventually financial and customer demand data.
**How it compounds:** Data collected for one problem can improve decisions elsewhere in the platform. Environmental and cultivation data can improve disease detection; disease history can improve risk alerts; yield and quality data can improve production planning; production costs and market demand can improve profitability recommendations.

### Network Loop - 2/5
**What you capture today:** Individual producer cultivation data, genetics, environmental conditions, outcomes, images, quality measurements, and eventually anonymized market and consumer behavior data.
**How it compounds:** As more farms use BluRok, the platform can identify patterns that would be impossible to discover from one operation alone. For example, BluRok could determine how the same cultivar performs across different climates, facilities, cultivation systems, regions, and production methods.

**Total Flywheel Score: 10/20**
**Weakest Loop:** Correction and Network
**Fix for weakest loop:** Build structured feedback directly into every major AI interaction so users can confirm, reject, or correct recommendations and record the eventual outcome. At the same time, create a privacy-safe benchmarking layer that converts anonymized producer results into collective intelligence, allowing every additional farm, grow cycle, image, sensor reading, quality result, and market outcome to improve recommendations across the BluRok network.

---

## Encroachment Threat Assessment

### 1. Platform Encroachment
**Attacker:** OpenAI
**Vector:** AI recommendations, image analysis, cultivation Q&A, decision support, workflow automation
**Time-to-threat:** 2–4 years
**% of value at risk:** 70%

### 2. Vertical Competitor
**Attacker:** GrowerOS and other cultivation-management platforms
**Vector:** Existing growers, cultivation workflows, operational records, financial data, compliance integrations
**Time-to-threat:** Current
**% of value at risk:** 35%

### 3. Adjacent Expansion
**Attacker:** John Deere, LeafLink, farm-management software providers, agriculture-input platforms, marketplaces, and seed-to-sale platforms
**Vector:** Existing farmer/producer relationships, equipment data, market transactions, financial data, compliance data, and distribution
**Time-to-threat:** 1–3 years
**% of value at risk:** 60%

---

## 90-Day Encroachment Plan

*Your partner played the Big Tech attacker. What was their plan to kill you?*

**Attacker:** OpenAI
**Attack vector (target the weakest loop):**
**Weeks 1-4 - what they ship:**
**Weeks 5-8 - how they poach users:**
**Weeks 9-12 - why users don't come back:**
**Your defense:** 
Close the Correction Loop
Allow farmers to approve, reject, modify, or correct every significant recommendation and capture why.

Capture Outcomes
Record whether the farmer followed the recommendation and what happened afterward.

Build Farm Memory
Create a persistent model of each operation's genetics, environment, cultivation methods, costs, outcomes, preferences, and historical performance.

Create Network Intelligence
Aggregate anonymized results across producers so every additional grow improves benchmarking and recommendations for the broader network.
