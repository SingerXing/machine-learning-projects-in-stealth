# Task 2210 — revised model optimization pipeline

This revision preserves the original TF-IDF + LinearSVC project and responds to the [mentor feedback](../../feedback/task-2210-mentor-feedback.md). The [original notebook](../../Model%20Optimization%20Pipeline.ipynb) remains unchanged.

## Read the work

- [Revised notebook](model_optimization_pipeline_revised.ipynb): code, design rationale, results, and plots.
- [HTML export](model_optimization_pipeline_revised.html): download and open locally without Jupyter.
- [Observed-results summary](artifacts/results_summary.md).
- [Artifacts](artifacts/): trial-level fold scores, actual completion order, elapsed times, CV-selected configurations, test predictions, controlled grid comparisons, figures, and the execution environment.

## What changed

1. Made search RNG seeds explicit, kept CV/model seeds fixed, and repeated all three strategies with search seeds 42, 43, and 44.
2. Matched concurrency at one trial and one Ray CPU, limited numerical-library threads, and rotated strategy order.
3. Recorded actual trial completion order and elapsed search time, separating wall time from time spent inside CV.
4. Selected configurations and the primary-seed strategy using CV, rather than choosing a strategy by its test score.
5. Used paired contrasts and a balanced interaction display from the complete grid for parameter analysis.
6. Replaced a hard-coded winner with conclusions generated from the observed run.

The budget is 32 full five-fold evaluations per strategy per seed: **288 trials and 1,440 CV model fits**, plus the baseline and final models. Runtime depends on hardware and Ray overhead. Completed trials are saved immediately; each search also updates aggregate CSVs. Raw Ray logs are written outside the repository to a temporary run directory. This notebook starts a new benchmark rather than silently resuming a partial run.

## Reproduce

Use Python 3.13.9 and the pinned [requirements](requirements.txt). From this directory in an isolated environment:

~~~bash
python -m pip install -r requirements.txt
jupyter nbconvert --to notebook --execute --inplace --ExecutePreprocessor.timeout=7200 model_optimization_pipeline_revised.ipynb
jupyter nbconvert --to html --embed-images model_optimization_pipeline_revised.ipynb
~~~

The public 20 Newsgroups corpus is loaded from the normal scikit-learn cache (`SCIKIT_LEARN_DATA` or `~/scikit_learn_data`) and downloaded only if absent. The notebook exports hashes and labels rather than document text. It requires permission to start local Ray processes and sockets. Run in a fresh kernel with no existing Ray session.

## Interpretation

All strategies use identical folds and equal trial/concurrency budgets. Grid C values are discrete; random and TPE C values are continuous. The test split was examined in the original notebook and is a descriptive benchmark here, not a new untouched validation set. Three search seeds measure limited search randomness on fixed folds; they do not support significance tests or broad claims of a universal winner. Original and revised timing figures use different execution setups and should not be treated as a controlled speedup comparison.
