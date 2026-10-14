# Changelog

All accepted framework changes and community case studies are logged here.

Format: `[YYYY-MM] Type — Description — Contributor`

---

## v1.4 — October 2026
v1.4 is a corrective release. Weights, thresholds and dimension definitions are unchanged, and no evaluated project's score or verdict changes. There was no v1.3 release.
**Framework (SKILL.md)**
- `[2026-10]` Framework — Two modes: Owner Mode (a health check for maintainers: diagnosis and next steps, no verdict label) and Investor Mode (verdict and IC thesis). Scoring is identical in both — @lucy-cxy
- `[2026-10]` Framework — One veto list. In v1.2 the README, SKILL.md and the template listed three different veto sets. v1.4 keeps four hard vetoes (core IP not owned, license conflict, confirmed fabricated traction or benchmarks, unresolved major litigation) and turns the rest into risk flags A1, B1, B2, B3, C1, C2, D1 and G1 — @lucy-cxy
- `[2026-10]` Framework — Judgment & Trust Observation Log (J1–J6, T1–T7), non-scoring. Each item is labeled by data class (third-party automatable / third-party with a coding rule / owner-reported), with coding rules R1–R5 — @lucy-cxy
- `[2026-10]` Framework — Star Health Protocol: removed Fork Rate (the reciprocal of Star/Fork, previously double-counted); Star/Fork below 5x is treated as normal; 2+ Critical now triggers a fabricated-traction review instead of a veto review — @lucy-cxy
- `[2026-10]` Framework — Macro Gate: in Owner Mode a NO is recorded as a strategic risk instead of stopping the evaluation — @lucy-cxy
- `[2026-10]` Framework — N/A rule: signals that do not apply (e.g., a project that does not accept outside PRs) are marked N/A, not scored as weak — @lucy-cxy
- `[2026-10]` Framework — Acqui-hire Candidate flag moved from the template into SKILL.md (closes #3) — @lucy-cxy
- `[2026-10]` Framework — Known Limitations section added — @lucy-cxy
**Repository**
- README rewritten for project owners; health-check process and conflict-of-interest rules published
- New Health Check issue template and `health-check` label
- Fixed the README table workflow: it failed on every run (JSON parsing error), its rows had 5 columns while the table has 6, and it inserted the issue title directly into a shell command. Data is now passed through environment variables
- Replaced links to the old GitHub account
- llms.txt: corrected the claim that weights were derived from evaluated projects
- MimiClaw (community submission, #2) added to the Evaluated Projects table
**Deferred to v2.0:** dynamic weights by stage (#4), PMF-direction sub-indicator (#5), scoring the Observation Log, back-testing scores against outcomes.
---

## v1.1 — March 2026 (Initial Public Release)

**Framework changes from internal review:**
- `[2026-03]` Framework — Removed China-policy-specific language; all geopolitical references replaced with globally neutral equivalents — @lucycxy
- `[2026-03]` Framework — Dimension D: Replaced "Managed SaaS" revenue tier with "Infrastructure embedding / OEM licensing" and "Proprietary data & model asset monetisation" to reflect current USD VC valuation reality — @lucycxy
- `[2026-03]` Framework — Macro Gate Q3: Replaced "RL environment value" with structural chokepoint framing applicable across AI Infra sub-sectors — @lucycxy

**Founding case studies:**
- `[2026-03]` Case — vLLM / Inferact: 8.9/10 → Strongly Recommend. $150M Seed @ $800M, a16z + Lightspeed — @lucycxy
- `[2026-03]` Case — Hugging Face: 8.5/10 → Strongly Recommend. $235M Series D @ $4.5B, $130M ARR — @lucycxy

---

## v1.2 Roadmap (Post Aryn Retrograde)

Three framework gaps identified from the Aryn/Sycamore retrograde evaluation (W13):

1. **Acqui-hire Candidate flag** — When Dim B (Team) ≥ 7.5 AND Dim E (Exit) ≥ 6.0, flag as "Acqui-hire Candidate" even if weighted total < 5.5. Current Pass verdict misclassifies teams with high acqui-hire value floor. **Status: done in v1.4.**

2. **Dynamic dimension weights for pre-product stage** — Explore allowing Dim B weight to increase from 20% → 30% and Dim A (Ecosystem) to decrease from 25% → 15% for early-stage infrastructure projects where team IS the product. **Status: deferred to v2.0.**

3. **Product-Market Fit Direction sub-indicator in Dim C** — Explicitly model the gap between technical vision and current market demand. "Tech direction right + product packaging wrong" ≠ "Tech direction wrong." Sycamore's end-to-end analytics vs. market's demand for point parsing is the canonical example. **Status: deferred to v2.0.**

Triggered by: Aryn scored 5.13 (Pass), then was acquired by Glean ($7.2B) 3 weeks later. All 5 dimensions were directionally correct, but the final verdict was misleading for seed investors.

---

## Pending Review

*(Community submissions under review appear here before acceptance)*

---

## How to Read This Log

- **Framework** entries = changes to SKILL.md scoring rules
- **Case** entries = new project evaluations added to /cases/
- **Correction** entries = factual fixes to existing case studies with source citations

## W13 (2026-03-23)

### New Evaluations
- **Unsloth** (8.10 🟡 Yellow Strong) — Fine-tuning infra, 57K stars, 150M downloads
- **Hindsight** (7.55 🟡 Yellow) — Agent memory layer, $1M ARR / 7-person team
- **DeepAgents** (7.45 🟡 Yellow) — LangChain coding agent, NVIDIA GTC partnership
- **TradingAgents** (6.35 🟠 Watch) — Multi-agent financial trading, 18% fork ratio
- **MiroFish** (5.54 🟠 Watch) — Swarm simulation, GitHub #1 trending, Shanda-backed

### README Updates
- Evaluated Projects table expanded: 2 → 13 projects (benchmarks + W10 + W13)
- Added mermaid charts (bar + quadrant) with all evaluated projects
- Added "Batch" column to distinguish evaluation waves

### Cumulative Stats
- Total projects evaluated: 13
- 🟢 Green: 2 | 🟡 Yellow: 6 | 🟠 Watch: 5
