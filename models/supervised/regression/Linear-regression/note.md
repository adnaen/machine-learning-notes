# Maths Behind Linear Regression

### Linear Equation

#### $${z = w \cdot x + b}$$

- where:
  - $z$ is known as logits / Weighted sum in the context of Linear Regression
  - $w$ is the weight of the features (a.k.a model coefficients),
  - $x$ is the feature (input data),
  - $b$ is the bias term (a.k.a model intercept) .

### Activation Functions

#### Sigmoid

##### $${\hat{y} = \frac{1}{1 + e^{-z}}}$$

- where:
  - $\hat{y}$ is the predicted probability of the class.
  - Here, we transform logits into probability.
  - The output of the sigmoid function will always be between 0 and 1, which makes it interpretable as a probability.

#### Softmax Activation Function

##### $$\hat{y}_i = \frac{e^{z_i}}{\sum_{j} e^{z_j}}$$

- Where:
  - $\hat{y}_i$ is the predicted probability for the class $i$.
  - The softmax function transforms the logits for each class into probabilities.
  - The sum of the probabilities for all classes will always be 1, making them interpretable as a probability distribution over the classes.

### Workflow

1. **Initialize Model Parameters**
   - Set the **learning rate** (e.g., 0.01) and **number of epochs**.
   - Initialize **weights** and **bias** to small random values or zeros.

2. **Forward Propagation**
   - Calculate the **logits**
   - **For binary classification**: Apply the **sigmoid** function to transform the logits into probabilities:

   - **For multi-class classification**: Apply the **softmax** function to transform the logits into probabilities:

3. **Compute Loss**
   - **For binary classification**: Use **binary cross-entropy** loss:

   - **For multi-class classification**: Use **categorical cross-entropy** loss:

4. **Backward Propagation**
   - Compute the **gradients** of the loss function with respect to the weights (\( w \)) and bias (\( b \)).
     - For **binary classification**:

     $$
     \frac{\partial \text{Loss}}{\partial w} = \hat{y} - y
     $$

     $$
     \frac{\partial \text{Loss}}{\partial b} = \hat{y} - y
     $$

     - For **multi-class classification**, the gradient for the softmax output would be:

     $$
     \frac{\partial \text{Loss}}{\partial w_i} = \hat{y}_i - y_i
     $$

     $$
     \frac{\partial \text{Loss}}{\partial b_i} = \hat{y}_i - y_i
     $$

5. **Update Parameters**
   - Use **gradient descent** to update the weights and bias:
     - For weights:

     $$
     w = w - \alpha \cdot \frac{\partial \text{Loss}}{\partial w}
     $$

     - For bias:

     $$
     b = b - \alpha \cdot \frac{\partial \text{Loss}}{\partial b}
     $$

     where:
     - \( \alpha \) is the learning rate,
     - \( \frac{\partial \text{Loss}}{\partial w} \) is the gradient with respect to the weights,
     - \( \frac{\partial \text{Loss}}{\partial b} \) is the gradient with respect to the bias.

6. **Repeat Steps 2–5**
   - Iterate through the forward and backward propagation steps for the specified number of epochs or until convergence (when the loss stops decreasing significantly).

7. **Prediction**
   - After training, use the learned weights and bias to predict probabilities for new data.
   - **For binary classification**: Apply a threshold (e.g., \( \hat{y} > 0.5 \)) to classify probabilities into discrete class labels (0 or 1).
   - **For multi-class classification**: Choose the class with the highest probability as the predicted class.
