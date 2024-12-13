# Gradient Descent

Gradient Descent is a optimization algorithm used for minimizing the cost/loss function in various machine learning algorithms, It is used for updating the parameters of the learning model.

- Used in Linear Models & Neural Networks
- In Neural Network context this step also known as backpropagation

![gradient descent](../../assets/gradient_descent.jpeg)

Where:

- $w$ : Weight
- $Cost$ : A.K.A Loss
- Learning Step ($\alpha$) : Learning Rate

## **How Gradient Descent Works**

Gradient Descent is a method to minimize the loss function by iteratively updating model parameters such as weights ($w$) and bias ($b$).

### A simple example

- You're playing a video game where your character is lost on a hilly landscape, and you want to reach the lowest valley (global minimum). The valley represents the lowest loss for your machine learning model.

Steps:

1. Start Anywhere: You randomly start on the mountain (random initialization of weights & bias).
2. Look Around: You check the steepness in all directions using derivatives:
3. How steep is it if you move forward (partial derivative with respect to $x$)?
4. How steep if you move sideways (partial derivative with respect to $y$)?
5. Take a Step: You move downhill based on the gradient (combined steepness of all directions), but only a small step (controlled by the learning rate).
6. Repeat: Keep repeating until the steepness is nearly zero (derivative = 0), meaning you’ve reached the bottom (global or local minimum).

---

### **1. Calculate Gradients**

- **Gradient** = The "best guess" for which direction to move to reduce the loss.

Gradients measure how the loss function changes with respect to weights ($w$) and bias ($b$).  
Each loss function has a different gradient equation:

#### **1.1 Mean Squared Error (MSE)**  

- **Loss Function**:
  
  $$L = \frac{1}{n} \sum_{i=1}^n (\hat{y}_i - y_i)^2$$

- **Gradients**:
  
  $$dw = \frac{2}{n} \sum_{i=1}^n (\hat{y}_i - y_i) x_i$$
  
  $$db = \frac{2}{n} \sum_{i=1}^n (\hat{y}_i - y_i)$$

---

#### **1.2 Mean Absolute Error (MAE)**  

- **Loss Function**:  
  $$L = \frac{1}{n} \sum_{i=1}^n | \hat{y}_i - y_i |$$

- **Gradients**:  
  $dw$ and $db$ depend on the sign of $(\hat{y}_i - y_i)$:
  
  - If $\hat{y}_i > y_i$:

    $$dw = \frac{1}{n} \sum_{i=1}^n x_i, db = \frac{1}{n}$$

  - If $\hat{y}_i < y_i$:

    $$dw = -\frac{1}{n} \sum_{i=1}^n x_i, db = -\frac{1}{n}$$

---

#### **1.3 Binary Cross-Entropy (BCE)**  

- **Loss Function**:
  
  $$L = -\frac{1}{n} \sum_{i=1}^n \left[ y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i) \right]$$

- **Gradients**:
  
  $$dw = \frac{1}{n} \sum_{i=1}^n (\hat{y}_i - y_i) x_i$$
  
  $$db = \frac{1}{n} \sum_{i=1}^n (\hat{y}_i - y_i)$$

---

#### **1.4 Categorical Cross-Entropy (CCE)** (for multi-class classification)  

- **Loss Function**:
  
  $$L = -\frac{1}{n} \sum_{i=1}^n \sum_{k=1}^K y_{i,k} \log(\hat{y}_{i,k})$$
  
  Where $k$ is the class, and $\hat{y}_{i,k}$ is the predicted probability for class $k$.

- **Gradients**:
  
  $$dw = \frac{1}{n} \sum_{i=1}^n \sum_{k=1}^K (\hat{y}_{i,k} - y_{i,k}) x_i$$
  
  $$db = \frac{1}{n} \sum_{i=1}^n \sum_{k=1}^K (\hat{y}_{i,k} - y_{i,k})$$

---

### **2. Update Parameters**

Once gradients are calculated, update the weights ($w$) and bias ($b$) as follows:



- **For weights ($w$):**

  $$
  w = w - \alpha \cdot dw
  $$

- **For bias ($b$):**
  $$
  b = b - \alpha \cdot db
  $$

#### **Where**

- $w$: Current weight.  
- $b$: Current bias.  
- $\alpha$: Learning rate (controls how large the parameter updates are).  
- $dw$: Gradient of the loss with respect to $w$.  
- $db$: Gradient of the loss with respect to $b$.  
