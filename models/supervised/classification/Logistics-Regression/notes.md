# 🧠 Maths Behind Logistic Regression

###  ➡️ **Linear Equation**

#### $${z = w \cdot x + b}$$

- where:
  - $z$ is known as logits / Weighted sum in the context of Logistic Regression
  - $w$ is the weight of the features (a.k.a model coefficients),
  - $x$ is the feature (input data),
  - $b$ is the bias term (a.k.a model intercept) .

### ➡️ **Activation Functions**

**Sigmoid**

$$\hat{y} = \frac{1}{1 + e^{-z}}$$

- where:
  - $\hat{y}$ is the predicted probability of the class.
  - Here, we transform logits into probability.
  - The output of the sigmoid function will always be between 0 and 1, which makes it interpretable as a probability.

**Softmax**

$$\hat{y}_i = \frac{e^{z_i}}{\sum_{j} e^{z_j}}$$

- Where:
  - $\hat{y}_i$ is the predicted probability for the class $i$.
  - The softmax function transforms the logits for each class into probabilities.
  - The sum of the probabilities for all classes will always be 1, making them interpretable as a probability distribution over the classes.

### ⚙️ **Workflow**

1. **Initialize Model Parameters**
   - Set the **learning rate** (e.g., 0.01) and **number of epochs**.
   - Initialize **weights** and **bias** to small random values or zeros.

2. **Forward Propagation**
   - Calculate the **logits/Weighted Sum**.
   - **For binary classification**: Apply the **sigmoid** function to transform the logits into probabilities
   - **For multi-class classification**: Apply the **softmax** function to transform the logits into probabilities:

4. **Backward Propagation**
   - Compute the **gradients** of the appropriate loss function with respect to the weights ($w$) and bias ($b$).
   - Update current model Parameters such as Weight and Bias
5. **Repeat Steps 2–5**
   - Iterate through the forward and backward propagation steps for the specified number of epochs or until convergence (when the loss stops decreasing significantly).

6. **Prediction**
   - After training, use the learned weights and bias to predict probabilities for new data.
   - **For binary classification**: Apply a threshold (e.g., $\hat{y} > 0.5$) to classify probabilities into discrete class labels (0 or 1).
   - **For multi-class classification**: Choose the class with the highest probability as the predicted class.
