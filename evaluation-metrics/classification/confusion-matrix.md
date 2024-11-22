# Confusion Matrix

Confusion Matrix is a matrix used for evaluating the performance of a `Classification Model`
It give more information than Accuracy Score

|                | Predicted Positive | Predicted Negative |
|----------------|--------------------|--------------------|
| **Actual Positive** | True Positive **(TP)** | False Negative **(FN)** |
| **Actual Negative** | False Positive **(FP)** | True Negative **(TN)** |

- **TP (True Positive)**: The model correctly predicted the positive class.
- **TN (True Negative)**: The model correctly predicted the negative class.
- **FP (False Positive)**: The model incorrectly predicted the positive class (also called a "Type I error").
- **FN (False Negative)**: The model incorrectly predicted the negative class (also called a "Type II error").

**TP + TN = Correct Predictions**
**FP + FN = Wrong Predictions**

```python
from sklearn.metrics import confusion_matrix

y_true = [1, 0, 1, 1, 0, 1, 0, 1]  # True labels
y_pred = [1, 0, 0, 1, 0, 1, 1, 1]  # Predicted labels

# Calculate accuracy
TN, FP, FN, TP = confusion_matrix(y_true, y_pred).ravel()
print(f"{TN=}, {TP=}, {FP=}, {FN}")

```
