## Autoregressive time series

Let $Z_i$ for $i = 1, 2, \dots$ be iid random variables with mean zero and variance $\sigma^2$. Moreover, let $X_0$ be any random variable with mean zero and independent of the $Z_i$, and recursively define

$$
X_n = \rho X_{n-1} + Z_n, \quad n = 1, 2, \dots
$$

for $\rho \in \mathbb{R}$. The time series $X_1, X_2, \dots$ is called an *autoregressive time series of order one*, AR(1) for short.

1. Show that $\mathbb{E} X_n = 0$ for $n = 1, 2, \dots$
2. Assume $\mathrm{Var}(X_0) = \sigma_0^2 < \infty$, derive the covariance $\mathrm{Cov}(X_{n+k}, X_n)$ for $n, k = 0, 1, \dots$
3. Write in concise matrix format the covariance matrix of $\mathbf{X} = (X_1, X_2, \dots, X_n)$.

---

## 1. Show that $\mathbb{E} X_n = 0$ for $n = 1, 2, \dots$

Given the recursion: $X_n = \rho X_{n-1} + Z_n$

with $\mathbb{E}[Z_n] = 0$, and want to show:

$$
\mathbb{E}[X_n] = 0 \quad \text{for all } n \in \mathbb{N}
$$

### Proof by Induction

**Base Case (IB): $n = 0$**

By definition of $X_0$, we have:

$$
\mathbb{E}[X_0] = 0
$$

**Induction Assumtion (IA)**$$ \mathbb{E}[X_n] = 0$$
**Inductive Step (IS): Assume $\mathbb{E}[X_{n+1}] = 0$,**

Use the recursion:

$$
\begin{split}
\mathbb{E}[X_{n+1}] &= \mathbb{E}[\rho X_{n} + Z_{n+1}] \\
&= \rho \, \mathbb{E}[X_{n}] + \mathbb{E}[Z_{n+1}] \\
&= \rho \cdot 0 + 0 = 0
\end{split}
$$


So by induction, $\mathbb{E}[X_n] = 0$ for all $n \in \mathbb{N}$.

---
## 2. Assume $\mathrm{Var}(X_0) = \sigma_0^2 < \infty$, derive the covariance $\mathrm{Cov}(X_{n+k}, X_n)$ for $n, k = 0, 1, \dots$

Let $X_n = \rho X_{n-1} + Z_n$, with $\mathbb{E}[Z_n] = 0$, $\operatorname{Var}(Z_n) = \sigma^2$, and all $Z_n$ independent.

We want to show:

$$
\operatorname{Cov}(X_{n+k}, X_n) = \rho^k \operatorname{Var}(X_n)
$$
### Proof by Induction

**Base Case (IA): $k = 0$**

$$
\mathbb{E}[X_n^2] = \operatorname{Var}(X_n) + (\mathbb{E}[X_n])^2 = \operatorname{Var}(X_n)
$$

(since $\mathbb{E}[X_n] = 0$)

**Induction Assumtion (IA)**
$$
\mathbb{E}[X_{n+k} X_n] =\operatorname{Cov}(X_{n+k}, X_n) = \rho^k \operatorname{Var}(X_n)
$$

**Inductive Step $k \rightarrow k+1$**

$$
\begin{split}
\mathbb{E}[X_{n+k+1} X_n] &= \mathbb{E}[(\rho X_{n+k} + Z_{n+k+1}) X_n] \\
&= \rho \mathbb{E}[X_{n+k} X_n] + \mathbb{E}[Z_{n+k+1} X_n] \\
&= \rho \cdot \rho^k \operatorname{Var}(X_n) + 0 \\
&= \rho^{k+1} \operatorname{Var}(X_n)
\end{split}
$$

Therefore:

$$
\operatorname{Cov}(X_{n+k}, X_n) = \rho^k \operatorname{Var}(X_n)
$$
### Now we have to compute Closed-Form of $\operatorname{Var}(X_n)$

Recall:

$$
X_n = \rho^n X_0 + \sum_{j=1}^n \rho^{n-j} Z_j
$$

Then:

$$
\begin{split}
\operatorname{Var}(X_n) &= \operatorname{Var}\left( \rho^n X_0 + \sum_{j=1}^n \rho^{n-j} Z_j \right) \\
&= \rho^{2n} \operatorname{Var}(X_0) + \sum_{j=1}^n \rho^{2(n-j)} \operatorname{Var}(Z_j) \\
&= \rho^{2n} \sigma_0^2 + \sigma^2 \sum_{j=1}^n \rho^{2(n-j)} \\
&= \rho^{2n} \sigma_0^2 + \sigma^2 \sum_{k=0}^{n-1} \rho^{2k}
\end{split}
$$

Use the geometric series formula:

$$
\sum_{k=0}^{n-1} \rho^{2k} = \frac{1 - \rho^{2n}}{1 - \rho^2}
$$

So:

$$
\operatorname{Var}(X_n) = \rho^{2n} \sigma_0^2 + \sigma^2 \cdot \frac{1 - \rho^{2n}}{1 - \rho^2}
$$

Putting it all together:

$$
\operatorname{Cov}(X_{n+k}, X_n) = \rho^{k+1} \left( \rho^{2n} \sigma_0^2 + \frac{\sigma^2 (1 - \rho^{2n})}{1 - \rho^2} \right)
$$
---

## 3. Write in concise matrix format the covariance matrix of $\mathbf{X} = (X_1, X_2, \dots, X_n)$.

Let $\Sigma$ be the covariance matrix of the vector $(X_1, \dots, X_n)^\top$.

From the recursion $X_n = \rho X_{n-1} + Z_n$, we have:

$$
\operatorname{Cov}(X_i, X_j) = \rho^{|i - j|} \cdot \operatorname{Var}(X_{\min(i, j)})
$$

Using the formula for the variance:

$$
\operatorname{Var}(X_k) = \rho^{2k} \sigma_0^2 + \frac{\sigma^2 (1 - \rho^{2k})}{1 - \rho^2}
$$

So the covariance matrix is:

$$
\Sigma = \left( \rho^{|i - j|} \left( \rho^{2 \min(i, j)} \sigma_0^2 + \frac{\sigma^2 (1 - \rho^{2 \min(i, j)})}{1 - \rho^2} \right) \right)_{i,j = 1}^n
$$