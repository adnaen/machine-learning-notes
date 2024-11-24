# Maths Behind Logistic Regression

### Understand the Sigmoid Function

<img src="../../../../assets/sigmoid-function.png" width="600x" height="400px" />

$$\{z = w \cdot x + b}\$$

- where:
  - w is the weight vector (model coefficients),
  - x is the feature vector (input data),
  - b is the bias term.

<hr>

$$\{\text{Sigmoid Function } \hat{y} = \frac{1}{1 + e^{-z}}}\$$

- where:
  - y^ is the predicted probability of the positive class (class 1).
  - The output of the sigmoid function will always be between 0 and 1, which makes it interpretable as a probability.

Weights = Feature Importance: Larger weights indicate stronger influence on the prediction
