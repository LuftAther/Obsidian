### Exponential family log-likelihood

Show that the log-likelihood for the natural parameter in the canonical form of the exponential family is always concave and strictly concave unless the distribution of the natural statistic is degenerate.

---
---
Consider a $k$-parameter exponential family in **canonical form**, with density:

$$
f(x \mid \theta) = h(x) \exp\left( \langle \theta, T(x) \rangle - b(\theta) \right)
$$

where:
- $\theta \in \mathbb{R}^k$ is the **natural parameter**
- $T(x) \in \mathbb{R}^k$ is the **sufficient statistic**
- $b(\theta)$ is the **log-partition function**
- $h(x)$ is the base measure
- $\langle \cdot, \cdot \rangle$ denotes the standard inner product

---

Given data $x_1, \dots, x_n$ (i.i.d.), the log-likelihood is:

$$
\ell(\theta) = \sum_{i=1}^n \log f(x_i \mid \theta)
= \sum_{i=1}^n \left( \langle \theta, T(x_i) \rangle - b(\theta) + \log h(x_i) \right)
$$

Removing the constant term $\sum \log h(x_i)$:

$$
\ell(\theta) = \langle \theta, \sum_{i=1}^n T(x_i) \rangle - n b(\theta)
$$
Let $\bar{T}_n = \frac{1}{n} \sum_{i=1}^n T(x_i)$. Then:

**Gradient:**

$$
\nabla_\theta \ell(\theta) = \sum_{i=1}^n T(x_i) - n \nabla b(\theta) = n \left( \bar{T}_n - \nabla b(\theta) \right)
$$

**Hessian:**

$$
\nabla^2_\theta \ell(\theta) = -n \nabla^2 b(\theta)
$$

But $\nabla^2 b(\theta)$ is the **covariance matrix of $T(X)$ under $f(x \mid \theta)$**:

$$
\nabla^2 b(\theta) = \text{Cov}_\theta(T(X)) \quad \text{(always positive semi-definite)}
$$

So:

$$
\nabla^2_\theta \ell(\theta) = -n \cdot \text{Cov}_\theta(T(X)) \preceq 0
$$
The **log-likelihood is concave** (since the Hessian is negative semi-definite)
The log-likelihood is **strictly concave** if $\text{Cov}_\theta(T(X))$ is **positive definite**, i.e. when $T(X)$ is **not degenerate**.

- If $T(X)$ is **non-constant** (i.e., varies), $\text{Cov}_\theta(T(X)) \succ 0$ ⇒ strictly concave
- If $T(X)$ is **constant** a.s., then $\text{Cov}_\theta(T(X)) = 0$ ⇒ log-likelihood is affine (not strictly concave)

---
**Conclusion**

- $\ell(\theta)$ is **concave** in $\theta$
- It is **strictly concave** unless $T(X)$ is **degenerate**

This result justifies the uniqueness of MLEs under regular conditions for exponential families.

---

**Interpretation**

The MLE solves:

$$
\bar{T}_n = \nabla b(\hat{\theta})
$$

This is a **moment-matching condition**, since $\nabla b(\theta) = \mathbb{E}_\theta[T(X)]$.
