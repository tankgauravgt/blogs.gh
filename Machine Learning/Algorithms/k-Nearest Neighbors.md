## Objective

To classify a new sample based on the majority label among its $k$ nearest neighbors in the feature space.

## Model Formulation

Given a dataset $\{(\mathbf{x}_n, y_n)\}_{n=1}^N$, for a query point $\mathbf{x}_q$:
- Compute distances $d(\mathbf{x}_q, \mathbf{x}_n)$ for all $n$.
- Select $k$ samples with smallest distances.
- Predict $\hat{y}_q$ as the most frequent label among these neighbors.

## Key Properties

- Non-parametric, instance-based learning.
- Sensitive to feature scaling and choice of $k$.

## Applications

- Pattern recognition
- Recommendation systems
- Anomaly detection
