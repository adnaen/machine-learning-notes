# **Decision Tree**

# About
- This model can used in both Classification & Regression

# HyperParameters
- `max_depth`        : Number of levels (or depth) of the tree.
- `min_sample_split` : allows the tree to split nodes as long as each node has at least 2 samples.
- `min_sample_leaf`  : Minimum samples for splitting leaf nodes
- `max_features`     : Maximum feature for splitting
- `criterion`        : Defines the function used to measure the quality of a split
    - `gini` -> for gini impurity(mainly used for classification)
    - `entropy` -> for information gain

# Advantages
- Does not require to Standardize or Normalize data
- It can handle dataset with Non-Linear relationship

# Disadvantages
- High Depth tree can overfit model
- Target classes mut have balanced
- Slower on large dataset