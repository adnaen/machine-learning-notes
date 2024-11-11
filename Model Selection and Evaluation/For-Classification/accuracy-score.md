# Accuracy Score

Accuracy Score is the ratio between the `number of correct prediction` to the `number of prediction`
Is a evaluation metric for `Classification Models`

$$\\text{Accuracy Score} = \frac{\text{Number of Correct Predictions}}{\text{Number of Predictions}} \times 100\$$

Let's say

- Number of correct prediction = 128
- Number of total prediction = 170
- $$\\text{Accuracy Score} = \frac{128}{170} \times 100 = 75.3\%\$$

```python
from sklearn.metrics import accuracy_score

# Example predictions
y_true = [1, 0, 1, 1, 0, 1, 0, 1]  # True labels
y_pred = [1, 0, 0, 1, 0, 1, 1, 1]  # Predicted labels

# Calculate accuracy
accuracy = accuracy_score(y_true, y_pred) * 100
print(f"Accuracy Score: {accuracy:.2f}%")

```

> cons: Accuracy Score is not reliable when the dataset has uneven distribution of classes
