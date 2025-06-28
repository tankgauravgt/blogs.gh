## Objective

To partition data into $k$ clusters such that each sample belongs to the cluster with the nearest mean.

## Model Formulation

Given $N$ samples $\{\mathbf{x}_n\}_{n=1}^N$:
- Initialize $k$ cluster centroids $\{\boldsymbol{\mu}_j\}_{j=1}^k$.
- Assign each $\mathbf{x}_n$ to the nearest centroid.
- Update centroids as the mean of assigned points.
- Repeat assignment and update until convergence.

## Loss Function

Minimize within-cluster sum of squares (WCSS):
$$
\mathcal{L} = \sum_{j=1}^k \sum_{\mathbf{x}_n \in C_j} \|\mathbf{x}_n - \boldsymbol{\mu}_j\|^2
$$

## Applications

- Customer segmentation
- Image compression
- Document clustering
