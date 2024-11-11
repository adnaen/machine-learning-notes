# Precision Score

Precision is the ratio of `number of True Positive` to the `total number of Predicted Positive`.
It measures, out of the total predicted positive, how many are actually positive.

$$\\text{Precision Score} = \frac{\text{No.of True Positive}}{\text{No.of True Positive + No.of False Positive}} \times 100\$$

Let's say

- Number of TP = 140
- Number of TP + FP = 140+50 = 190
- $$\\text{Precision Score} = \frac{140}{190} \times 100 = 73.7\%\$$

```python
from sklearn.metrics import precision_score

# Example predictions
y_true = [1, 0, 1, 1, 0, 1, 0, 1]  # True labels
y_pred = [1, 0, 0, 1, 0, 1, 1, 1]  # Predicted labels

# Calculate precision
precision = precision_score(y_true, y_pred) * 100
print(f"Precision Score: {precision:.2f}%")

```
