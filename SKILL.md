---

name: oss-investment-scorecard

description: >

  Evaluate an open source project through a venture investor's lens. Owner Mode is a health

  check for maintainers (where the project stands, what an investor would ask, what to do next).

  Investor Mode decides whether a project is investable by a USD VC fund in the AI cycle.

  ALWAYS use this skill when the user asks to:

  - "evaluate [project] for investment" / "can we invest in [project]" / "score this open source company"

  - "health check my open source project" / "how would an investor see my project"

  - "投资评估 [项目]" / "这个开源项目值得投吗" / "给 [公司] 打分" / "帮我的开源项目做体检"

  - assess, rate, rank or compare open source startups from an investment perspective

  Output: a 5-dimension weighted scorecard (max 10). Investor Mode adds a verdict and an IC thesis;

  Owner Mode adds a diagnosis and next steps. Both modes check four hard vetoes, list risk flags,

  and keep a Judgment & Trust Observation Log.

---

# Open Source Project Investment Scorecard (V1.4)

## Purpose

Produce a rigorous, consistent, reusable evaluation of an open source project through the eyes of a USD venture investor, calibrated for the **AI technology acceleration cycle (2023 onwards)**.

Two audiences use the same scoring rules:

- **Project owners** (primary audience from v1.4): maintainers whose project already has a product and users but has not raised funding. Owner Mode shows them how an investor would read their project, before an investor does.

- **Investors and analysts**: Investor Mode decides whether a project is investable.

Scoring is identical in both modes. Scores stay comparable across modes and with every case evaluated since v1.1.

Built from: Bessemer Venture Partners Data 3.0 Roadmap, Oxx VC, Basis Set Ventures, Linux Foundation / COSSA, Unusual VC, Matrix VC, and two live case studies (Eigent.AI / CAMEL-AI and Datastrato / Apache Gravitino).

---

## Step 0 — Choose the Mode

| Mode | Use when | Output |

|------|----------|--------|

| **Owner Mode** | The project's maintainer asks for a self-assessment or a health check, or the report will go to the maintainer first | Diagnosis and next steps (Step 4B). No verdict label. |

| **Investor Mode** | An investor or analyst evaluates someone else's project for investment | Verdict and IC thesis (Step 4A) |

If the user says they built or maintain the project, use Owner Mode. If the mode is unclear, ask.

---

## Step 1 — Fact Sheet, Observation Log & Macro Gate

### 1.1 Pre-Evaluation Fact Sheet

Before scoring, perform a web search to gather the following 7 items. Each item MUST include a source URL or be marked as "Searched, not found". Record the date each data point was collected.

1. **GitHub Metrics:** Stars, Monthly Active Contributors (last 30d), External Contributor %, Dependent Repositories. For applications that other projects do not import (desktop apps, CLIs, hosted services), record install signals instead of dependents: release download counts, container image pulls, package-manager install statistics.

2. **Team Background:** Founders' prior OSS contributions, PMC/Committer status, prior infrastructure company experience.

3. **Funding History:** Total raised, last round valuation, lead investors.

4. **Commercial Traction:** Publicly mentioned ARR, customer logos, pricing model.

5. **Technical Architecture:** Core innovation level (L1-L4), key benchmarks (e.g., SOTA claims).

6. **Global Presence:** Documentation language, international contributor %, US customer presence.

7. **Competitive Benchmarking:** Identify 2-3 closest rivals; note their funding, stars, and key distribution partners (e.g., AWS/Azure).

### 1.2 Judgment & Trust Observation Log (non-scoring, new in v1.4)

When code is cheap, the scarce resources in an open source project are human judgment, attention and trust. Record the observations below for every evaluation.

In v1.4 these observations **do not change the score**. They inform the dimension narratives and the Owner Mode diagnosis, and they build the dataset that v2.0 will use to test which signals actually predict outcomes.

**Data classes**

- **Class 1 — Third-party, automatable.** Anyone can collect it from public data, and a script can collect it.

- **Class 2 — Third-party, needs a coding rule.** The raw data is public, but a person or a model must classify it using the rules in 1.3.

- **Class 3 — Owner-reported.** Only the project can provide it. Use it only in Owner Mode and label it "owner-reported, not verified". Never use it in a public Investor Mode evaluation.

If an observation cannot be collected, record **"Not observable"**. Never treat "Not observable" as a weak result.

**Judgment and attention**

| ID | Observation | Class | What to record | Watch out for |

|----|-------------|-------|----------------|---------------|

| J1 | Scope written down | 2 | Whether the README or docs state who the project is for, who it is not for, and what it will not do; whether design docs, decision records or AGENTS.md exist | File presence is automatable; whether the scope is clear needs rule R1 |

| J2 | Reasons given when declining | 2 | Of the last 10 PRs or issues a maintainer closed without merging, how many include a maintainer-written reason (rule R2) | Exclude stale-bot closures |

| J3 | Substantive review | 2 | Of the last 10 merged PRs from non-maintainers, how many show substantive review or maintainer follow-up commits (rule R3) | If review happens in internal systems, record "Not observable" |

| J4 | Response to newcomers | 1 | Median time from a first-time contributor's issue or PR to the first maintainer response (GitHub labels first-time contributors) | If the project routes feedback to Discord or a forum, record "Not observable", not "slow" |

| J5 | Release discipline | 1 | Months in the last 12 with at least one release; whether releases have notes; whether breaking changes were announced | Count months, not versions: CI can publish many versions in one day |

| J6 | People who merge and sign | 1 | Number of distinct people who merged PRs or signed release commits in the last 6 months | Who holds merge rights is not public (Class 3) |

**Trust** — trust shows in what others pay to rely on the project. A star costs nothing; a dependency, an integration or a payment costs something.

| ID | Observation | Class | What to record | Watch out for |

|----|-------------|-------|----------------|---------------|

| T1 | Dependents or installs | 1 | Libraries: dependents from deps.dev, package registries or the GitHub dependency graph. Applications: the install signals listed in 1.1 | Closed-source dependents are invisible |

| T2 | Third-party integrations | 2 | Integrations, plugins and "add to …" buttons maintained by parties other than the project's maintainers (rule R4), with URLs | The search is never complete; record where you searched |

| T3 | Downstream forks | 2 | Among active forks, how many build on the project and how many walked away (rule R5) | The same fork count can mean adoption or dissatisfaction |

| T4 | Money | 1 / 3 | Public: GitHub Sponsors (public sponsors), Open Collective, sponsor logos, pricing page. Owner-reported: paying customers, contracts, revenue | Keep public and owner-reported figures apart |

| T5 | Verifiable security and releases | 1 | OpenSSF Scorecard result and date; signed releases; SECURITY.md; published security advisories; signed or notarized binaries | — |

| T6 | Maintainer track record | 1 | Maintainers' earlier projects and whether they are still maintained; LICENSE change history | Whether a license change harmed users needs judgment |

| T7 | Agent recommendation (experimental) | 2 | Ask three coding agents for a tool that does this project's job; record model, version, date, prompt, and whether the project was recommended | Low reproducibility; never use on its own |

**Owner-reported only (Class 3):** who holds merge and release rights; community activity in private channels (Discord, Slack, WeChat groups); usage telemetry; paying customers and revenue.

### 1.3 Coding Rules for Class 2 Observations

- **R1 Scope written down:** counts when the project states its intended users and at least one explicit non-goal or out-of-scope item. A tagline alone does not count.

- **R2 Reason given:** counts when a human maintainer's closing comment says why: out of scope, duplicate (with link), superseded (with link), won't fix (with rationale), or needs design discussion first. Bot messages, template replies and silent closes do not count.

- **R3 Substantive review:** counts when the PR has at least one review comment that requests or discusses a change, or a maintainer follow-up commit before or after merge (commit-then-review). An approval alone or "LGTM" does not count.

- **R4 Third-party integration:** counts only when the integration is maintained by a person or organization that is not a maintainer of the project, and a public URL shows it.

- **R5 Fork type:** *Build-on*: the fork merged upstream changes in the last 90 days, or is published as a plugin, extension or distribution that names the upstream. *Walk-away*: the fork is ahead of upstream, has not merged upstream changes for 180+ days, and says in its README or issues that it diverged. Anything else is *Unclassified*.

For published evaluations, code each Class 2 observation twice (by two people, or by a model with a fixed prompt plus a human spot-check) and note any disagreement.

### 1.4 Macro Gate (Non-Scoring Pre-Check)

Answer these three binary questions.

- **Investor Mode:** if any answer is NO, stop and recommend Pass.

- **Owner Mode:** do not stop. Record each NO as a strategic risk and continue.

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

- **Signals that do not apply:** If a signal does not apply (for example, the project does not accept outside pull requests, so it has no PR merge latency and no external contributor share), mark it N/A and score on the remaining signals. N/A is not weak.

- **Risk Flag A1 (replaces the v1.2 veto):** External contributor % < 5%. Record it and reflect it in the A score with a written rationale. Concentrated contribution is common in successful commercial open source (Elasticsearch has long had more than 95% of its changes from Elastic employees), and many maintainers now close outside pull requests by choice. Treat it as concentration risk, not as a disqualifier.

- **AI-era caution:** Commit counts, contributor counts, PR merge latency and issue close rate are increasingly shaped by coding agents and by maintenance style (bulk closing of stale issues, commit-then-review). Read them together with the Observation Log.

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

- **Risk Flag B1 (replaces the v1.2 veto):** Zero verifiable OSS history outside the company repo.

- **Risk Flag B2:** Single human decision-maker: one person merges and releases everything, and there is no succession plan. Writing code with agents is not the risk; having only one person who decides is.

- **Risk Flag B3:** Market access or jurisdiction risk: no path to the markets USD investors expect, or a corporate structure affected by outbound or inbound investment rules. Record the structure and the intended route; non-US routes can be viable.

---

### Dimension C — Technical Moat & Market Positioning (20%)

| Level | Description | VC Signal |

|-------|-------------|-----------|

| L1 | New algorithm / architecture | Strongest moat |

| L2 | Significant engineering innovation | Strong moat |

| L3 | Differentiated system integration | Moderate moat |

| L4 | Prompt engineering / wrapper | Weak — no moat |

**Market Positioning:**

- Is this on track to be the **de facto standard**?

- Does vendor-neutrality create structural lock-in?

- **Narrative Consistency:** ≥2 pivots in <24 months = -1 point penalty. *Note: Market-following pivots (e.g., RAG → Agent Memory) do not count as penalties.*

**Risk Flag C1 (replaces the v1.2 veto):** Core product is L4 (wrapper) with no algorithmic differentiation. An L4 project usually scores 4 or lower on C.

**Risk Flag C2:** Narrative pivots ≥3 in <24 months (the -1 penalty above still applies).

**Copy risk (non-scoring in v1.4):** With coding agents, a library with clear APIs and good tests can be forked or rewritten in weeks. Record how fast a well-resourced team could replicate the project, and what it could not copy: the maintainers' trust, the community, the written project context, the distribution position.

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

- **Risk Flag D1 (replaces the v1.2 veto; Investor Mode):** Revenue entirely unverified (LoI/MOU only) AND valuation >2× sector median.

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

## Step 2.5 — Hard Vetoes and Risk Flags

v1.2 listed three different sets of "one-vote vetoes" in README.md, SKILL.md and the evaluation template. v1.4 replaces all three with the single list below.

### Hard vetoes

In Investor Mode, any hard veto means an automatic Pass regardless of the total score. In Owner Mode, report it as "must fix before any fundraise".

| ID | Hard veto |

|----|-----------|

| V1 | Core IP is not owned by the project's entity or founders (contributor IP not assigned, or claimed by an employer) |

| V2 | A license conflict blocks commercial use or redistribution of the core |

| V3 | Fabricated traction or benchmarks (manipulated stars or downloads, or falsified performance claims), confirmed by evidence. A Star Health "2+ Critical" result triggers a V3 review, not an automatic veto |

| V4 | Unresolved major litigation or patent claims on the core technology |

### Risk flags

Risk flags never cause an automatic Pass. Record each one, reflect it in the related dimension score with a written rationale, and in Owner Mode give a mitigation.

| ID | Risk flag | Trigger | Possible mitigation (Owner Mode) |

|----|-----------|---------|-----------------------------------|

| A1 | Concentrated contribution | External contributor % < 5% | State the contribution policy; show adoption through dependents, installs and integrations |

| B1 | No outside OSS record | Zero verifiable OSS work outside the company repo | Contribute upstream to the projects you depend on |

| B2 | Single decision-maker | One person merges and releases everything; no succession plan | Give a second person review and release rights; write down the release process |

| B3 | Market access / jurisdiction | No path to the markets USD investors expect, or a structure affected by investment rules | Document the corporate structure and the intended route early |

| C1 | Wrapper (L4) | Core product is L4 with no algorithmic differentiation | Identify the part that is hard to copy and build on it |

| C2 | Narrative instability | ≥3 pivots in <24 months | Write down the scope and the reason for each pivot |

| D1 | Unverified revenue at a high valuation (Investor Mode) | Revenue LoI/MOU only and valuation >2× sector median | — |

| G1 | No global reach | No English documentation and zero international contributors | Publish English documentation for the core use case |

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

- **Investor Mode** uses the Decision column.

- **Owner Mode** shows the score and its band as a reference point, without the Decision label.

**Acqui-hire Candidate flag (added in v1.4):** If B ≥ 7.5 AND E ≥ 6.0 AND the weighted total < 5.5, add the flag "Acqui-hire Candidate" next to the verdict. Source: the Aryn / Sycamore retrograde case scored 5.13 (Pass), and the company was acquired by Glean three weeks later.

---

## Optional Module: Star Health & Anti-Fraud Protocol (SHP)

**Usage:** Trigger this module if (a) user explicitly requests "Star Health check", (b) project is in a hyper-hyped AI sector, or (c) Star growth velocity is >20% MoM without corresponding Issue/PR activity.

**Change in v1.4:** Fork Rate (Forks ÷ Stars) is removed. It is the reciprocal of the Star/Fork ratio, so v1.2 counted the same fact twice.

### SHP Step 1: Data Collection

Calculate the following ratios from GitHub data:

1. **Star/Fork Ratio (S/F):** Total Stars ÷ Total Forks.

2. **Star/Issue Ratio (S/I):** Total Stars ÷ Total Issues (Open + Closed).

3. **External Commit % (EC):** Commits by non-core-team ÷ Total Commits.

### SHP Step 2: Signal Evaluation

| Metric | Healthy | Warning | Critical |

|:---|:---|:---|:---|

| **S/F Ratio** | ≤10x (below 5x is normal, not a warning) | 11x - 20x | >20x |

| **S/I Ratio** | ≤100x | 101x - 200x | >200x |

| **EC %** | >20% | 5% - 19% | <5% |

Read ratios against projects of the same type: curated lists, skill collections and end-user apps naturally show higher S/F and S/I than libraries.

### SHP Step 3: Scoring Adjustment for Dimension A

If SHP is active, apply the following penalties to the raw score of **Dimension A**:

- **1 Warning:** -0.5 points.

- **2 Warnings:** -1.0 points.

- **1 Critical:** -1.5 points.

- **2+ Critical:** -2.0 points and trigger a V3 (fabricated traction) review.

If Risk Flag A1 is already reflected in the A score, do not apply the EC penalty again.

---

## Step 4 — Required Output Format

### 4A. Investor Mode

1. **Macro Gate Result:** One sentence per question.

2. **Scorecard Table:** Dimension, Weight, Score, Weighted.

3. **Verdict Line:** `🟢/🟡/🟠/🔴 [Decision] — [One sentence rationale]` (add "Acqui-hire Candidate" when it applies).

4. **Dimension Narrative:** 2-4 sentences per dimension. *Note: Explicitly mention if scores are based on indirect signals.*

5. **Hard Veto and Risk Flag Check:** Hard vetoes triggered (if any); risk flags with rationale.

6. **Observation Log Summary:** Class 1 and Class 2 items only, each with its data class and collection date.

7. **IC Thesis:** One paragraph, ≤100 words (Why now, Why this, Exit conviction).

8. **DD Priority List:** Top 3-5 questions to verify (especially "Not Found" items).

9. **Watch Triggers:** Specific milestones for upgrade.

### 4B. Owner Mode

1. **Where you stand:** the score and its band as a reference point; the strongest and the weakest dimension, and why.

2. **What an investor will ask:** the three questions an investor is most likely to ask, each tied to a dimension.

3. **What to do next:** three concrete actions for the next 90 days.

4. **Project context check:** scope and non-goals, engineering constraints, tests that verify core behavior, decision records, AGENTS.md: present or missing.

5. **Copy risk:** how fast a well-resourced team with coding agents could replicate the project, and what it could not copy.

6. **Path fit:** which paths fit this project: venture-backed company, bootstrapped business, sponsorship, or remaining a community or personal project. "Not raising venture capital" is a legitimate conclusion, not a failure.

7. **Hard vetoes and risk flags:** each with a mitigation.

8. **Observation Log:** every item with its data class; owner-reported items labeled "owner-reported, not verified".

9. **Data gaps:** items marked "Searched, not found" or "Not observable".

**Owner Mode handling rule:** Send the report to the maintainer privately first. Publish it only with the maintainer's consent, together with the maintainer's response.

---

## Known Limitations (v1.4)

1. Weights and thresholds are practitioner judgment. They have not yet been tested against funding or exit outcomes. v2.0 will back-test scores against what happened to evaluated projects.

2. Activity metrics are increasingly shaped by coding agents and maintenance style, and part of the development process is moving out of public view (internal review, private chat channels, automated releases).

3. The code-based moat ladder (L1-L4) is weakening: with coding agents, forks and large rewrites are cheap.

4. The two calibration anchors (vLLM/Inferact and Hugging Face) are both successful companies. There are no early-stage or negative anchors yet.

5. Observation Log items are recorded but not scored until v2.0 tests them.
