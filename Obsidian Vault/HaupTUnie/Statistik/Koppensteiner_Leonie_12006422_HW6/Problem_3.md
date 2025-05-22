## Problem 3: CLT Implications

Suppose $X_1, X_2, \ldots$ is a sequence of i.i.d. random variables.

1. If $\theta$ is a constant and

$$
\sqrt{n}(X_n - \theta) \xrightarrow{d} Y
$$

where $Y$ is any random variable, show that

$$
X_n \xrightarrow{p} \theta
$$

2. Given that the variance $\sigma^2$ of $X_1$ is non-zero and finite. Let $S_n = S_n(X_1, \ldots, X_n)$ be some function of the data, such that

$$
S_n \xrightarrow{p} \sigma
$$

Show that

$$
\frac{\sqrt{n}(X_n - \mu)}{S_n} \xrightarrow{d} \mathcal{N}(0, 1)
$$

---

### 1. Show that if $\sqrt{n}(X_n - \theta) \xrightarrow{d} Y$ for some random variable $Y$, then $X_n \xrightarrow{p} \theta$

We take inspiration from Note 6, page 53/112.
![[Pasted image 20250502232014.png]]

$$
\bar{X}_n - \theta = \underbrace{\frac{1}{\sqrt{n}}}_{\to 0} \underbrace{\sqrt{n}(X_n - \theta)}_{\xrightarrow{d} y} \xrightarrow{d} \frac{1}{\sqrt{n}} \cdot Y \xrightarrow{d} 0 \cdot Y = 0
$$

and since convergence in distribution to a constant implies convergence in probability:
$$
\bar{X}_n \xrightarrow{p} \theta
$$

---

### 2. Show that if $S_n \xrightarrow{p} \sigma$ and $\sigma^2 > 0$, then

$$
\frac{\sqrt{n}(\bar{X}_n - \mu)}{S_n} \xrightarrow{d} \mathcal{N}(0,1)
$$

From the **Central Limit Theorem (CLT)**, we know:

$$
\sqrt{n}(\bar{X}_n - \mu) \xrightarrow{d} Z \sim \mathcal{N}(0, \sigma^2)
$$

We also know that:

$$
S_n \xrightarrow{p} \sigma
$$

Then **Slutsky’s theorem**:

![[Pasted image 20250502233154.png]]
![[Pasted image 20250502233049.png]]
gives us:

$$
\frac{\sqrt{n}(\bar{X}_n - \mu)}{S_n} \xrightarrow{d} \frac{Z}{\sigma} \sim \mathcal{N}\left(0, \frac{\sigma^2}{\sigma^2}\right) = \mathcal{N}(0,1)
$$
