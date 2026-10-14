# W10 Score Authority Resolution

Date: **2026-10-14**. This follow-up resolves the five README/case conflicts identified in the P1 review. It does not change v1.4 weights, thresholds, or the meaning of any outcome field.

## Decisions

| Project | Authority | A–E vector | Exact weighted total | Public canonical action |
|---|---|---|---:|---|
| LMCache | Detailed case | 8.0 / 7.0 / 8.5 / 4.5 / 7.5 | 7.125 | Change 7.78 → **7.13** |
| AReaL | Detailed case | 7.2 / 6.5 / 8.0 / 4.5 / 6.5 | 6.575 | Change 7.23 → **6.58** |
| AgentScope | AgentVC README W10 correction | 7.0 / 6.5 / 6.5 / 7.0 / 6.5 | 6.725 | Retain **6.73** |
| Hermes Agent | AgentVC README W10 correction | 6.5 / 7.0 / 6.0 / 5.5 / 6.5 | 6.300 | Retain **6.30** |
| DeerFlow | AgentVC README W10 correction | 7.0 / 6.5 / 6.5 / 6.0 / 4.0 | 6.150 | Retain **6.15** |

All exact totals use 25% / 20% / 20% / 20% / 15%. The public display rounds to two decimals.

## Source hierarchy

A detailed case is authoritative when it is the only source containing dimension-specific evidence and the official project facts support its relative strengths and weaknesses. This applies to LMCache and AReaL. Their AgentVC README vectors were later summary/backfill records without dimension-level evidence, so both README layers are synchronized to the cases.

The later AgentVC README W10 correction is authoritative for AgentScope, Hermes Agent and DeerFlow because it is a signed, same-batch `update README with correct scorecard data and charts` record, it is retained by the downstream Scorecard README, and it is consistent across later backfills. Their original case files were initial narrative drafts. The case files are synchronized to the public W10 vectors; Hermes also required an object-identity correction from `hermes-function-calling` to `hermes-agent`.

## Scope of the correction

The case repository PR updates five case files and the two AgentVC W10 aggregate displays affected by the case-authoritative decisions. The Scorecard PR synchronizes the public aggregate table, historical outcome dataset, P1 audit report, data dictionary and changelog. No new evidence is used to re-score unrelated projects, and no outcome is changed by this authority pass.

## Evidence

- [LMCache case](https://github.com/lucy-cxy/agentvc-index/blob/main/cases/2026-03-08_lmcache.md), [AgentVC W10 README](https://github.com/lucy-cxy/agentvc-index/blob/main/README.md), [case edit history](https://github.com/lucy-cxy/agentvc-index/commit/e41e2ed4a4a90e5189382f8e76366cff96dc5092).
- [AReaL case](https://github.com/lucy-cxy/agentvc-index/blob/main/cases/2026-03-08_areal.md), [AgentVC W10 README](https://github.com/lucy-cxy/agentvc-index/blob/main/README.md), [historical project README](https://raw.githubusercontent.com/areal-project/AReaL/b48b013945f505d9cabb8e19c84efed9fb4330cb/README.md).
- [AgentScope case](https://github.com/lucy-cxy/agentvc-index/blob/main/cases/2026-03-08_agentscope.md), [AgentVC correction commit](https://github.com/lucy-cxy/agentvc-index/commit/9ff5b53b2637f4fdad695c9ef107cbd18fa8aef7), [historical AgentScope README](https://raw.githubusercontent.com/agentscope-ai/agentscope/66b475ba124b8b1edba17ebed9281941d809f0cb/README.md).
- [Hermes Agent case](https://github.com/lucy-cxy/agentvc-index/blob/main/cases/2026-03-08_hermes-agent.md), [AgentVC correction commit](https://github.com/lucy-cxy/agentvc-index/commit/9ff5b53b2637f4fdad695c9ef107cbd18fa8aef7), [Hermes Agent repository](https://github.com/NousResearch/hermes-agent).
- [DeerFlow case](https://github.com/lucy-cxy/agentvc-index/blob/main/cases/2026-03-08_deer-flow.md), [AgentVC correction commit](https://github.com/lucy-cxy/agentvc-index/commit/9ff5b53b2637f4fdad695c9ef107cbd18fa8aef7), [DeerFlow repository](https://github.com/bytedance/deer-flow).
