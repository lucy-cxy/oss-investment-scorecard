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
