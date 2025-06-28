## Objective

To classify data by learning axis-aligned decision rules that split the feature space.

## Model Formulation

- At each node, select the feature and threshold that best splits the data (e.g., by information gain or Gini impurity).
- Recursively partition until stopping criteria are met (e.g., max depth, min samples).
- Predict by traversing the tree from root to leaf.

## Applications

- Credit scoring
- Medical diagnosis
- Feature selection
