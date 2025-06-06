**Exponential Rate Estimator**

Let $X_1, \ldots, X_n$ be a random sample from $\text{Exp}(\lambda)$, where $\lambda > 0$ is unknown.
1. Find the method of moments estimator of $\lambda$.
2. Find the MLE of $\lambda$.
3. Determine the asymptotic distribution of the MLE.
4. The MLE of $\lambda$ is biased. Derive an unbiased estimator for $\lambda$ by “correcting” the MLE.
---

1) **MME** (Method of Moments Estimator):
$$
\bar{X}_n = \mathbb{E}(X_1) = \frac{1}{\lambda} \quad \Rightarrow \quad \lambda \approx \frac{1}{\bar{X}_n}
$$

---

**2) **MLE** (Maximum Likelihood Estimator):**
Let $\ell_n(\lambda)$ be the log-likelihood function:

$$
\begin{split}
\ell_n(\lambda) &= \sum_{i=1}^n \log(f_\lambda(x_i)) = \sum_{i=1}^n \log(\lambda e^{-\lambda x_i}) \\
&= \sum_{i=1}^n \left( \log(\lambda) - \lambda x_i \right) \\
&= n \log(\lambda) - \lambda \sum_{i=1}^n x_i = n \log(\lambda) - n \lambda \bar{X}_n
\end{split}
$$

Take the derivative:

$$
\begin{split}
\ell_n'(\lambda) &= \frac{n}{\lambda} - n \bar{X}_n \\
0 &= \ell_n'(\lambda) \quad \Rightarrow \quad \frac{n}{\lambda} = n \bar{X}_n \\
\Rightarrow \quad \lambda &= \frac{1}{\bar{X}_n}
\end{split}
$$

---

**3. Determine the asymptotic distribution of the MLE.**

Given:
$$
\operatorname{Var}(X_1) = \frac{1}{\lambda^2} < \infty
$$

By the **Central Limit Theorem (CLT)**:
$$
\sqrt{n} \left( \bar{X}_n - \frac{1}{\lambda} \right) \xrightarrow{d} \mathcal{N}\left(0, \frac{1}{\lambda^2} \right)
$$
**Delta Method:**

Let
$$
g(x) = \frac{1}{x}, \quad g'(x) = -\frac{1}{x^2}
$$

Then:
$$
\begin{split}
\left( g'\left(\frac{1}{\lambda} \right) \right)^2 \cdot \frac{1}{\lambda^2}
&= \left( -\lambda^2 \right)^2 \cdot \frac{1}{\lambda^2} \\
&= \lambda^4 \cdot \frac{1}{\lambda^2} = \lambda^2
\end{split}
$$

Using the CLT and the Delta Method:
$$
\sqrt{n} \left( \frac{1}{\bar{X}_n} - \lambda \right)
\xrightarrow{d} \mathcal{N} \left( 0, g'\left(\frac{1}{\lambda} \right)^2 \cdot \frac{1}{\lambda^2} \right)
= \mathcal{N}(0, \lambda^2)
$$

So:
$$
\frac{1}{\bar{X}_n} \approx \mathcal{N} \left( \lambda, \frac{\lambda^2}{n} \right)
$$
---

**4. The MLE of $\lambda$ is biased. Derive an unbiased estimator for $\lambda$ by “correcting” the MLE.**

Let $Y := n \bar{X}_n \Rightarrow Y \sim \text{Gamma}(n, \lambda)$

Let $Z := \frac{1}{Y} \Rightarrow$

$$
\begin{split}
f_Z(z) &= f_Y\left( \frac{1}{z} \right) \cdot \left| -\frac{1}{z^2} \right| \\
&= \frac{\lambda^n}{\Gamma(n)} \left( \frac{1}{z} \right)^{n-1} \exp\left( -\lambda \cdot \frac{1}{z} \right) \cdot \frac{1}{z^2}
\end{split}
$$

Expectation of $\frac{1}{\bar{X}_n}$:

$$
\begin{split}
\mathbb{E}\left( \frac{1}{\bar{X}_n} \right)
&= n \cdot \mathbb{E}\left( \frac{1}{Y} \right)
= n \int_0^\infty z f_Z(z) \, dz \\
&= n \cdot \frac{\lambda^n}{\Gamma(n)} \int_0^\infty \frac{1}{z^{n}} e^{-\lambda / z} \, dz
\end{split}
$$

Change of variable:

Let $u = \frac{\lambda}{z} \Rightarrow \frac{du}{dz} = -\frac{\lambda}{z^2} \Rightarrow dz = -\frac{z^2}{\lambda} \, du$

So:
$$
dz = -\frac{\lambda^n}{u^2} \cdot \frac{du}{\lambda}
= -\frac{\lambda^{n-1}}{u^2} du
$$

Substitute into the integral (rest continues...).
Continuing the expectation calculation:

$$
\begin{split}
\mathbb{E}\left( \frac{1}{\bar{X}_n} \right)
&= n \cdot \frac{\lambda^n}{\Gamma(n)} \int_\infty^0 \frac{u^n}{\lambda^n} e^{-u} \left(-\frac{\lambda}{u^2}\right) \, du \\
&= \frac{n \lambda}{\Gamma(n)} \int_0^\infty u^{n - 2} e^{-u} \, du \\
&= \lambda \cdot \frac{n \Gamma(n - 1)}{\Gamma(n)}
\end{split}
$$

Using this, we conclude:

$$
\mathbb{E} \left( \frac{\Gamma(n)}{\bar{X}_n \cdot n \cdot \Gamma(n - 1)} \right) = \lambda
$$

⟹ The estimator

$$
\boxed{\frac{\Gamma(n)}{\bar{X}_n \cdot n \cdot \Gamma(n - 1)}}
$$

is **unbiased** for $\lambda$.
