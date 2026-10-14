# Scored Examples — Calibration Reference

Two landmark cases that anchor the scoring scale. Both are real, publicly funded projects evaluated using the same 5-dimension framework.

---

## Case 1: vLLM → Inferact (AI Inference Infrastructure)

**Status at evaluation:** Open-source project actively raising institutional capital  
**Outcome:** $150M Seed @ $800M valuation, led by a16z + Lightspeed (January 2026)  
**Use this case as the anchor for: 9.0+ scores — what a category-defining open-source infrastructure project looks like**

### Background

vLLM was created in 2023 at UC Berkeley's Sky Computing Lab (same lab that produced Apache Spark and Ray). Its core innovation, PagedAttention, fundamentally changed how LLM inference manages GPU memory — reducing waste by storing KV cache data in non-adjacent RAM segments. The commercial entity Inferact was founded in November 2025 by vLLM's core maintainers to bring the project to market.

### Scores

| Dimension | Score | Key Evidence |
|-----------|-------|-------------|
| A. Open-Source Ecosystem | 9.5/10 | 2,000+ contributors; 50+ core developers; used by Meta, Google, Amazon in production; supports 500+ model architectures, 200+ accelerator types; PyTorch Foundation stewardship; a16z hosted the first vLLM meetup and made the first OSS AI grant to this team |
| B. Team & Globalisation | 9.0/10 | Ion Stoica (Databricks co-founder, UC Berkeley Prof, Sky Computing Lab director) as key advisor; Simon Mo, Woosuk Kwon, Kaichao You as founders — all core Berkeley researchers; proven track record: same lab produced Spark ($43B Databricks) and Ray |
| C. Technical Moat | 9.5/10 | L1 innovation: PagedAttention is a genuinely new algorithm with reproducible benchmarks; de facto standard for LLM inference — every major hardware vendor (NVIDIA, AMD, Intel Gaudi, Google TPU, AWS Neuron) integrates with vLLM on Day 1 of new chip release; this IS the inference standard |
| D. Commercialisation | 7.0/10 | Minimal direct revenue at time of raise ("little revenue" per Forbes); but Amazon Web Services is a named production user; managed serverless product roadmap is clear; Open Core → Managed SaaS path well-defined; weakness: revenue not yet established |
| E. Exit Path | 9.5/10 | Three credible paths: ①IPO (category leader, Berkeley pedigree); ②Strategic acquisition by NVIDIA/AWS/Google/Microsoft (whoever doesn't own the inference standard loses); ③Databricks-style growth to $10B+ independent platform. "Must-buy-or-lose" urgency is real |

**Total: 8.9/10 → 🟢 Strongly Recommend**

**Hard Veto Check:** None triggered.

**IC Thesis:** vLLM is the inference equivalent of what Kubernetes was for container orchestration — not one of many options, but the standard that every other player must be compatible with. Inferact monetises this position through managed infrastructure while keeping the upstream open. With Ion Stoica's track record (Spark → Databricks, Ray → Anyscale) and a16z/Lightspeed co-leading, the institutional conviction is already validated. The $800M seed valuation is aggressive on current revenue but appropriate for a project with 2,000+ contributors and Amazon as a production customer. Risk: inference commodity pressure from NVIDIA/cloud giants building competing managed offerings.

**What validated this score:** The round closed at $800M Seed — one of the largest seed rounds in history. SGLang (competitor from the same Berkeley lab) simultaneously raised at $400M. Both within 48 hours of each other. The market confirmed the thesis.

**Scoring lesson:** 
- High D score is NOT required for a Green verdict when A + C + E are all 9+
- The "no revenue" risk was overridden by the structural necessity of the product
- This is the "infrastructure standard" exception to the PMF-first rule

---

## Case 2: Hugging Face (AI Model Hub & Open-Source Platform)

**Status at evaluation (2023):** Series D raise  
**Outcome:** $235M Series D @ $4.5B valuation; investors include Google, Amazon, NVIDIA, Salesforce, IBM  
**2024 revenue:** $130M ARR (up from $70M in 2023)  
**Use this case as the anchor for: 8.5-9.0 scores — what successful open-source commercialisation looks like at scale**

### Background

Hugging Face started as a chatbot in 2016, found product-market fit in 2018 by open-sourcing its Transformers library. Has since become the "GitHub of AI" — hosting 500,000+ models, 250,000+ datasets, 250,000+ apps. Commercial model: freemium hub ($0) + Pro plans ($9/month) + Enterprise Hub (custom) + Inference API usage billing.

### Scores

| Dimension | Score | Key Evidence |
|-----------|-------|-------------|
| A. Open-Source Ecosystem | 9.0/10 | Transformers library: 130,000+ GitHub stars; 1M+ repositories on the Hub; community contributions from virtually every AI lab; datasets and models cross-contributed by Google, Meta, Microsoft; no single governance body but network effects create own lock-in |
| B. Team & Globalisation | 8.5/10 | Clément Delangue (CEO), Julien Chaumond (CTO), Thomas Wolf (CSO) — all French founders with genuine US market penetration; CEO testified before US Congress on AI; 10,000 paying enterprise customers including Intel, Pfizer, Bloomberg; HQ Brooklyn, NY |
| C. Technical Moat | 8.5/10 | L2-L3: Transformers library is an engineering standard; model hub creates network effects (more models → more users → more models); hub-as-infrastructure moat is similar to npm/PyPI but for AI; differentiation is ecosystem, not single algorithm |
| D. Commercialisation | 8.5/10 | $130M ARR (2024); 5× YoY growth; product subscription dominant (not PS); 10,000+ paying customers; enterprise plan with SaaS + on-prem options; gross margin estimated >70%; inbound-heavy (community drives trial) |
| E. Exit Path | 8.0/10 | IPO most likely path (CEO has publicly expressed desire); M&A also credible: Salesforce, Google, Microsoft each have strategic rationale; $4.5B valuation implies ~35× ARR multiple — aggressive but defensible given growth rate and network effects |

**Total: 8.5/10 → 🟢 Strongly Recommend**

**Hard Veto Check:** None triggered.

**IC Thesis:** Hugging Face has done what most open-source companies fail at: converted a free community into a sustainable enterprise revenue engine without destroying the community in the process. $130M ARR growing at 86% YoY, with Google/Amazon/NVIDIA as both investors and distribution partners, creates a flywheel that is extremely hard to displace. The risk is that cloud providers (who are all investors) vertically integrate model hosting and marginalise the independent hub. But the model diversity and community trust Hugging Face has built is a moat that took 5+ years to accumulate.

**What this case teaches:**
- Open Core → Hub-as-Platform is a distinct and highly valuable commercialisation model in AI
- Strategic investors (NVIDIA, Google, Amazon) as round participants are both validation AND risk mitigation — they reduce the chance these companies build competing infrastructure
- Revenue multiple of 100× ARR at Series D is only justifiable when growth rate ≥80% AND network effects are demonstrably compounding

---

## Calibration Summary: The Scoring Scale

| Score | Verdict | Real-World Anchor |
|-------|---------|------------------|
| 9.5 | 🟢 Strongly Recommend — Category Standard | vLLM post first paid managed service contract |
| 8.5 – 9.0 | 🟢 Strongly Recommend | vLLM / Inferact at Seed (8.9) and Hugging Face at Series D (8.5) — strong infrastructure / product ARR anchors |
| 8.0 – 8.4 | 🟢 Strongly Recommend | Early-stage high-signal project with a clear commercialisation path |
| 7.0 – 7.9 | 🟡 Recommend with Conditions | Strong project, one structural gap to fix; milestone-linked term sheet |
| 5.5 – 6.9 | 🟠 Watch / Track | Real assets, premature for investment; re-evaluate in 6-9 months |
| < 5.5 | 🔴 Pass | Hard veto or multiple critical failures |

**How to use these anchors when scoring new projects:**

Ask: "Is this project's open-source community health closer to vLLM (9.5) or to an early-stage project with 200 stars and 3 contributors (3.0)?" Score relative to these anchors, not in absolute terms.
