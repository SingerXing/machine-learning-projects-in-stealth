# Machine Learning Projects in Stealth

Machine learning notebooks from my internship and project work at Stealth.

| Notebook | Project |
| --- | --- |
| [Model Optimization Pipeline.ipynb](Model%20Optimization%20Pipeline.ipynb) | Text classification on four categories from the 20 Newsgroups dataset using TF-IDF and LinearSVC. Compares grid, random, and Bayesian hyperparameter searches with Ray Tune, including cross-validation, evaluation metrics, runtime comparisons, and visualizations. |
| [model_optimation.ipynb](model_optimation.ipynb) | Logistic regression on scikit-learn's Breast Cancer Wisconsin dataset, with feature standardization, GridSearchCV, and a baseline-versus-tuned accuracy comparison. |

## Tools and data

- Python, Jupyter Notebook, NumPy, pandas, Matplotlib, and scikit-learn.
- The text-classification notebook also uses Ray Tune and HyperOpt.
- The 20 Newsgroups dataset is downloaded through scikit-learn when it is not already cached. The breast-cancer dataset is included with scikit-learn.

## Notebook status

These are the original notebooks, including their saved outputs and plots. They were not rerun during this upload, and the saved results have not been independently reproduced.

The original `model_optimation.ipynb` has a variable-name mismatch: it defines `x_train_scaled` but later references `X_train_scaled`. That needs to be corrected before a fresh top-to-bottom run. The notebook is preserved here as submitted.

