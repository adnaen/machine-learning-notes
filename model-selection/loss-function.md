# Loss Function

$$
L(\theta) = \frac{1}{m} \sum_{i=1}^{m} \mathcal{L}(y^{(i)}, \hat{y}^{(i)})
$$

Where:

- \( m \) is the number of training examples.
- \( y^{(i)} \) is the true value (target) for the \( i \)-th sample.
- \( \hat{y}^{(i)} \) is the predicted value for the \( i \)-th sample.
- \( \mathcal{L}(y^{(i)}, \hat{y}^{(i)}) \) is the **loss** for the \( i \)-th example, which can vary depending on the problem (e.g., squared error, absolute error, etc.).

. Loss function measures how far an estimated value is from its true value.
. The official term for this numerical quantification is the prediction error.
. It is helpful to determine which model performs better & which parameters are better

## Mean Square Error (MSE) / L2 Loss

| Loss Function                          | Applicability to Classification | Applicability to Regression |
|----------------------------------------|---------------------------------|-----------------------------|
| Mean Square Error (MSE) / L2 Loss      | ✖️                               | ✔️                          |
| Mean Absolute Error (MAE) / L1 Loss    | ✖️                               | ✔️                          |
| Binary Cross-Entropy Loss / Log Loss   | ✔️                               | ✖️                          |
| Categorical Cross-Entropy Loss         | ✔️                               | ✖️                          |
| Hinge Loss                             | ✔️                               | ✖️                          |
| Huber Loss / Smooth Mean Absolute Error| ✖️                               | ✔️                          |
| Log Loss                               | ✔️                               | ✖️                          |
