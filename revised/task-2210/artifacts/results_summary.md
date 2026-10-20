### Task 2210 — observed benchmark results

All 288 trials completed: 32 configurations × 3 strategies × 3 search seeds. Every trial used the same five training folds, one Ray CPU, one concurrent trial, and a one-thread numerical-library limit.

- Baseline training-CV macro F1: **0.7622**; existing-test macro F1: **0.7364**.
- Primary seed 42 strategy selected by training CV: **Bayesian**, CV macro F1 **0.7739**; existing-test macro F1 **0.7428**.
- Its observed test difference from baseline is **+0.0064 macro F1**. This is a descriptive comparison on the previously inspected test benchmark.

| Strategy | Best CV F1, mean ± SD across 3 search seeds | Search wall seconds, mean ± SD | Existing-test F1 range |
| --- | --- | --- | --- |
| Grid | 0.7717 ± 0.0000 | 135.1 ± 1.2 | 0.7395–0.7395 |
| Random | 0.7732 ± 0.0002 | 125.5 ± 5.4 | 0.7404–0.7423 |
| Bayesian | 0.7724 ± 0.0043 | 132.1 ± 17.8 | 0.7401–0.7518 |

SD describes three proposal-seed runs; it is not a confidence interval. Grid scores are repeated deterministic evaluations of one exhaustive grid. No strategy or seed was selected by its test score. Equal trial/concurrency budgets do not mean equal runtime or identical C spaces. Fixed-fold selection optimism, previously seen test data, and machine-dependent timing prevent a general claim that one strategy is best.
