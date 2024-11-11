# F1 Score

F1 Score is an important evaluation metric for binary classification that combines Precision & Recall.
F1 Score is the Harmonic Mean of Precision & Recall

$$\\text{F1 Score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision + Recall}} \$$

```python
from sklearn.metrics import f1_score

# Example predictions
y_true = [1, 0, 1, 1, 0, 1, 0, 1]  # True labels
y_pred = [1, 0, 0, 1, 0, 1, 1, 1]  # Predicted labels

# Calculate f1 score 
f1 = f1_score(y_true, y_pred) * 100
print(f"f1 Score: {recall:.2f}%")

```

> Useful when dataset has imbalanced classes
