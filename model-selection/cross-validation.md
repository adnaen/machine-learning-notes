# Cross Validation

**Cross Validation is the Technique that used in Machine Learning to evaluate the performance of the model on unseen data**

- #### **Types Of Cross Validation**

  1. ###### **`Hold One Out Cross Validation`**: Typical Train Test Split that used in ML

        - The dataset is split into two parts: training and testing.
        - A single split is made, e.g., 80% for training and 20% for testing.
        - Pros: Simple and quick.
        - Cons: Performance can depend on how the data was split.

        ```python
        from sklearn.model_selection import train_test_split
        from sklearn.ensemble import RandomForestClassifier
        from sklearn.metrics import accuracy_score

        X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
        model = RandomForestClassifier()
        model.fit(X_train, y_train)
        predictions = model.predict(X_test)
        print("Hold-Out Accuracy:", accuracy_score(y_test, predictions))

        ```

  2. ###### **`K Fold Cross Validation`**: Data split into K Folds(subset), in each

        - The dataset is split into k folds (typically k=5 or 10).
        - Each fold is used as a test set once, while the remaining k-1 folds are used for training.
        - Pros: More reliable than hold-out; reduces variance.
        - Cons: Requires more computation time as the model is trained k times.

        ```python
        from sklearn.model_selection import KFold, cross_val_score
        from sklearn.ensemble import RandomForestClassifier

        kfold = KFold(n_splits=5, shuffle=True, random_state=42)
        model = RandomForestClassifier()
        scores = cross_val_score(model, X, y, cv=kfold)
        print("K-Fold Accuracy:", scores.mean())
        ```

  3. ###### **`Stratified K Fold Cross Validation` = the typical `train test split`**

        - A variant of K-Fold where each fold has roughly the same proportion of class labels as the entire dataset.
        - Useful for imbalanced datasets where one class significantly outnumbers others.
        - Pros: Ensures balanced distribution across folds; reliable for classification tasks.
        - Cons: More suitable for classification than regression.

        ```python
        from sklearn.model_selection import StratifiedKFold, cross_val_score

        skfold = StratifiedKFold(n_splits=5, shuffle=True, random_state=42)
        model = RandomForestClassifier()
        scores = cross_val_score(model, X, y, cv=skfold)
        print("Stratified K-Fold Accuracy:", scores.mean())
        ```

  4. ###### **`Leave One Out Cross Validation` = the typical `train test split`**

        - Each sample is used as a test set once, and all other samples are used for training.
        - The process is repeated for each sample in the dataset.
        - Pros: Uses nearly all data for training each time, yielding very unbiased estimates.
        - Cons: Computationally expensive for large datasets.

        ```python
        from sklearn.model_selection import LeaveOneOut, cross_val_score

        loo = LeaveOneOut()
        model = RandomForestClassifier()
        scores = cross_val_score(model, X, y, cv=loo)
        print("Leave-One-Out Accuracy:", scores.mean())
        ```

> `K Fold Cross Validation is Mostly Used`
