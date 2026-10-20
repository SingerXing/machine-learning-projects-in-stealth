### Observed results

- **Primary held-out accuracy:** baseline 96.49%; tuned 98.25% (+1.75 percentage points).
- **Primary malignant recall:** baseline 92.86%; tuned 95.24%.
- **Missed malignant cases:** baseline 3; tuned 2, among 42 malignant test observations.
- **Nested-CV mean accuracy on the primary training partition:** baseline 97.14%; tuned procedure 96.70%. Fold standard deviations are in the development table.

### Interpretation limits

The dataset and test samples are small. These experiments do not demonstrate a general advantage for tuning, and the 25% split does not establish stability across datasets or seeds. Accuracy-based selection can prefer a configuration that does not maximize malignant recall. Threshold selection, probability calibration, repeated evaluation, and external validation would need separate development and validation plans. Coefficients describe the fitted model and do not establish causal effects.
