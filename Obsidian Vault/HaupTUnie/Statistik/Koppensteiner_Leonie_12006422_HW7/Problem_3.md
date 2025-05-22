## Exponential of the Mean

Suppose $X_1, X_2, \ldots$ are i.i.d. Poisson distributed with expectation $\lambda$, that is, $X_1 \sim \text{Poi}(\lambda)$.  
What is the limiting distribution of:
$$
\sqrt{n} \left( \exp(-\bar{X}_n) - \exp(-\lambda) \right)
$$
where $\bar{X}_n$ denotes the sample mean?

---
---


Central Limit Theorem (CLT)
Assume $X_1, X_2, \dots, X_n$ are i.i.d. random variables from a Poisson distribution with parameter $\lambda$. Then:

$$
\mathbb{E}[X_i] = \lambda, \quad \text{Var}(X_i) = \lambda
$$

So by the Central Limit Theorem we get :

$$
\sqrt{n}(\bar{X}_n - \lambda) = \sqrt{ n } (\bar{X}_{n}-\mathbb{E}(X_{1}))\xrightarrow{d} \underbrace{\mathcal{N}(0, \mathbb{V}(X_{1}))}_{=\mathcal{N}(0, \lambda)}
$$
![[Pasted image 20250509091354.png]]

---
Let $g(x) = e^{-x}$. Then:

$$
g'(\lambda) = -e^{-\lambda}
$$

By the Delta Method:

$$
\sqrt{n}(g(\bar{X}_n) - g(\lambda)) \xrightarrow{d} \mathcal{N}(0, \lambda \cdot (g'(\lambda))^2)
$$

$$
\begin{split}
g(x) := e^{-x} \\
g'(x) = -e^{-x}
\end{split}
$$

Then:
$$
\begin{split}
&\sqrt{n} \left( \exp(-\bar{X}_n) - \exp(-\lambda) \right)\\
&= \sqrt{n} \left( g(\bar{X}_n) - g(\lambda) \right)
\xrightarrow{d} \mathcal{N}(0, \lambda (g'(\lambda))^2)\\
&= \mathcal{N}(0, \lambda e^{-2\lambda})
\end{split}
$$
