# Machine Learning Projects in Stealth

Machine learning notebooks from my internship and project work at Stealth.

## Task 2203: original → mentor feedback → revision

| Stage | Files |
| --- | --- |
| Original submission | [model_optimation.ipynb](model_optimation.ipynb), preserved with its original saved outputs. |
| Mentor feedback | [Full transcription](feedback/task-2203-mentor-feedback.md) and [original screenshot](feedback/task-2203-mentor-feedback.png). |
| Revised version | [Executed notebook](revised/model_optimation_revised.ipynb), [HTML export](revised/model_optimation_revised.html), and [revision notes and run instructions](revised/README.md). |
| Revised results | [Summary](revised/artifacts/results_summary.md) and [figures and tables](revised/artifacts/). |

The revision addresses the feedback with additional visualizations, a 25% test-split check, explicit error analysis, and fixes to preprocessing and tuning. Results are reported as observed, without assuming tuning always improves performance.

## Original project notebooks

| Notebook | Project |
| --- | --- |
| [Model Optimization Pipeline.ipynb](Model%20Optimization%20Pipeline.ipynb) | Text classification on four categories from 20 Newsgroups using TF-IDF and LinearSVC. Compares grid, random, and Bayesian searches with Ray Tune, including cross-validation, metrics, runtime comparisons, and visualizations. |
| [model_optimation.ipynb](model_optimation.ipynb) | Logistic regression on scikit-learn's Breast Cancer Wisconsin dataset, with standardization, GridSearchCV, and a baseline-versus-tuned accuracy comparison. |

## Tools and data

- Python, Jupyter Notebook, NumPy, pandas, Matplotlib, and scikit-learn.
- Text classification additionally uses Ray Tune and HyperOpt.
- 20 Newsgroups downloads through scikit-learn if not cached. Breast-cancer data ships with scikit-learn.
- The revised logistic-regression notebook has its own [requirements](revised/requirements.txt) and [recorded environment](revised/artifacts/environment.json).

## Original notebook status

Both root-level notebooks retain their original code, saved outputs, and plots. They were not rerun during upload; their saved results are historical records.

The original logistic-regression notebook has a training-variable naming mismatch. It remains as submitted; this is fixed in the separate revision. The text-classification notebook has not been revised as part of Task 2203.
