# OSS Investment Scorecard — Evaluation Template

*Framework version: v1.4 | Choose a mode, fill in all sections, calculate the weighted total, then request a health check (project owners) or submit via GitHub Issue (investors and analysts)*

---

## Project Information

| Field | Value |
|-------|-------|
| Project Name | |
| GitHub Repository | |
| Commercial Entity | |
| Funding Stage | |
| Sub-sector | |
| Evaluator | |
| Evaluation Date | |
| Mode | ☐ Owner Mode ☐ Investor Mode |

---

## Step 1 — Macro Gate (answer before scoring)

| Question | Answer | Notes |
|----------|--------|-------|
| 1. Is the sub-sector still in window-of-opportunity phase? | ☐ Yes ☐ No | |
| 2. Does open-source mode confer structural advantage? | ☐ Yes ☐ No | |
| 3. Is the AI-cycle value premium applicable? | ☐ Yes ☐ No | |

*Investor Mode: any NO → stop and Pass. Owner Mode: record each NO as a strategic risk and continue.*

**Gate result:** ☐ Proceed to scoring ☐ Stop — Pass (reason: ___)

---

## Step 1.2 — Judgment & Trust Observation Log (non-scoring)
*Class 1 = third-party, automatable · Class 2 = third-party, apply coding rules R1–R5 in SKILL.md · Class 3 = owner-reported (Owner Mode only, label "owner-reported, not verified"). If you cannot collect an item, write "Not observable": it is not a weak result.*
| ID | Observation | Class | Finding | Source URL | Date collected |
|----|-------------|-------|---------|-----------|----------------|
| J1 | Scope written down (users, non-goals, design docs, AGENTS.md) | 2 | | | |
| J2 | Reasons given when declining (last 10 closed without merging) | 2 | | | |
| J3 | Substantive review (last 10 merged PRs from non-maintainers) | 2 | | | |
| J4 | Median time to first maintainer response for newcomers | 1 | | | |
| J5 | Months with a release in the last 12; release notes; breaking-change notices | 1 | | | |
| J6 | Distinct people who merged PRs or signed releases (last 6 months) | 1 | | | |
| T1 | Dependents (libraries) or installs (applications) | 1 | | | |
| T2 | Third-party integrations, plugins, "add to …" buttons | 2 | | | |
| T3 | Downstream forks: build-on vs walk-away | 2 | | | |
| T4 | Money: public sponsors, Open Collective, pricing page / owner-reported customers | 1 / 3 | | | |
| T5 | OpenSSF Scorecard, signed releases, SECURITY.md, advisories | 1 | | | |
| T6 | Maintainers' track record; LICENSE change history | 1 | | | |
| T7 | Agent recommendation test (experimental: model, version, date, prompt) | 2 | | | |

---

## Step 2 — Five-Dimension Scorecard

### A. Open-Source Ecosystem Health (25%)

| Signal | Data | Score (0-10) |
|--------|------|-------------|
| Dependent Repositories | | |
| Monthly Active Contributors | | |
| External Contributor % | | |
| PR Merge Latency (days) | | |
| Issue Close Rate (90d) | | |
| Release Cadence | | |
| ADOPTERS.md / Named Enterprise Logos | | |
| Governance Tier (ASF TLP / CNCF / etc.) | | |
| Stars — Share of Voice vs. top 3 rivals | | |
| Prestigious Backing (GitHub SOS Fund, etc.) | | |

*Mark N/A for signals that do not apply (for example, a project that does not accept outside PRs). N/A is not weak.*

**Dimension A Score: ___ / 10**

Key evidence:

Main risk:

---

### B. Team & Globalisation Capability (20%)

| Signal | Evidence | Score (0-10) |
|--------|----------|-------------|
| Engineering depth (Apache/CNCF committer, papers) | | |
| Prior infrastructure company experience | | |
| Verifiable OSS contribution outside company repo | | |
| English-first documentation | | |
| US paying customers or enterprise pilots | | |
| Non-home-country contributor % | | |
| VC/enterprise network access | | |
| Legal structure (Cayman/Singapore) | | |

**Dimension B Score: ___ / 10**

Key evidence:

Main risk:

---

### C. Technical Moat & Market Positioning (20%)

**Technology Layer:** ☐ L1 (new algorithm) ☐ L2 (eng. innovation) ☐ L3 (integration) ☐ L4 (prompt/fine-tune — Pass)

| Signal | Evidence | Score (0-10) |
|--------|----------|-------------|
| Technology layer (see above) | | |
| Independent benchmark validation | | |
| On track to be de facto standard? | | |
| Vendor-neutral governance advantage | | |
| Sub-sector positioning (high-value AI niche?) | | |
| Narrative consistency (pivot count: ___) | | |

**Dimension C Score: ___ / 10**  
*(Apply -1 penalty if narrative pivot count ≥ 2)*

Key evidence:

Main risk:

---

### D. Commercialisation & PMF (20%)

**Revenue type:** ☐ Product ARR ☐ Usage-based ☐ Managed SaaS ☐ Professional Services ☐ Grants only

| Metric | Value | Healthy? |
|--------|-------|---------|
| ARR / Revenue (last 12m) | | |
| YoY growth rate | | |
| Largest customer concentration | % | ☐ <30% ☐ >30% |
| US-paying customers present? | | ☐ Yes ☐ No |
| Gross margin (est.) | % | |
| Inbound % of pipeline | % | |
| Runway post-raise | months | |

*If PS-dominant: note mandatory term sheet condition (product ARR conversion within 18m)*

**Dimension D Score: ___ / 10**

Key evidence:

Main risk:

---

### E. Capital Exit Path (15%)

| Exit Path | Probability | Rationale |
|-----------|------------|-----------|
| Strategic M&A | % | |
| IPO | % | |
| Follow-on rounds | % | |
| Acqui-hire | % | |
| Downside / Pass | % | |

**Most comparable historical exit:**

**Named potential acquirers:**

**Dimension E Score: ___ / 10**

Key evidence:

Main risk:

---

## Step 3 — Weighted Total

| Dimension | Weight | Score | Weighted |
|-----------|--------|-------|---------|
| A. Open-Source Ecosystem | 25% | /10 | |
| B. Team & Globalisation | 20% | /10 | |
| C. Technical Moat | 20% | /10 | |
| D. Commercialisation & PMF | 20% | /10 | |
| E. Exit Path | 15% | /10 | |
| **TOTAL** | 100% | — | **/10** |

**Verdict:** ☐ 🟢 Strongly Recommend ☐ 🟡 Recommend with Conditions ☐ 🟠 Watch ☐ 🔴 Pass

### Acqui-hire Candidate Check (v1.4)

If Dim B ≥ 7.5 AND Dim E ≥ 6.0 AND Weighted Total < 5.5:
→ Flag as 🟡 **Acqui-hire Candidate** (in addition to Pass verdict)
→ Note: project may generate positive seed-stage returns via talent acquisition despite failing standalone commercialization threshold.

---

## Hard Veto Check (v1.4)
*Investor Mode: any box checked = automatic Pass. Owner Mode: report as "must fix before any fundraise".*
- ☐ V1 Core IP not owned by the project's entity or founders
- ☐ V2 License conflict blocks commercial use or redistribution of the core
- ☐ V3 Fabricated traction or benchmarks, confirmed by evidence
- ☐ V4 Unresolved major litigation or patent claims on the core technology
**Hard veto triggered:** ☐ Yes (specify: ___) ☐ No
---
## Risk Flags (v1.4)
*Risk flags never disqualify on their own. Reflect each one in the related dimension score and explain it.*
| ID | Risk flag | Triggered? | Rationale / mitigation |
|----|-----------|-----------|------------------------|
| A1 | Concentrated contribution (external contributor % < 5%) | ☐ | |
| B1 | No verifiable OSS record outside the company repo | ☐ | |
| B2 | Single decision-maker (one person merges and releases; no succession plan) | ☐ | |
| B3 | Market access / jurisdiction risk | ☐ | |
| C1 | Wrapper (L4) with no algorithmic differentiation | ☐ | |
| C2 | Narrative pivots ≥ 3 in < 24 months | ☐ | |
| D1 | Revenue LoI/MOU only and valuation > 2× sector median (Investor Mode) | ☐ | |
| G1 | No English documentation and zero international contributors | ☐ | |
---
## Owner Mode Report (Owner Mode only)
1. **Where you stand** (score and band as a reference only; strongest and weakest dimension):
2. **What an investor will ask** (three questions, each tied to a dimension):
3. **What to do next** (three actions for the next 90 days):
4. **Project context check** (scope and non-goals / engineering constraints / tests for core behavior / decision records / AGENTS.md: present or missing):
5. **Copy risk** (how fast a well-resourced team with coding agents could replicate this, and what it could not copy):
6. **Path fit:** ☐ Venture-backed company ☐ Bootstrapped business ☐ Sponsorship ☐ Community or personal project ("Not raising venture capital" is a legitimate conclusion.)
7. **Hard vetoes and risk flags, with mitigations:**
8. **Owner-reported items** (label "owner-reported, not verified"):
9. **Data gaps** ("Searched, not found" / "Not observable"):
---

## IC Thesis (≤ 100 words) — Investor Mode only

*Why now · Why this project · Exit path conviction*

> 

---

## DD Priority List

1. 
2. 
3. 
4. 
5. 

---

## Watch Triggers (if verdict = Watch)

*Specific, measurable milestones that would upgrade to Recommend:*

1. 
2. 
3.
