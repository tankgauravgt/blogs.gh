## Objective

To perform classification based on Bayes' theorem, assuming feature independence.

## Model Formulation

For class $c$ and input $\mathbf{x}$:
$$
P(y = c | \mathbf{x}) \propto P(y = c) \prod_{d=1}^D P(x_d | y = c)
$$
- Estimate $P(y = c)$ and $P(x_d | y = c)$ from data.
- Predict class with highest posterior probability.

## Applications

- Spam filtering
- Sentiment analysis
- Medical diagnosis
