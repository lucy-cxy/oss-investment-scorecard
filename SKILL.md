---
name: oss-investment-scorecard
description: >
  Evaluate whether an open source project / company is investable by a USD-denominated VC fund in the current AI cycle.
  ALWAYS use this skill when the user asks any of the following:
  - "evaluate [project] for investment"
  - "can we invest in [project]"
  - "score this open source company"
  - "投资评估 [项目]"
  - "这个开源项目值得投吗"
  - "给 [公司] 打分"
  - Any request to assess, rate, or rank an open source startup's investability
  - Any comparison of two or more open source companies from an investment perspective
  The skill produces a structured 5-dimension weighted scorecard (max 10 pts), a pass/recommend/watch verdict, and an IC-ready one-paragraph thesis. It also flags one-vote-veto conditions that cause an immediate Pass regardless of total score.
---

# Open Source Project Investment Scorecard (V1.2)

## Purpose

Produce a rigorous, consistent, reusable investment evaluation for any open source project/company being considered by a USD VC fund — specifically calibrated for the **AI technology acceleration cycle (2023-onwards)**.

Built from: Bessemer Venture Partners Data 3.0 Roadmap, Oxx VC, Basis Set Ventures, Linux Foundation / COSSA, Unusual VC, Matrix VC, and two live case studies (Eigent.AI / CAMEL-AI and Datastrato / Apache Gravitino).

---

## Step 1 — Pre-Evaluation Fact Sheet & Macro Gate

### 1.1 Pre-Evaluation Fact Sheet
Before scoring, perform a web search to gather the following 7 items. Each item MUST include a source URL or be marked as "Searched, not found".

1. **GitHub Metrics:** Stars, Monthly Active Contributors (last 30d), External Contributor %, Dependent Repositories.
2. **Team Background:** Founders' prior OSS contributions, PMC/Committer status, prior infrastructure company experience.
3. **Funding History:** Total raised, last round valuation, lead investors.
4. **Commercial Traction:** Publicly mentioned ARR, customer logos, pricing model.
5. **Technical Architecture:** Core innovation level (L1-L4), key benchmarks (e.g., SOTA claims).
6. **Global Presence:** Documentation language, international contributor %, US customer presence.
7. **Competitive Benchmarking:** Identify 2-3 closest rivals; note their funding, stars, and key distribution partners (e.g., AWS/Azure).

### 1.2 Macro Gate (Non-Scoring Pre-Check)
Answer these three binary questions. If any answer is NO, stop and recommend Pass.

1. **Is the sub-sector still in its window-of-opportunity phase?**
   - Yes if: no single open-source project has monopolised the niche yet, OR the target IS that emerging monopolist.
   - No if: a dominant closed-source or open-source player already owns >60% mindshare AND the target has no credible differentiation.

2. **Does open-source mode confer structural advantage here?**
   - Yes if: vendor-neutral governance, community data flywheel, standards control, or ecosystem lock-in applies.
   - No if: the project is essentially a wrapper / prompt-engineering layer with no community moat.

3. **Is the AI-cycle value premium applicable?**
   - Higher than cloud-era because: the project sits on a structural chokepoint in the AI stack.
   - If purely a cloud-era Open Core play with no AI-cycle differentiation, note this as a risk factor (not automatic veto).

**Handling "Not Found" items:**
"Not Found" does NOT mean "Does not exist". If data is missing:
- Look for **indirect signals** (e.g., SOC2 certification implies enterprise customers; complex billing implies revenue).
- Use **range estimates** (e.g., "ARR likely $200K-$1M based on indirect signals").
- Mark as a **DD Priority** for verification.

---

## Step 2 — Five-Dimension Scorecard

Score each dimension **0–10**. Apply weights. Sum for a weighted total out of 10.

| # | Dimension | Weight |
|---|-----------|--------|
| A | Open-Source Ecosystem & Community Health | 25% |
| B | Team & Globalisation Capability | 20% |
| C | Technical Moat & Market Positioning | 20% |
| D | Commercialisation Path & PMF | 20% |
| E | Capital Exit Path | 15% |

---

### Dimension A — Open-Source Ecosystem & Community Health (25%)

**Core principle: Keyboard Metrics > Mouse Metrics.**

| Signal | Strong (8-10) | Weak (<5) |
|--------|---------------|-----------|
| Dependent Repositories | ≥1,000 | <10 |
| Monthly Active Contributors | ≥50 | <5 |
| External Contributor % | ≥40% | <10% |
| PR Merge Latency | ≤7 days | >30 days |
| Issue Close Rate (90d) | ≥60% | <20% |
| Release Cadence | Weekly/bi-weekly | Sporadic |
| ADOPTERS.md / Logos | 5+ named logos | None |
| Governance Tier | ASF TLP / CNCF | standalone |

**Scoring Guide:**
- **Project Age Calibration:** For projects <12 months old, prioritize **velocity** over absolute levels. A project reaching 5K stars in 3 months has higher signal than 10K stars in 3 years. Velocity signal can add +1 to the score (max 8.0).
- **One-Vote Veto for A:** External contributor % <5% (pure self-directed project) → automatic Pass.

---

### Dimension B — Team & Globalisation Capability (20%)

**Engineering Depth signals:**
- Founders are Apache/CNCF/LF committers or PMC members.
- Verifiable OSS history outside the company repo.
- Top-tier academic papers (NeurIPS/ICML/VLDB).

**GTM / Global Reach signals:**
- English-first documentation (Day 1).
- International contributors ≥20%.
- US paying customers or pilots.

**Scoring Guide:**
- 9-10: World-class engineers + proven US enterprise access.
- 5-6: Strong engineering, weak GTM — flag as "Series A condition".
- **One-Vote Veto for B:** Zero verifiable OSS history outside company repo → automatic Pass.

---

### Dimension C — Technical Moat & Market Positioning (20%)

| Level | Description | VC Signal |
|-------|-------------|-----------|
| L1 | New algorithm / architecture | Strongest moat |
| L2 | Significant engineering innovation | Strong moat |
| L3 | Differentiated system integration | Moderate moat |
| L4 | Prompt engineering / wrapper | Pass — no moat |

**Market Positioning:**
- Is this on track to be the **de facto standard**?
- Does vendor-neutrality create structural lock-in?
- **Narrative Consistency:** ≥2 pivots in <24 months = -1 point penalty. *Note: Market-following pivots (e.g., RAG → Agent Memory) do not count as penalties.*

**One-Vote Veto for C:** Core product is L4 (Wrapper) with no algorithmic differentiation → automatic Pass.

---

### Dimension D — Commercialisation Path & PMF (20%)

**Revenue Quality Hierarchy:**
1. Product ARR / Subscription (8-15x)
2. Usage-based / API billing (6-10x)
3. Infrastructure embedding / OEM (Strategic premium)
4. Proprietary data monetisation (High ceiling)
5. Professional Services (1-3x) ⚠️ Not scalable

**Indirect PMF Signals (Use when ARR is unknown):**
- SOC2 / HIPAA / ISO certification (implies enterprise readiness).
- Tiered pricing / Stripe integration (implies active billing).
- Detailed customer testimonials (not just generic quotes).
- Hiring for Sales/GTM roles.
*If 3+ indirect signals exist, D-score should not be below 5.0.*

**Scoring Guide:**
- 9-10: Product ARR ≥$1M, US enterprise customers, ≥50% inbound.
- 7-8: Early product ARR + strong PMF signals (top-tier logos).
- **One-Vote Veto for D:** Revenue entirely unverified (LoI/MOU only) AND valuation >2× sector median → automatic Pass.

---

### Dimension E — Capital Exit Path (15%)

**Strategic M&A value checklist:**
- Project is a "standard creator" (e.g., Iceberg, vLLM).
- Acquirer has "must have" urgency.
- **Sector Validation:** Large funding rounds for direct competitors (Series A+) are POSITIVE signals for sector value, even if they increase competition.

**Scoring Guide:**
- 9-10: Clear "must acquire" logic; comparable exits >$1B.
- 5-6: Acqui-hire probable; or M&A possible but buyer urgency low.

---

## Step 3 — Compute Weighted Total

```
Total = (A × 0.25) + (B × 0.20) + (C × 0.20) + (D × 0.20) + (E × 0.15)
```

| Score | Decision | Action |
|-------|----------|--------|
| 8.5 – 10.0 | 🟢 Strongly Recommend | Fast-track IC |
| 7.0 – 8.4 | 🟡 Recommend with Conditions | Milestone-linked terms |
| 5.5 – 6.9 | 🟠 Watch / Track | Re-evaluate in 6 months |
| < 5.5 | 🔴 Pass | Decline |

---


---

## Optional Module: Star Health & Anti-Fraud Protocol (SHP)

**Usage:** Trigger this module if (a) user explicitly requests "Star Health check", (b) project is in a hyper-hyped AI sector, or (c) Star growth velocity is >20% MoM without corresponding Issue/PR activity.

### SHP Step 1: Data Collection
Calculate the following ratios from GitHub data:
1. **Star/Fork Ratio (S/F):** Total Stars ÷ Total Forks.
2. **Star/Issue Ratio (S/I):** Total Stars ÷ Total Issues (Open + Closed).
3. **Fork Rate (FR):** Total Forks ÷ Total Stars.
4. **External Commit % (EC):** Commits by non-core-team ÷ Total Commits.

### SHP Step 2: Signal Evaluation
| Metric | Healthy | Warning | Critical |
|:---|:---|:---|:---|
| **S/F Ratio** | 5x - 10x | 11x - 20x | >20x |
| **S/I Ratio** | 50x - 100x | 101x - 200x | >200x |
| **Fork Rate** | 9% - 23% | 5% - 8% | <5% |
| **EC %** | >20% | 5% - 19% | <5% |

### SHP Step 3: Scoring Adjustment for Dimension A
If SHP is active, apply the following penalties to the raw score of **Dimension A**:
- **1 Warning:** -0.5 points.
- **2 Warnings:** -1.0 points.
- **1 Critical:** -1.5 points.
- **2+ Critical:** -2.0 points and flag for "One-Vote Veto" review.

---
## Step 4 — Required Output Format

1. **Macro Gate Result:** One sentence per question.
2. **Scorecard Table:** Dimension, Weight, Score, Weighted.
3. **Verdict Line:** `🟢/🟡/🟠/🔴 [Decision] — [One sentence rationale]`
4. **Dimension Narrative:** 2-4 sentences per dimension. *Note: Explicitly mention if scores are based on indirect signals.*
5. **One-Vote Veto Check:** Confirm if any veto is triggered.
6. **IC Thesis:** One paragraph, ≤100 words (Why now, Why this, Exit conviction).
7. **DD Priority List:** Top 3-5 questions to verify (especially "Not Found" items).
8. **Watch Triggers:** Specific milestones for upgrade.
