### Exponential MLE

Let $X_1, \ldots, X_n$ be a random sample from a population with an exponential distribution $\text{Exp}\left(\frac{1}{\tau}\right)$, i.e. with pdf

$$
f(x \mid \tau) = \mathbb{I}_{[0, \infty)}(x) \, \frac{1}{\tau} e^{-x/\tau}
$$

and unknown scale parameter $\tau > 0$.

1. **Find the MLE of $\tau$**. What is the exact sampling distribution of the MLE? Use the CLT to find a normal approximation to the sampling distribution.

2. **Show that the MLE is unbiased** and find its exact variance. Is there any other unbiased estimate with smaller variance?

> **Hint:** The sum of the $X_i$ follows a gamma distribution.

---
---

**1. Finding the MLE of $\tau$**

The likelihood function is: $L(\tau) = \prod_{i=1}^n \frac{1}{\tau} e^{-x_i / \tau} = \tau^{-n} \exp\left(-\frac{1}{\tau} \sum_{i=1}^n x_i \right)$

The log-likelihood function is: 
$$
\begin{split}
\ell(\tau) &= \log \left( \tau^{-n} \exp\left(-\frac{1}{\tau} \sum_{i=1}^n x_i \right) \right)\\
&= \log(\tau^{-n}) + \log\left( \exp\left(-\frac{1}{\tau} \sum_{i=1}^n x_i \right) \right)\\
&= -n \log(\tau) - \frac{1}{\tau} \sum_{i=1}^{n}x_i
\end{split}
$$


To find the maximum, differentiate:

$$
\begin{split}
\frac{d\ell}{d\tau} &= -\frac{n}{\tau} + \frac{1}{\tau^2} \sum_{i=1}^n x_i\\ 
&\Rightarrow \quad
-\frac{n}{\tau} + \frac{1}{\tau^2} \sum_{i=1}^n x_i = 0\\
&\Leftrightarrow -n\tau + \sum_{i=1}^n x_i = 0\\
&\Leftrightarrow \sum_{i=1}^n x_i = n\tau\\
& \Rightarrow \hat{\tau} = \frac{1}{n} \sum_{i=1}^n x_i = \bar{X}
\end{split}
$$
So, the **MLE** is $\hat{\tau} = \bar{X}$.

---


**Exact Sampling Distribution of $\hat{\tau}$:**

We know:

$$
\sum_{i=1}^n X_i \sim \text{Gamma}(n, \theta = \tau)
$$

Then:

$$
\hat{\tau} = \frac{1}{n} \sum X_i \sim \text{Gamma}(n, \frac{\tau}{n})
$$

(because scaling a gamma variable by $\frac{1}{n}$ scales the parameter $\theta$ to $\frac{\tau}{n}$)

---

**Normal Approximation (by CLT):**

Since $\bar{X} = \hat{\tau}$ and for $X \sim \text{Exp}(\tau)$ we know:

- $\mathbb{E}[X] = \tau$
- $\text{Var}(X) = \tau^2$

- We know by the **Central Limit Theorem (CLT)**:

$$
\sqrt{n}(\bar{X}_n - \mu) \xrightarrow{d} \mathcal{N}(0, \sigma^2)
$$

and for $X \sim \text{Exp}(\tau)$:

$$
\mathbb{E}[X] = \tau, \quad \text{Var}(X) = \tau^2
$$

- So for large $n$:

$$
\sqrt{n}(\bar{X}_n - \tau) \xrightarrow{d} \mathcal{N}(0, \tau^2)
\quad \Rightarrow \quad
\hat{\tau} = \bar{X}_n \approx \mathcal{N}(\tau, \frac{\tau^2}{n})
$$

---
### 2) Unbiasedness and Variance of the MLE

Since $\mathbb{E}(X_i) = \tau$:

$$
\mathbb{E}(\hat{\tau}) = \mathbb{E}(\bar{X}) = \mathbb{E}\left( \frac{1}{n} \sum_{i=1}^n X_i \right)
= \frac{1}{n} \sum_{i=1}^n \mathbb{E}(X_i) = \frac{1}{n} \cdot n \cdot \tau = \tau
$$

$\Rightarrow$ **$\hat{\tau}$ is unbiased.**

- Since $\text{Var}(X_i) = \tau^2$:

$$
\text{Var}(\hat{\tau}) = \text{Var}(\bar{X}) = \text{Var}\left( \frac{1}{n} \sum_{i=1}^n X_i \right)
= \frac{1}{n^2} \cdot n \cdot \tau^2 = \frac{\tau^2}{n}
$$
By Cramér–Rao Lower Bound (CRLB).  The Fisher information for a single observation is

$$
\mathcal{I}(\tau) = \mathbb{E} \left[ \left( \frac{\partial}{\partial \tau} \log f(X \mid \tau) \right)^2 \right]
$$

This bound confirms that the variance of $\hat{\tau}$ achieves the minimum possible for unbiased estimators.
$$
\mathcal{I}(\tau) = \mathbb{E} \left[ \left( \frac{\partial}{\partial \tau} \log f(X \mid \tau) \right)^2 \right]
= \mathbb{E} \left[ \left( \frac{1}{\tau} - \frac{X}{\tau^2} \right)^2 \right]
= \mathbb{E} \left[ \frac{X^2}{\tau^4} - \frac{2X}{\tau^3} + \frac{1}{\tau^2} \right]
$$

We know:

- $\mathbb{E}(X) = \tau$
- $\text{Var}(X) = \mathbb{E}(X^{2) - \mathbb{E}(X)^{2}\Leftrightarrow}\mathbb{E}(X^2) = \text{Var}(X) + \mathbb{E}(X)^{2=}\tau^2 + \tau^2 = 2\tau^2$

So:
$$
\begin{split}
\mathbb{E} \left[ \left( \frac{\partial}{\partial \tau} \log f(X \mid \tau) \right)^2 \right]
&= \frac{1}{\tau^4} \mathbb{E}(X^2) - \frac{2}{\tau^3} \mathbb{E}(X) + \frac{1}{\tau^2}\\
&= \frac{2\tau^2}{\tau^4} - \frac{2\tau}{\tau^3} + \frac{1}{\tau^2}\\
&= \frac{2}{\tau^2} - \frac{2}{\tau^2} + \frac{1}{\tau^2}\\
&= \frac{1}{\tau^2}
\end{split}
$$

- For $n$ independent observations: $\mathcal{I}_n(\tau) = n \cdot \mathcal{I}(\tau) = \frac{n}{\tau^2}$
- By Cramér–Rao Inequality: $\text{Var}(\hat{\tau}) \geq \frac{1}{\mathcal{I}_n(\tau)} = \frac{1}{\frac{n}{\tau^{2}}} = \frac{\tau^2}{n}$
- Since we previously showed: $\text{Var}(\hat{\tau}) = \frac{\tau^2}{n}$

But we have already shown: $\text{Var}(\hat{\tau}) = \frac{\tau^2}{n}$ which matches the Cramér–Rao lower bound: $\Rightarrow \text{MLE } \hat{\tau} \text{ achieves the Cramér–Rao lower bound.}$

So, $\hat{\tau}$ is efficient and attains the Cramér–Rao lower bound, $\Rightarrow \hat{\tau} \text{ is the best unbiased estimator (Minimum Variance Unbiased Estimator, MVUE).}$
