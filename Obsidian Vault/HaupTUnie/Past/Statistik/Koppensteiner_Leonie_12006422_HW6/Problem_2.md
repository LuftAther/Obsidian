## Problem 2: Moving Average

Suppose that $X_1, X_2, \ldots$ are i.i.d. random variables with mean $\mu$ and variance $\tau^2$. For each $k \geq 1$, define

$$
Y_k = \sum_{i=0}^{m-1} X_{k+i}
$$

The sequence $Y_1, Y_2, \ldots$ is called a moving average time series of order $m$, abbreviated as MA(m). Show that

$$
Y_n = \frac{1}{n} \sum_{k=1}^n Y_k = m\mu + \mathcal{O}_p(n^{-1/2})
$$

---
![[Pasted image 20250502224104.png]]
Let $X_1, X_2, \dots$ be i.i.d. random variables with $\mathbb{E}(X_i) = \mu$ and $\operatorname{Var}(X_i) = \tau^2 < \infty$. Define the moving average of order $m$:

$$
Y_k := \sum_{i=0}^{m-1} X_{k+i}
$$

Then the expected value of $Y_k$ is: $\mathbb{E}(Y_k) = \sum_{i=0}^{m-1} \mathbb{E}(X_{k+i}) = m \cdot \mathbb{E}(X_1) = m \mu$
We aim to compute the average: $\bar{Y}_n := \frac{1}{n} \sum_{k=1}^{n} Y_k$
We construct an index mapping via functions $\alpha(j)$ such that: $\sum_{j=1}^{m} \alpha(j) = n \quad \text{and} \quad \alpha(j)(-1) + m + j \leq n$
We rewrite: $\bar{Y}_n = \frac{1}{n} \sum_{k=1}^{n} Y_k = \frac{1}{n} \sum_{j=1}^{m} \sum_{k=0}^{\alpha(j)-1} Y_{k \cdot m + j}$
We re-express the sum: $= \frac{1}{n} \sum_{j=1}^{m} \alpha(j) \underbrace{\left( \frac{1}{\alpha(j)} \sum_{k=0}^{\alpha(j)-1} Y_{k \cdot m + j} \right)}_{\text{mean of iid nv's -> we can aply WLLN}}$

Hence: $\bar{Y}_n = \frac{1}{n} \sum_{j=1}^{m} \alpha(j) \left( m \mu + \mathcal{O}_p(\alpha(j)^{-1/2}) \right)$
Split the sum: $= \left(m \mu + \mathcal{O}_p(n^{-1/2})\right) \left( \frac{1}{n} \sum_{j=1}^{m} \alpha(j) \right)$
By construction: $\sum_{j=1}^{m} \alpha(j) = n \Rightarrow \frac{1}{n} \sum_{j=1}^{m} \alpha(j) = 1$
Thus we conclude: $\bar{Y}_n = m \mu + \mathcal{O}_p(n^{-1/2})$