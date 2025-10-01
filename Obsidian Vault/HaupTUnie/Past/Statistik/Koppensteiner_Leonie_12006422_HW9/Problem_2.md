**Binomial Method of Moments**
Let $X_1, \ldots, X_n$ be i.i.d. $\text{Bin}(N, p)$, where both $N$ and $p$ are unknown.

- Find the method of moments estimators of $N$ and $p$.

---
**Sample Moments (Slides)**

If $X_1, \dots, X_n$ are a random sample, the sample moments are the moments of the *empirical distribution* associated with the vector $\mathbf{X} = (X_1, \dots, X_n)^T$.

1. The **first moment** is the **sample mean**: $\bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i$
2. The **k-th sample moment**:  $\frac{1}{n} \sum_{i=1}^n X_i^k$
3. The **k-th central moment**: $\frac{1}{n} \sum_{i=1}^n (X_i - \bar{X}_n)^k$

---

## Population Moments:

$$
\mathbb{E}(X_i) = Np
$$
Where: $\operatorname{Var}(X_i) = \mathbb{E}(X_i^2) - \left(\mathbb{E}(X_i)\right)^2$: 
$$
\begin{split}
\mathbb{E}(X_i^2) &= \operatorname{Var}(X_i) + \left( \mathbb{E}(X_i) \right)^2 \\
&= Np(1 - p) + (Np)^2 \\
&= Np(1 - p) + N^2 p^2
\end{split}
$$
![[Pasted image 20250522135932.png]]

This leads to:

$$
\left\{
\begin{array}{l}
\frac{1}{n} \sum\limits_{i=1}^n X_i = Np \\\\
\frac{1}{n} \sum\limits_{i=1}^n X_i^2 = Np(1 - p) + N^2 p^2
\end{array}
\right.
$$
We plug in \( Np \):

$$
\begin{split}
\frac{1}{n} \sum_{i=1}^n X_i^2 &= \bar{X}_n (1 - p) + \bar{X}_n^2\\
\iff 1 - p &= \frac{\frac{1}{n} \sum_{i=1}^n X_i^2 - \bar{X}_n^2}{\bar{X}_n} \\
&\text{if } \bar{X}_n \ne 0 \text{; else } Np = 0 \Rightarrow p = 0\\
\iff p &= 1 - \frac{1}{n \bar{X}_n} \sum_{i=1}^n X_i^2 + \frac{\bar{X}_n^2}{\bar{X}_n} \\
&= 1 - \frac{1}{n \bar{X}_n} \sum_{i=1}^n X_i^2 + \bar{X}_n\\
\Rightarrow N &= \frac{\bar{X}_n}{p}
= \frac{\bar{X}_n}{1 - \frac{1}{n \bar{X}_n} \sum_{i=1}^n X_i^2 - \bar{X}_n}
\end{split}
$$
