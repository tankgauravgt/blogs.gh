---
## Goal?

{text}

---
## Objective

To model the probability of a binary outcome by fitting a logistic function to the input features, enabling classification.


## Model Formulation

For a binary classification problem with outcomes $y_n \in \{0, 1\}$, the probability of the positive class is modeled using the sigmoid (logistic) function:
$$
P(y_n=1|\mathbf{x}_n; \mathbf{w}) = \sigma(\mathbf{x}_n^T \mathbf{w}) = \frac{1}{1 + e^{-\mathbf{x}_n^T \mathbf{w}}}
$$
Where:

*   $\mathbf{x}_n \in \mathbb{R}^{D}$: Input feature vector for sample $n$.
*   $\mathbf{w} \in \mathbb{R}^{D}$: Weight vector (including bias).
*   $\sigma(\cdot)$: The sigmoid activation function.

The predicted class $\hat{y}_n$ is typically 1 if $P(y_n=1|\mathbf{x}_n; \mathbf{w}) \ge 0.5$, and 0 otherwise.


## Loss Function

The model is optimized by minimizing the Binary Cross-Entropy (BCE) loss, also known as log loss, for $N$ samples:
$$
\mathcal{L}(\mathbf{w}) = -\frac{1}{N} \sum_{n=1}^N [y_n \log(\hat{p}_n) + (1 - y_n) \log(1 - \hat{p}_n)]
$$
Where $\hat{p}_n = \sigma(\mathbf{x}_n^T \mathbf{w})$ is the predicted probability for sample $n$.


## Optimization Strategies

Unlike linear regression, logistic regression typically lacks a closed-form solution. Optimization is performed iteratively:

*   **Gradient Descent:** Iterative updates: $\mathbf{w} \leftarrow \mathbf{w} - \eta \nabla_{\mathbf{w}} \mathcal{L}(\mathbf{w})$, with $\eta$ as the learning rate.
*   **Newton's Method / Quasi-Newton Methods:** More advanced iterative optimization algorithms.


## Key Assumptions

*   **Binary Outcome:** The dependent variable must be binary.
*   **Independence of Observations:** Data points are independent.
*   **No Multicollinearity:** Independent variables should not be highly correlated.
*   **Linearity of Log-Odds:** The relationship between independent variables and the log-odds of the outcome is linear.


## Applications

*   Binary classification (e.g., spam detection, disease prediction, customer churn).
*   Estimating the probability of an event.
*   Establishing a baseline for more complex classification models.