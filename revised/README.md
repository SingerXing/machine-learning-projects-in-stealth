# Task 2203 — revised logistic regression project

This revision responds to the [mentor feedback](../feedback/task-2203-mentor-feedback.md). The [original notebook](../model_optimation.ipynb) remains unchanged.

## Read the work

- [Executed notebook](model_optimation_revised.ipynb): code, explanations, tables, and embedded plots.
- [HTML export](model_optimation_revised.html): download and open locally to read without Jupyter.
- [Results summary](artifacts/results_summary.md): generated from the executed notebook.
- [Figures and tables](artifacts/): five plots, metrics, predictions, split membership, tuning results, and environment.

## Changes made

1. Fixed the inconsistent training-variable name.
2. Put standardization inside the pipeline so each cross-validation fold fits its own scaler.
3. Used valid L1/L2 penalty and solver combinations for scikit-learn 1.7.2.
4. Made malignant the positive class explicitly and reported false-negative and false-positive counts.
5. Added confusion matrices, accuracy/F1 comparison, ROC curves, and standardized-coefficient plots.
6. Added nested cross-validation on the primary training partition to evaluate tuning with reduced selection bias.
7. Repeated the modeling recipe with a 25% test split as a descriptive sensitivity check.

Selection remains accuracy-based. The test-split experiments reuse data and are not independent validations. Test results and plots are not used to select thresholds or revise the grid. Original and revised scores are not a controlled comparison because their evaluation setups differ.

## Verification

The revised notebook was executed from a fresh kernel on October 20, 2026. All 10 code cells completed. Primary metrics were independently checked against the saved predictions, and the five plots were visually reviewed. Both original notebooks were checked against their source files.

## Reproduce

The saved run uses Python 3.13.9. The requirements file records directly used package versions; it is not a full environment lockfile. Create a separate environment, install requirements, and run from this directory. This notebook needs no external dataset download.

~~~bash
python3.13 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m ipykernel install --user --name stealth-revision --display-name "Stealth revision"
jupyter nbconvert --to notebook --execute --inplace --ExecutePreprocessor.kernel_name=stealth-revision --ExecutePreprocessor.timeout=240 model_optimation_revised.ipynb
jupyter nbconvert --to html --embed-images model_optimation_revised.ipynb
~~~

Running regenerates artifacts/. Keep scikit-learn pinned to 1.7.2 for the recorded API. Check environment changes before comparing results.
