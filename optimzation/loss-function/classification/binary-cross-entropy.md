# Binary Cross Entropy (Log Loss)

- Binary Cross Entropy is the negative average of the log of corrected predicted probabilities.
- This is used when dealing with binary classification problems

**Formula:**

$$
\text{BCE Loss} = - \frac{1}{n} \sum_{i=1}^{n} \left[ y_i \cdot \log(\hat{y}_i) + (1 - y_i) \cdot \log(1 - \hat{y}_i) \right]
$$

Where:

- $y_i$ is the actual label of the $i^{th}$ sample (0 or 1).
- $\hat{y}_i$ is the predicted probability of the sample belonging to class 1 (output of the sigmoid function).
- $n$ is the number of samples.

## **Python Implementation**

```python
from sklearn.metrics import log_loss

y_true = [0, 1, 0, 1, 1, 1]
y_prob = [0.9, 0.3, 0.8, 0.6, 0.8, 0.5]

BSE = log_loss(y_true, y_prob)
print("BSE is: ", BSE)

```

## **Output**

```bash
BSE is 1.0905186942323712
```
