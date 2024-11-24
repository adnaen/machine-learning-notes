# Basic Terminologies in ML

In the context of machine learning:

## **Feature Variables**

- The columns in the dataset that exclude the target variable.
- These are the input data that the model uses to learn.

## **Target Variable**

- The column that contains the output or prediction you're trying to make.
- Also known as the dependent variable or label.

## **Training**

- Training the model with data involves adjusting the model’s parameters (weights and biases) to minimize the error between the predicted and actual values.

## **Weight**

- The coefficient that indicates the influence of a feature variable on the target variable.
- Weights are learned during training and are adjusted to reduce prediction errors.
- The value can range from -∞ to +∞.

## **Learning Rate**

- The step size at each iteration while moving toward a minimum of a loss function.
- It controls how quickly or slowly the model learns.

## **Bias**

- A parameter in the model that helps the model make better predictions by adjusting the output independent of the input features.
- Bias helps the model generalize better by shifting the output.

## **Variance**

- The measure of how much the model’s predictions change when trained on different subsets of the data.
- High variance often leads to overfitting, where the model is too complex and learns noise in the data rather than the underlying pattern.

## **Epochs**

- The number of times the model iterates over the entire training dataset during the training process.
- More epochs may lead to better learning, but too many may cause overfitting.

## **Loss**

- The difference between the actual value and the predicted value.
- The loss function quantifies this difference and guides the optimization process during training.

## **Optimization**

- The process of adjusting the model's parameters (weights and biases) to minimize the loss.
- Optimization algorithms, like Gradient Descent, are used to find the best parameters that reduce the loss.

## **Overfitting**

- Occurs when the model learns the training data too well, including the noise, and fails to generalize to new, unseen data.
- It can be mitigated using techniques like cross-validation, regularization, or reducing model complexity.

## **Underfitting**

- Occurs when the model is too simple and fails to capture the underlying patterns in the data.
- This can happen if the model is too constrained or if insufficient features are used.

## **Gradient Descent**

- A popular optimization algorithm used to minimize the loss function by adjusting the weights in the direction of the negative gradient.
- It helps the model converge toward the optimal parameters.

## **Regularization**

- A technique used to reduce overfitting by adding a penalty to the loss function based on the complexity of the model (e.g., L1 or L2 regularization).
- It helps in controlling model complexity by discouraging overly large weights.

## **Validation Set**

- A subset of the data used during training to evaluate the model’s performance and tune hyperparameters.
- Helps to detect overfitting early on.

## **Test Set**

- A subset of the data that is kept separate from the training process.
- It is used to evaluate the final model's performance after training is complete.

## **Cross-Validation**

- A technique used to assess how well a model generalizes by splitting the dataset into several parts (folds) and training/testing on different combinations of those parts.
- Common methods include k-fold cross-validation.
