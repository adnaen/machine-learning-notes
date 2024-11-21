# Categorical Cross Entropy

- Categorical Cross Entropy is the negative log of the predicted probability for the true class.
- This is used for multi-class classification problems where the target variable has more than two classes.

## **Formula:**

$$
\text{CCE Loss} = - \frac{1}{n} \sum_{i=1}^{n} \sum_{c=1}^{C} y_{i,c} \cdot \log(\hat{y}_{i,c})
$$

Where:

- \(y_{i,c}\) is the true label of the \(i^{th}\) sample for class \(c\) (1 if class \(c\) is the true class, otherwise 0).
- \(\hat{y}_{i,c}\) is the predicted probability of the \(i^{th}\) sample for class \(c\) (output of the softmax function).
- \(C\) is the total number of classes.
- \(n\) is the number of samples.

If we consider the true class label, we can simplify the equation to:

$$
\text{CCE Loss} = - \log(\hat{y}_{i, \text{true}})
$$

Where \(\hat{y}_{i, \text{true}}\) is the predicted probability of the true class for the \(i^{th}\) sample.

## **Python Implementation**

```python
# test data
Y_TRUE_C = [[0, 1, 0, 0],
          [0, 0, 1, 0],
          [0, 0, 0, 1],
          [1, 0, 0, 0]]

Y_PROB_C = [[0.1, 0.8, 0.05, 0.05],
          [0.1, 0.1, 0.7, 0.1],
          [0.1, 0.1, 0.2, 0.6],
          [0.9, 0.06, 0.02, 0.02]]

from sklearn.metrics import log_loss
cce = log_loss(Y_TRUE_C, Y_PROB_C)
print("CCE: ", cce)
```

## **Output**

```bash
CCE: 0.2990011586691898
```
