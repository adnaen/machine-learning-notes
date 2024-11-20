# Mean Square Error (MSE)

The **Mean Squared Error (MSE)** is a metric that evaluates how well a model's predictions match the actual values. It calculates the average of the squared differences between the actual values ($y_i$) and predicted values ($\hat{y}_i$).

**Formula:**
$$\text{MSE} = \frac{1}{n} \sum_{i=1}^n \left( y_i - \hat{y}_i \right)^2$$

Where:

- $n$ = Number of data points
- $y_i$ = Actual value for the $i$-th data point
- $\hat{y}_i$ = Predicted value for the $i$-th data point

How to Interpret MSE

- A **lower MSE** indicates that the model's predictions are closer to the actual values.
- A **higher MSE** indicates that the model's predictions are farther from the actual values.

## **Python Implementation**

```python
from sklearn.metrics import mean_squared_error

x = [10, 20, 30, 40, 50]
y_true = [4232, 5342, 5634, 6353, 7534]
y_pred = [4250, 5360, 5690, 6340, 7534]

MSE = mean_squared_error(y_true, y_pred)
print("MSE is: ", MSE)
```

**output**

```bash
MSE is: 790.6
```
