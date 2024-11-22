# Model Training Process

## **Classification Model Training Process**

1. **Initialize Parameters**:
   - Initialize model parameters (weights `w` and bias `b`) with random values or small numbers.

2. **Model Prediction (Logits)**:
   - **Calculate logits**: Compute the **weighted sum** of the input features:  
     \[
     z = w_1 x_1 + w_2 x_2 + \dots + w_n x_n + b
     \]
     where `x_i` are input features, `w_i` are corresponding weights, and `b` is the bias.

3. **Apply Activation Function**:
   - For **binary classification**, use **sigmoid** activation to convert logits to a probability:
     \[
     \hat{y} = \sigma(z) = \frac{1}{1 + e^{-z}}
     \]
   - For **multi-class classification**, use **softmax** to convert logits to probabilities for each class:
     \[
     \hat{y}_i = \frac{e^{z_i}}{\sum_j e^{z_j}}
     \]
     where `z_i` is the logit for class `i`, and the denominator sums the exponentials over all logits to ensure that probabilities sum to 1.

4. **Calculate Loss**:
   - **Binary Cross-Entropy (BCE)** for binary classification:
     \[
     L = -\left(y \log(\hat{y}) + (1 - y) \log(1 - \hat{y})\right)
     \]
   - **Categorical Cross-Entropy (CCE)** for multi-class classification:
     \[
     L = - \sum_i y_i \log(\hat{y}_i)
     \]
     where `y_i` is the one-hot encoded true label and `\hat{y}_i` is the predicted probability for class `i`.

5. **Backpropagation**:
   - Compute the **gradient** of the loss function with respect to the weights and bias.
   - This involves taking the derivative of the loss with respect to each parameter, which tells us how much the loss would change if we adjusted the parameters slightly.

6. **Update Parameters (Gradient Descent)**:
   - Update weights and bias using **gradient descent**:
     \[
     w = w - \eta \frac{\partial L}{\partial w}
     \]
     \[
     b = b - \eta \frac{\partial L}{\partial b}
     \]
     where `\eta` is the learning rate, which controls the step size.

7. **Repeat the Process**:
   - This process (steps 2-6) is repeated for **multiple iterations (epochs)** over the entire training dataset to gradually minimize the loss function.

8. **Convergence**:
   - The training process continues until the **loss function converges** (i.e., the loss stops improving significantly or reaches a minimum).

---

## **Regression Model Training Process** (e.g., Linear Regression)

1. **Initialize Parameters**:
   - Initialize model parameters (weights `w` and bias `b`) with random values or small numbers.

2. **Model Prediction**:
   - **Calculate prediction**: Compute the **weighted sum** of the input features:
     \[
     \hat{y} = w_1 x_1 + w_2 x_2 + \dots + w_n x_n + b
     \]
     where `x_i` are input features, `w_i` are corresponding weights, and `b` is the bias.

3. **Calculate Loss**:
   - **Mean Squared Error (MSE)** for regression:
     \[
     L = \frac{1}{n} \sum_{i=1}^{n} (\hat{y}_i - y_i)^2
     \]
     where `\hat{y}_i` is the predicted value and `y_i` is the true value.

4. **Backpropagation**:
   - Compute the **gradient** of the loss function with respect to the weights and bias.
   - This involves taking the derivative of the loss with respect to each parameter to determine how much each parameter should be adjusted to minimize the loss.

5. **Update Parameters (Gradient Descent)**:
   - Update weights and bias using **gradient descent**:
     \[
     w = w - \eta \frac{\partial L}{\partial w}
     \]
     \[
     b = b - \eta \frac{\partial L}{\partial b}
     \]
     where `\eta` is the learning rate.

6. **Repeat the Process**:
   - This process (steps 2-5) is repeated for **multiple iterations (epochs)** over the training dataset.

7. **Convergence**:
   - The training process continues until the **loss function converges** (i.e., the loss stops improving significantly or reaches a minimum).

---

### **Key Differences**

- In **classification**, **logits** are the raw predictions before applying an activation function.
- In **regression**, the model directly outputs continuous values, and we don’t call them logits—just the raw predicted values.

### Summary

In **regression**:

- We don't use the term **logits**. Instead, the model directly computes the weighted sum of the input features and outputs a **continuous predicted value**.
- The **loss function** is typically **Mean Squared Error (MSE)**.

In **classification**:

- The model outputs **logits** (raw values) and then applies an **activation function** (e.g., **sigmoid** or **softmax**) to convert them into probabilities.
- The **loss function** is typically **cross-entropy** (binary or categorical).

This distinction helps clarify the difference between how predictions are made in regression and classification.

---

## **Key Differences Between Classification and Regression**

- **Model Output**:
  - In **classification**, the model outputs **probabilities** (via **sigmoid** or **softmax**) after calculating the logits.
  - In **regression**, the model directly outputs **continuous values** (logits themselves are the predictions).

- **Loss Function**:
  - **Classification** uses **cross-entropy loss** (binary or categorical).
  - **Regression** uses **mean squared error (MSE)**.

- **Activation Function**:
  - **Classification** often uses **sigmoid** or **softmax** as an activation function to convert logits to probabilities.
  - **Regression** does not use an activation function in the same sense; the raw output (logits) is directly used as the predicted value.

---

## **Summary**

Both **classification** and **regression** models follow a very similar training process:

1. **Initialization of parameters** (weights and bias).
2. **Model prediction** (logits).
3. **Loss calculation**.
4. **Backpropagation** of gradients.
5. **Optimization** via gradient descent.
6. **Repetition** through multiple epochs until convergence.

The main differences lie in how the model output is interpreted and the type of **loss function** used.

```python
import numpy as np
from sklearn.datasets import make_classification
from sklearn.model_selection import train_test_split

# 1. Sigmoid function
def sigmoid(z):
    return 1 / (1 + np.exp(-z))

# 2. Binary Cross-Entropy Loss Function
def binary_cross_entropy(y_true, y_pred):
    m = len(y_true)
    return - (1 / m) * np.sum(y_true * np.log(y_pred) + (1 - y_true) * np.log(1 - y_pred))

# 3. Gradient of the Binary Cross-Entropy Loss function with respect to weights and bias
def gradients(X, y_true, y_pred):
    m = len(X)
    dz = y_pred - y_true
    dw = (1 / m) * np.dot(X.T, dz)
    db = (1 / m) * np.sum(dz)
    return dw, db

# 4. Logistic Regression Model Class
class LogisticRegressionScratch:
    def __init__(self, learning_rate=0.01, epochs=1000):
        self.learning_rate = learning_rate
        self.epochs = epochs
        self.weights = None
        self.bias = None

    # 5. Fit the model (train)
    def fit(self, X_train, y_train):
        # Initialize weights and bias
        self.weights = np.zeros(X_train.shape[1])
        self.bias = 0
        
        # Training loop
        for epoch in range(self.epochs):
            # Forward pass
            z = np.dot(X_train, self.weights) + self.bias
            y_pred = sigmoid(z)
            
            # Calculate loss (optional to track)
            loss = binary_cross_entropy(y_train, y_pred)
            if epoch % 100 == 0:  # print loss every 100 iterations
                print(f'Epoch {epoch}, Loss: {loss}')
            
            # Backward pass (compute gradients)
            dw, db = gradients(X_train, y_train, y_pred)
            
            # Update weights and bias using gradient descent
            self.weights -= self.learning_rate * dw
            self.bias -= self.learning_rate * db

    # 6. Predict method
    def predict(self, X):
        # Calculate logits (z)
        z = np.dot(X, self.weights) + self.bias
        # Apply sigmoid to get probabilities
        y_pred_prob = sigmoid(z)
        # Convert probabilities to binary class predictions (0 or 1)
        return (y_pred_prob >= 0.5).astype(int)

# 7. Generate a synthetic dataset for binary classification
X, y = make_classification(n_samples=1000, n_features=20, n_classes=2, random_state=42)

# 8. Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# 9. Initialize and train the model
model = LogisticRegressionScratch(learning_rate=0.01, epochs=1000)
model.fit(X_train, y_train)

# 10. Make predictions
y_pred = model.predict(X_test)

# 11. Evaluate the model
accuracy = np.mean(y_pred == y_test)
print(f'Accuracy: {accuracy * 100:.2f}%')


```
