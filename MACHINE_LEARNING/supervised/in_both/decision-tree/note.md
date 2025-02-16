| Hyperparameter       | Description                                        | Typical Values                     |
|----------------------|----------------------------------------------------|------------------------------------|
| `max_depth`          | Maximum depth of the tree. Controls overfitting.  | [3, 5, 10, 20, None]              |
| `min_samples_split`  | Minimum number of samples required to split a node.| [2, 5, 10, 20]                    |
| `min_samples_leaf`   | Minimum number of samples required at a leaf node.| [1, 5, 10, 20]                    |
| `max_features`       | Maximum number of features considered for a split.| ["auto", "sqrt", "log2", None]    |
| `criterion`          | Function to measure split quality (classification).| ["gini", "entropy", "log_loss"]   |
