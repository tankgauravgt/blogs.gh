## Objective

To reduce the dimensionality of data while preserving as much variance as possible.

## Model Formulation

Given centered data matrix $\mathbf{X} \in \mathbb{R}^{N \times D}$:
- Compute covariance matrix $\mathbf{S} = \frac{1}{N} \mathbf{X}^T \mathbf{X}$.
- Find eigenvectors (principal components) and eigenvalues of $\mathbf{S}$.
- Project data onto the top $M$ eigenvectors.

## Applications

- Data visualization
- Noise reduction
- Preprocessing for supervised learning
