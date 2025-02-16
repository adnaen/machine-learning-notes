| **Hyperparameter**       | **Description**                                        | **Typical Values**                     |
|---------------------------|------------------------------------------------------|----------------------------------------|
| **`n_estimators`**        | Number of trees in the forest.                        | [50, 100, 200, 300, 500]              |
| **`max_depth`**           | Maximum depth of each tree. Controls overfitting.     | [10, 20, 30, None]                    |
| **`min_samples_split`**   | Minimum number of samples required to split a node.   | [2, 5, 10, 20]                        |
| **`min_samples_leaf`**    | Minimum number of samples required at a leaf node.    | [1, 2, 5, 10]                         |
| **`max_features`**        | Number of features considered for the best split.     | ["sqrt", "log2"]                      |
| **`bootstrap`**           | Whether to use bootstrap samples when building trees. | [True, False]                         |
| **`max_samples`**         | Fraction of the dataset used for training each tree.  | [0.5, 0.75, 1.0]                      |