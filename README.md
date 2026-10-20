# Machine Learning Projects in Stealth

Machine learning notebooks from my internship and project work at Stealth.

## Task 2203: original → mentor feedback → revision

| Stage | Files |
| --- | --- |
| Original submission | [model_optimation.ipynb](model_optimation.ipynb), preserved with its original saved outputs. |
| Mentor feedback | [Written feedback](feedback/task-2203-mentor-feedback.md). |
| Revised version | [Executed notebook](revised/model_optimation_revised.ipynb), [HTML export](revised/model_optimation_revised.html), and [revision notes and run instructions](revised/README.md). |
| Revised results | [Summary](revised/artifacts/results_summary.md) and [figures and tables](revised/artifacts/). |

The revision addresses the feedback with additional visualizations, a 25% test-split check, explicit error analysis, and fixes to preprocessing and tuning. Results are reported as observed, without assuming tuning always improves performance.

## Task 2210: original → mentor feedback → revision

| Stage | Files |
| --- | --- |
| Original submission | [Model Optimization Pipeline.ipynb](Model%20Optimization%20Pipeline.ipynb), preserved with its original saved outputs. |
| Mentor feedback | [Written feedback from July 27, 2026](feedback/task-2210-mentor-feedback.md). |
| Revised version | [Notebook](revised/task-2210/model_optimization_pipeline_revised.ipynb), [HTML export](revised/task-2210/model_optimization_pipeline_revised.html), and [revision notes](revised/task-2210/README.md). |
| Revised results | [Figures and tables](revised/task-2210/artifacts/). |

This revision makes the resource budget consistent across Grid, Random, and Bayesian search and adds controlled search-space sensitivity analysis. Search choices use cross-validation; test results and timings are reported with their limitations.

## Original project notebooks

| Notebook | Project |
| --- | --- |
| [Model Optimization Pipeline.ipynb](Model%20Optimization%20Pipeline.ipynb) | Text classification on four categories from 20 Newsgroups using TF-IDF and LinearSVC. Compares grid, random, and Bayesian searches with Ray Tune, including cross-validation, metrics, runtime comparisons, and visualizations. |
| [model_optimation.ipynb](model_optimation.ipynb) | Logistic regression on scikit-learn's Breast Cancer Wisconsin dataset, with standardization, GridSearchCV, and a baseline-versus-tuned accuracy comparison. |

## Tools and data

- Python, Jupyter Notebook, NumPy, pandas, Matplotlib, and scikit-learn.
- Text classification additionally uses Ray Tune and HyperOpt.
- 20 Newsgroups downloads through scikit-learn if not cached. Breast-cancer data ships with scikit-learn.
- Both revisions include pinned dependencies and recorded execution environments: [logistic regression](revised/README.md) and [text-classification optimization](revised/task-2210/README.md).

## Original notebook status

Both root-level notebooks retain their original code, saved outputs, and plots. They were not rerun during upload; their saved results are historical records.

The original logistic-regression notebook has a training-variable naming mismatch. It remains as submitted; this is fixed in the separate revision. The separate Task 2210 revision addresses the feedback on the text-classification project.
