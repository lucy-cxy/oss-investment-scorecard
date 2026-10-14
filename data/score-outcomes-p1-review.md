# P1 Historical Score Drift and Outcome Review

P1 reviewed all 16 rows in `data/score-outcomes.csv` against their linked case source and the public README. The review date was **2026-10-14**. The five source conflicts were resolved in the authority-correction follow-up documented here; v1.4 weights and thresholds remain unchanged.

## Result counts

| Review result | Count | Meaning |
|---|---:|---|
| No drift / formatting-only rounding | 3 | vLLM / Inferact, Hugging Face, Infisical Agent Vault |
| Arithmetic mismatch | 7 | Unsloth, Hindsight, DeepAgents, TradingAgents, MimiClaw, MiroFish, Aryn |
| Resolved README / case authority conflict | 5 | LMCache, AReaL, AgentScope, Hermes Agent, DeerFlow |
| Arithmetic rounding only | 1 | WFGY; P1 recovered its dimensions and reported total from Issue #1 |

The arithmetic-mismatch rows remain flagged for a separate correction pass. The five source conflicts are now resolved: LMCache and AReaL use the detailed case vectors; AgentScope, Hermes Agent and DeerFlow use the later AgentVC README W10 vectors. Only LMCache and AReaL canonical aggregates changed.

## Outcome window status

Fifteen projects have a 6-month event record with either `Confirmed` or `Provisional` status. These are deliberately broad observable outcomes such as official releases, continued maintenance, integrations, adoption milestones, funding, productization or acquisition. They are not automatically revenue outcomes. Infisical Agent Vault has useful interim productization and maintenance signals, but its 6-month endpoint is 2026-10-25 and therefore remains `Window not mature`.

All sixteen 12-month windows are `Window not mature` as of 2026-10-14. No 12-month result is backfilled from a partial window. Where relevant, interim events are mentioned in `outcome_12m` but are not treated as final 12-month outcomes.

## Project-by-project review

| Project | Drift status | 6-month result | 12-month status | Recommended action |
|---|---|---|---|---|
| vLLM / Inferact | No drift (formatting-only decimal precision difference) | Provisional — 2026-07-16; 2026-08-12; 2026-08-26; 2026-09-14 | Window not mature — 2027-03 (month-level endpoint) | retain canonical |
| Hugging Face | No substantive drift; arithmetic rounding only | Confirmed — 2026-09-02 / 2026-09-03 | Window not mature — 2027-03 (month-level endpoint) | retain canonical |
| Unsloth | Case arithmetic mismatch | Confirmed — 2026-09-22 | Window not mature — 2027-03-23 | correct case arithmetic (later governance edit; canonical unchanged in P1) |
| LMCache | Resolved — case authoritative | Confirmed — 2026-05-27; supporting 2026-04-03, 2026-05-12, 2026-06-02 | Window not mature — 2027-03-08 | Resolved in authority correction PR |
| Hindsight | Case arithmetic mismatch | Confirmed — 2026-04-22; 2026-06-09; 2026-08-06; 2026-08-14 | Window not mature — 2027-03-23 | correct case arithmetic |
| Infisical Agent Vault | No drift | Window not mature — 2026-07-30; 2026-10-01; 2026-10-08 (interim) | Window not mature — 2027-04-25 | retain canonical |
| DeepAgents | Case arithmetic mismatch | Confirmed — 2026-05-12; 2026-07-08; 2026-07-29; 2026-08-07 | Window not mature — 2027-03-23 | correct case arithmetic (canonical unchanged in P1) |
| AReaL | Resolved — case authoritative | Confirmed — 2026-04-18; 2026-04-23; 2026-06-17; 2026-07-01; 2026-08-25 | Window not mature — 2027-03-08 | Resolved in authority correction PR |
| AgentScope | Resolved — AgentVC README authoritative | Confirmed — 2026-05-25 | Window not mature — 2027-03-08 | Resolved in authority correction PR |
| TradingAgents | Case arithmetic mismatch | Confirmed — 2026-03-29 through 2026-09-18 | Window not mature — 2027-03-23 | correct case arithmetic |
| Hermes Agent | Resolved — AgentVC README authoritative | Confirmed — 2026-08-18 | Window not mature — 2027-03-08 | Resolved in authority correction PR |
| DeerFlow | Resolved — AgentVC README authoritative | Confirmed — 2026-06-25 | Window not mature — 2027-03-08 | Resolved in authority correction PR |
| WFGY | Arithmetic rounding only | Confirmed — 2026-05-05; 2026-05-11 | Window not mature — 2027-03 (month-level endpoint) | retain canonical |
| MimiClaw | Case arithmetic mismatch | Confirmed — 2026-06-12; 2026-06-13; 2026-08-21 | Window not mature — 2027-03 (month-level endpoint) | correct case arithmetic (verify whether undisclosed unrounded scores were intended) |
| MiroFish | Case arithmetic mismatch | Confirmed — 2026-07-22 through 2026-07-23 | Window not mature — 2027-03-23 | correct case arithmetic |
| Aryn / Sycamore | Case arithmetic mismatch at 3-decimal precision; canonical unchanged after normal rounding | Confirmed — 2026-03-11; 2026-04-15; 2026-05-31 | Window not mature — 2027-02 (month-level endpoint) | correct case arithmetic (record exact 5.125; retain canonical 5.13) |

## Evidence and interpretation rules

The CSV stores evidence URLs in `outcome_6m_evidence_urls` and `outcome_12m_evidence_urls`. `Confirmed` means the dated event was verified in an opened authoritative source, usually an official release, repository, company announcement or regulatory filing. `Provisional` means the event is credible but the observation boundary, source independence or exact evaluation date is limited. `No verified event found in searched sources` is not used as evidence of failure or zero outcome.

Month-only evaluation dates are retained as month-only. Events near a six-month boundary are marked `Provisional` or excluded when the exact day could change inclusion. Pre-evaluation financing, launch and traction claims are excluded as look-ahead. Acquisition announcements are distinguished from completed acquisitions; the Hugging Face event is an announced transaction expected to close in H1 2027, while Aryn is recorded as a completed acquisition based on the reviewed sources.

## P1 follow-up decisions

1. Keep the five authority decisions and their source links in the audit trail; do not silently re-open them without new primary evidence.
2. Prepare a separate correction PR for the seven arithmetic-mismatch cases. That PR should correct case totals only where the displayed dimensions are confirmed as authoritative; it must not silently change the historical canonical score.
3. Re-open the 12-month outcome pass after the relevant windows mature. The earliest mature windows are the February 2026 Aryn retrospective around 2027-02 and the March 2026 rows around 2027-03.
