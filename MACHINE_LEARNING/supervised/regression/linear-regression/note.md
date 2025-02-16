# 🧠 Maths Behind Linear Regression

### ➡️ **Linear Equation**

For single variable:
$${\hat{y} = m \cdot X + c}$$

For multi variable:
$${\hat{y} = m_1 \cdot X_1 + ... + m_2 \cdot X_2 + c}$$

- where:
  - $\hat{y}$ predicted value.
  - $X$ is the feature (input data).
  - $m$ Slop(coefficient) of the straight line.
  - $c$ intercept (what is the value of y when x = 0).

### ⚙️ **Workflow**

1. **Initialize Model/Hyper Parameters**
   - Set the **learning rate** (e.g., 0.01) and **number of epochs**.
   - Initialize **Coefficient(slop)** and **Intercept** to small random values or zeros.

2. **Calculate prediction**
   - Calculate prediction by **Linear Equation**

3. **Compute Loss**
   - You can use either **MSE** or **MAE**

   | **Loss Function** | **Outlier Sensitivity** | **When to Use**                             | **Data Distribution**                       |
   |--------------------|--------------------------|---------------------------------------------|---------------------------------------------|
   | **MSE**           | High                    | When large errors matter more (e.g., predicting house prices). | Best for normally distributed data.         |
   | **MAE**           | Low                     | When you have outliers and want to treat all errors equally.     | Works well with skewed or non-normal data.  |

4. **Gradient Descent**
   - Compute the **gradients** of the loss function with respect to the coefficient ($m$) and intercept ($c$).
   - Use **gradient descent** to update the slop and intercept:
   - [Know about Gradient Descent](../../../../optimzation-and-training/gradient-descent/note.md)

5. **Repeat Steps 2–5**
   - Iterate through the forward and backward propagation steps for the specified number of epochs or until convergence (when the loss stops decreasing significantly).

6. **Prediction**
   - After training, use the learned weights and bias to predict probabilities for new data.
