# Gradient Descent

Gradient Descent is a optimization algorithm used for minimizing the cost function in various machine learning algorithms, It is used for updating the parameters of the learning model.

![gradient descent](../../assets/gradient_descent.jpeg)
Where:

- $w$ : Weight
- $Cost$ : A.K.A Loss
- Learning Step ($\alpha$) : Learning Rate

## **How Gradient Descent Works**

Gradient Descent is a method to minimize the loss function by iteratively updating model parameters such as weights ($w$) and bias ($b$).

---

### **1. Calculate Gradients**

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

$w = w - \alpha \cdot dw$  
$b = b - \alpha \cdot db$

Where:

- $\alpha$: The **learning rate**, which controls how much the weights and bias are adjusted.
- $dw$, $db$: Gradients calculated based on the loss function.

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
