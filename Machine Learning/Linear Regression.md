---
## Goal?

{text}

---
## Loss Function

{text}


---
## Objective

{text}


---
## Applications

{list}

# Linear Regression

Linear regression models the relationship between input $\mathbf{X} \in \mathbb{R}^{N \times D}$ and output $\mathbf{y} \in \mathbb{R}^{N}$ via a linear mapping:

$$
\mathbf{y} = \mathbf{X}\mathbf{w} + \boldsymbol{\epsilon}
$$

where $\mathbf{w} \in \mathbb{R}^{D}$ is the weight vector (including bias as an extra dimension if needed), $\boldsymbol{\epsilon}$ is noise. For the $n^{\text{th}}$ sample, $\mathbf{x}_{n} \in \mathbb{R}^D$, $y_{n} = \mathbf{x}_{n}^T \mathbf{w} + \epsilon_{n}$.

The optimal $\mathbf{w}$ minimizes the loss:

$$
\mathcal{L}(\mathbf{w}) = \frac{1}{N} \sum_{n=1}^N (y_{n} - \mathbf{x}_{n}^T \mathbf{w})^2
$$

Closed-form solution:

$$
\mathbf{w}^* = (\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T\mathbf{y}
$$

Gradient descent update:

$$
\mathbf{w} \leftarrow \mathbf{w} - \eta \nabla_{\mathbf{w}} \mathcal{L}(\mathbf{w})
$$

Assumptions: linearity, independence, homoscedasticity, normality of errors.

---

- Prediction: $\hat{y}_{n} = \mathbf{x}_{n}^T \mathbf{w}$
- Loss: $\mathcal{L}$ (MSE)
- $x_{n,d}$: $d^{\text{th}}$ feature of $n^{\text{th}}$ sample, $D$ is dimensionality, $N$ is number of samples.
- $\eta$: learning rate