# Gradient Descent

Gradient Descent is a optimization algorithm used for minimizing the cost function in various machine learning algorithms, It is used for updating the parameters of the learning model.

![gradient descent](../../assets/gradient_descent.jpeg)

Where:

- $w$ : Weight
- $Cost$ : A.K.A Loss
- Learning Step ($\alpha$) : Learning Rate

## **How Gradient Descent Works**

1. **Calculate Gradients**: Compute the partial derivatives of the loss function with respect to the weights ($w$) and bias ($b$).
2. **Update Parameters**: Adjust the weights and bias by moving in the direction opposite to the gradient to reduce the loss.

### Equation

- **For weights ($w$):**

  $$
  w = w - \alpha \cdot dw
  $$
  Where:
  $$
  dw = (\hat{y} - y) \cdot x
  $$

- **For bias ($b$):**
  $$
  b = b - \alpha \cdot db
  $$
  Where:
  $$
  db = \hat{y} - y
  $$

#### **Where**

- $w$: Current weight.  
- $b$: Current bias.  
- $\alpha$: Learning rate (controls how large the parameter updates are).  
- $dw$: Gradient of the loss with respect to $w$.  
- $db$: Gradient of the loss with respect to $b$.  
- $x$: Input feature.  
- $y$: True label.  
- $\hat{y}$: Predicted probability.  
