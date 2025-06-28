## Objective

To establish a linear mapping from input features $\mathbf{x}_n$ to an output $y_n$, minimizing prediction error.


## Model Formulation

The linear model is defined as:
$$
\mathbf{y} = \mathbf{X}\mathbf{w} + \boldsymbol{\epsilon}
$$
Where:

*   $\mathbf{X} \in \mathbb{R}^{N \times D}$: Input feature matrix ($N$ samples, $D$ features; bias can be included as an additional feature column).
*   $\mathbf{w} \in \mathbb{R}^{D}$: Weight vector.
*   $\mathbf{y} \in \mathbb{R}^{N}$: Observed output vector.
*   $\boldsymbol{\epsilon}$: Noise term.

Individual predictions are calculated as $\hat{y}_{n} = \mathbf{x}_{n}^T \mathbf{w}$.


## Loss Function

The model is optimized by minimizing the MSE (mean squared error):
$$
\mathcal{L}(\mathbf{w}) = \frac{1}{N} \sum_{n=1}^N (y_{n} - \mathbf{x}_{n}^T \mathbf{w})^2
$$


## Optimization Strategies

1.  **Closed-form Solution:** $\mathbf{w}^* = (\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T\mathbf{y}$
2.  **Gradient Descent:** Iterative updates: $\mathbf{w} \leftarrow \mathbf{w} - \eta \nabla_{\mathbf{w}} \mathcal{L}(\mathbf{w})$, with $\eta$ as the learning rate.


## Key Assumptions

*   **Linearity:** A linear relationship exists between features and the target.
*   **Independence:** Observations are independent.
*   **Homoscedasticity:** Errors exhibit constant variance.
*   **Normality of Errors:** Errors are normally distributed.


## Applications

*   Continuous outcome prediction (e.g., house prices, stock returns).
*   Feature importance analysis.
*   Establishing a baseline for more complex models.