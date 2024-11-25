### **Gradient Descent for Logistic Regression**

- **Gradient Descent** is an optimization algorithm used to minimize the loss function.  
- In **Logistic Regression**, Gradient Descent is used to find the optimal parameters (weights and bias) that minimize the loss.
- Gradient Descent iteratively updates the parameters until the loss stops decreasing significantly (reaches a global or local minimum).

---

### **How Gradient Descent Works**

1. **Calculate Gradients**: Compute the partial derivatives of the loss function with respect to the weights (\(w\)) and bias (\(b\)).
2. **Update Parameters**: Adjust the weights and bias by moving in the direction opposite to the gradient to reduce the loss.

### **Gradient Descent Update Equations**

The parameters \(w\) (weights) and \(b\) (bias) are updated in each iteration using the following equations:

- **For weights (\(w\)):**
  \[
  w = w - \alpha \cdot dw
  \]
  Where:
  \[
  dw = (\hat{y} - y) \cdot x
  \]

- **For bias (\(b\)):**
  \[
  b = b - \alpha \cdot db
  \]
  Where:
  \[
  db = \hat{y} - y
  \]

### **Explanation**

- \(w\): Current weight.  
- \(b\): Current bias.  
- \(\alpha\): Learning rate (controls how large the parameter updates are).  
- \(dw\): Gradient of the loss with respect to \(w\).  
- \(db\): Gradient of the loss with respect to \(b\).  
- \(x\): Input feature.  
- \(y\): True label.  
- \(\hat{y}\): Predicted probability.  
