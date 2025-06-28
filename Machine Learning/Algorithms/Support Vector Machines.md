## Objective

To classify data by finding the hyperplane that maximizes the margin between classes.

## Model Formulation

Given labeled data $\{(\mathbf{x}_n, y_n)\}_{n=1}^N$, $y_n \in \{-1, 1\}$:
- Find $\mathbf{w}, b$ such that $y_n (\mathbf{x}_n^T \mathbf{w} + b) \geq 1$ for all $n$.
- Maximize margin $\frac{2}{\|\mathbf{w}\|}$.

## Loss Function

Hinge loss (soft margin):
$$
\mathcal{L}(\mathbf{w}, b) = \frac{1}{N} \sum_{n=1}^N \max(0, 1 - y_n (\mathbf{x}_n^T \mathbf{w} + b))
$$

## Applications

- Text classification
- Image recognition
- Bioinformatics
