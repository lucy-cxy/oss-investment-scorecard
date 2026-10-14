# Historical Score Outcomes Dataset

`score-outcomes.csv` is the v2.0 P0 baseline ledger for historical score reconciliation and future outcome backtesting.

## Purpose

The file keeps three score views separate instead of silently overwriting historical data:

- `recomputed_weighted_total`: calculated from the displayed A–E dimension scores using the stable v1.4 weights (25/20/20/20/15).
- `reported_case_total`: the total written in the linked case report, after the Hugging Face arithmetic correction in this P0 change.
- `canonical_score`: the score currently published in the main README evaluation table. This is the comparison value used by the public scorecard.

A row with different values is a **data-quality finding**, not permission to rewrite the historical score. `data_quality_status` records whether the row is consistent, needs arithmetic reconciliation, or has a conflict between the README canonical score and the linked case.

## Missing-data rules

- `Not observable` means the field has not been collected. It is not a zero and must not be treated as a weak result.
- `Not assessed` means the v1.1/v1.2 source did not contain the v1.4 field or the field was intentionally not scored.
- No simulated outcomes are included.
- `outcome_6m` and `outcome_12m` remain `Not observable` until the observation window is anchored to the evaluation date and supported by a source URL.
- Anchor outcomes and the Aryn retrospective acquisition are marked `Provisional`; they require date normalization or primary-source verification before predictive backtesting.

## Column groups

- **Identity and provenance:** `project_id`, `project_name`, `source_case_url`, `evaluation_date`, `evaluation_batch`, `scorecard_version_source`, `evaluation_mode`.
- **Historical score:** `dim_a` through `dim_e`, `recomputed_weighted_total`, `reported_case_total`, `canonical_score`, `canonical_verdict`, `published_verdict`.
- **v2.0 experiment fields:** `stage_profile`, `pmf_direction`. Both are intentionally unscored in P0.
- **Outcome fields:** `outcome_6m`, `outcome_12m`, `outcome_status`, `outcome_observed_at`, `outcome_evidence_url`, `outcome_confidence`.
- **Quality control:** `hard_veto`, `acqui_hire_candidate`, `data_quality_status`, `notes`.

## P0 scope

P0 initializes the ledger from the published README and linked case files. It does not backfill unverified funding, revenue, acquisition, maintenance, or failure outcomes, and it does not re-score any historical project. The next stage should reconcile the flagged rows before any v2.0 weight or PMF rule is tested against outcomes.

## P1 review fields

P1 adds explicit `score_drift_status`, `drift_finding`, and `drift_recommended_action` fields. It also separates `outcome_6m_*` and `outcome_12m_*` fields so a partial window cannot be mistaken for a mature result. `outcome_6m` and `outcome_12m` contain concise evidence summaries; the corresponding `*_evidence_urls` fields preserve the URLs used for the judgment.

The fixed P1 review date is 2026-10-14. A window marked `Window not mature` is intentionally not a negative result. A `Confirmed` outcome may describe maintenance, release, integration, adoption, funding, productization, or acquisition; it does not imply ARR or investment success unless the evidence explicitly supports that claim.

P1 recovered dimension data for WFGY and MimiClaw from their original Issues. WFGY is arithmetic-rounding consistent at 5.77 → 5.8. MimiClaw remains flagged because its disclosed dimensions recompute to 6.775 while the Issue and README show 6.9.

## Authority-resolution correction

The W10 authority pass resolved five README/case conflicts. LMCache and AReaL use the detailed cases as source of record and their public canonical aggregates are now 7.13 and 6.58. AgentScope, Hermes Agent and DeerFlow use the later AgentVC README W10 vectors; their existing canonical scores 6.73, 6.30 and 6.15 remain unchanged, and the case files are synchronized to those vectors. This is a source-of-record correction, not a v1.4 weight or threshold change.
