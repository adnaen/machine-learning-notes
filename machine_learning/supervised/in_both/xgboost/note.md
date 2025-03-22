# Hyperparameters in XGBoost

| Hyperparameter       | Description                                                                 | Typical Value Range                |
|----------------------|-----------------------------------------------------------------------------|------------------------------------|
| **`max_depth`**      | Maximum depth of a tree. Controls model complexity.                        | 3–10 (default: 6)                 |
| **`learning_rate`**  | Step size shrinkage to prevent overfitting (lower = slower, more accurate). | 0.01–0.3 (default: 0.3)           |
| **`n_estimators`**   | Number of boosting rounds (trees).                                         | 100–1000 (use early stopping)     |
| **`subsample`**      | Fraction of samples to use for training each tree. Reduces overfitting.    | 0.5–1 (default: 1)                |
| **`colsample_bytree`** | Fraction of features to use for training each tree.                      | 0.5–1 (default: 1)                |
| **`min_child_weight`** | Minimum sum of instance weights (Hessian) in a leaf. Controls overfitting. | 1–10 (default: 1)                 |
| **`gamma`**          | Minimum loss reduction required to split a node. Higher = more conservative. | 0–5 (default: 0)                  |