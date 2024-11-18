# Mean Square Error (MSE)

The **Mean Squared Error (MSE)** is a metric that evaluates how well a model's predictions match the actual values. It calculates the average of the squared differences between the actual values ($y_i$) and predicted values ($\hat{y}_i$).

**Formula:**
$$\text{MSE} = \frac{1}{n} \sum_{i=1}^n \left( y_i - \hat{y}_i \right)^2$$

Where:

- $n$ = Number of data points
- $y_i$ = Actual value for the $i$-th data point
- $\hat{y}_i$ = Predicted value for the $i$-th data point

#### How to Interpret MSE

- A **lower MSE** indicates that the model's predictions are closer to the actual values.
- A **higher MSE** indicates that the model's predictions are farther from the actual values.

**Python Implementation**

```python
from sklearn.metrics import mean_squared_error

x = [10, 20, 30, 40, 50]
y_true = [4232, 5342, 5634, 6353, 7534]

# average prediction
y_pred_av = [4250, 5360, 5690, 6340, 7534]

# good prediction
y_pred_go = [4233, 5344, 5635, 6354, 7534]

# poor prediction
y_pred_po = [4400, 5600, 5800, 6700, 7900]



SK_MSE_OF_AV = mean_squared_error(y_true, y_pred_av)
SK_MSE_OF_GO = mean_squared_error(y_true, y_pred_go)
SK_MSE_OF_PO = mean_squared_error(y_true, y_pred_po)

print(f"MSE of Average Good predic by sklearn : {SK_MSE_OF_AV}")
print(f"MSE of the Good prediction by sklearn : {SK_MSE_OF_GO}")
print(f"MSE of the Poor prediction by sklearn : {SK_MSE_OF_PO}")

```

**output**

```bash
MSE of Average Good predic by sklearn : 790.6
MSE of the Good prediction by sklearn : 1.4
MSE of the Poor prediction by sklearn : 75341.8
```
