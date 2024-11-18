# Mean Absolute Error (MAE)

**Mean Absolute Error (MAE)** is an evaluation metric used to measure the average magnitude of errors between predicted values and actual values. Unlike MSE, MAE does not square the errors, so it treats all differences linearly. It is less sensitive to outliers compared to MSE.

**Formula:**
$$\text{MAE} = \frac{1}{n} \sum_{i=1}^n \left| y_i - \hat{y}_i \right|$$

Where:

- $n$ = Number of data points
- $y_i$ = Actual value for the $i$-th data point
- $\hat{y}_i$ = Predicted value for the $i$-th data point
- $|y_i - \hat{y}_i|$ = Absolute error (difference between actual and predicted values)

```python
from sklearn.metrics import mean_absolute_error

x = [10, 20, 30, 40, 50]
y_true = [4232, 5342, 5634, 6353, 7534]
y_pred = [4250, 5360, 5690, 6340, 7534]

MAE = mean_absolute_error(y_true, y_pred)
print("MAE is: ", MAE)
```

**output**

```bash
MAE is: 21.0
```
