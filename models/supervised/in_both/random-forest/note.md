| **Hyperparameter**       | **Description**                                        | **Typical Values**                     |
|---------------------------|------------------------------------------------------|----------------------------------------|
| **`n_estimators`**        | Number of trees in the forest.                        | [50, 100, 200, 300, 500]              |
| **`max_depth`**           | Maximum depth of each tree. Controls overfitting.     | [10, 20, 30, None]                    |
| **`min_samples_split`**   | Minimum number of samples required to split a node.   | [2, 5, 10, 20]                        |
| **`min_samples_leaf`**    | Minimum number of samples required at a leaf node.    | [1, 2, 5, 10]                         |
| **`max_features`**        | Number of features considered for the best split.     | ["sqrt", "log2", None, specific values like 2, 3, 4] |
| **`bootstrap`**           | Whether to use bootstrapped samples.                  | [True, False]                         |
| **`class_weight`**        | Balances class weights for imbalanced datasets.       | ["balanced", "balanced_subsample", None] |
| **`max_leaf_nodes`**      | Maximum number of leaf nodes.                         | [10, 20, 30, None]                    |
| **`n_jobs`**              | Number of parallel jobs to use for training.          | [-1 (use all processors)]             |
| **`random_state`**        | Seed for reproducibility.                             | [Any integer, e.g., 42]               |
| **`max_samples`**         | Fraction of samples used for training each tree.      | [0.5, 0.8, None]                      |
