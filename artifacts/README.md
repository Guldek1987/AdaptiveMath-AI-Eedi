# Aggregate scientific results

The current primary results are under `Round2/`, matching the immutable source namespace. Files are copied unchanged; no metric was recalculated for this GitHub update.

| Question | Evidence |
|---|---|
| What population was supplied and selected? | [Source population](Round2/source_population_audit.csv), [cohort sparsity](Round2/round2_primary_hash_question_frequency.csv), [cohort rule](Round2/cohort_sensitivity_manifest.csv) |
| What are the calendar boundaries and timestamp ties? | [Date partitions](Round2/split_date_overlap.csv), [batch counts](Round2/timestamp_tie_audit.csv) |
| How do all nine variants compare? | [Equal-window metrics](Round2/round2_ablation_metrics.csv), [monthly metrics](Round2/round2_window_metrics.csv) |
| How much seed variability was recorded? | [Per-seed/window metrics](Round2/round2_primary_per_seed_window_metrics.csv) |
| What is the primary paired effect? | [Macro and response-weighted intervals](Round2/round2_window_macro_bootstrap.csv), [monthly intervals](Round2/round2_window_model_differences.csv) |
| Which components have evidence of added benefit? | [Ablation intervals](Round2/round2_ablation_paired_intervals.csv), [matched-control metrics](Round2/round2_recency_control_metrics.csv), [matched-control intervals](Round2/round2_recency_control_intervals.csv) |
| Why is pooled AUC a different estimand? | [Cross-window pair decomposition](Round2/round2_cross_window_pair_diagnostic.csv) |
| What is the calibration pattern? | [Monthly bins](Round2/monthly_calibration_bins15.csv), [subgroup/history calibration](Round2/frozen_subgroup_calibration.csv) |
| What does equal-budget error review retrieve? | [Entropy, 1−p and random review](Round2/frozen_equal_budget_review.csv) |
| What did the separate sequence-proxy experiment use? | [Candidate registry](candidate_registry.csv), [supporting fixed-split results](matched_information_results.csv) |

Primary AUC averages six within-month estimates after averaging seed probabilities inside each month. Per-seed metrics, pooled AUC and supporting fixed-split neural results are different estimands.

The paired intervals use 5,000 common-student bootstrap draws conditional on frozen predictions. They do not include refitting uncertainty. Calibration intercept/slope in the macro table are descriptive averages, not coefficients of a newly fitted pooled calibrator.

The subgroup and error-review files are descriptive frozen-prediction diagnostics. Error-review yield does not demonstrate educational benefit. Recorded runtime summaries remain in Notebook 06 with their warm-process measurement boundary.

Exact protocol, feature and aggregation definitions are retained in [the manifest directory](Round2/manifests/). Their internal source names are preserved for traceability. The public package intentionally excludes administrative reviewer reports, machine-specific logs and old five-window result tables.
