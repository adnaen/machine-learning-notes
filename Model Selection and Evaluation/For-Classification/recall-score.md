# Recall Score

Recall is the ratio of `No.of True Positive` to the `total No.of Actual Positive`.
It measures, out of the total actual positive, how many are predicted as True Positive

$$\\text{Recall Score} = \frac{\text{No.of True Positive}}{\text{No.of True Positive + No.of False Negative}} \times 100\$$

Let's say

- Number of TP = 160
- Number of TP + FP = 160+50 = 210
- $$\\text{Recall Score} = \frac{160}{210} \times 100 = 76.2\%\$$

```python
from sklearn.metrics import recall_score

# Example predictions
y_true = [1, 0, 1, 1, 0, 1, 0, 1]  # True labels
y_pred = [1, 0, 0, 1, 0, 1, 1, 1]  # Predicted labels

# Calculate recall
recall = recall_score(y_true, y_pred) * 100
print(f"Recall Score: {recall:.2f}%")

```
