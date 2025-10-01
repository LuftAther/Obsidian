## Problem 1: Mean of Indicators

Given an i.i.d. sequence of random variables $X_1, X_2, \ldots$ and a set $A \subseteq \mathbb{R}$. Define

$$
\bar{Y}_n = \frac{1}{n} \sum_{i=1}^n \mathbb{I}_A(X_i)
$$

Show that $\bar{Y}_n$ converges in probability to $\mathbb{P}(X_1 \in A)$. In particular, show that

$$
\bar{Y}_n = \mathbb{P}(X_1 \in A) + \mathcal{O}_p(n^{-1/2})
$$

---

Let $X_1, X_2, \ldots$ be i.i.d. random variables and let $A \subset \mathbb{R}$. Define $Y_i := \mathbb{I}_A \circ X_i$

This means: $Y_i = 1$ if $X_i \in A$, and $Y_i = 0$ otherwise. Then the expectation is:

$$
\mathbb{E}(Y_i) = \mathbb{E}(\mathbb{I}_A \circ X_1) = \int \mathbb{I}_A(x) \, d\mathbb{P}(x) = \mathbb{P}(A) = \mathbb{P}(X_1 \in A)
$$

Since the $Y_i$ are i.i.d., their sample mean is:

$$
\bar{Y}_n := \frac{1}{n} \sum_{i=1}^n Y_i = \frac{1}{n} \sum_{i=1}^n \mathbb{I}_A(X_i)
$$

By the **Weak Law of Large Numbers** (WLLN):
![[Pasted image 20250502224104.png]]
we get
$$
\bar{Y}_n \xrightarrow{p} \mathbb{P}(X_1 \in A)
$$

If the **second moments exist**, a stronger result holds. Specifically, the **Central Limit Theorem** (CLT) implies:

$$
\sqrt{n}(\bar{Y}_n - \mathbb{P}(X_1 \in A)) \xrightarrow{d} \mathcal{N}(0, \sigma^2)
$$

and therefore:

$$
\bar{Y}_n - \mathbb{P}(X_1 \in A) = \mathcal{O}_p(n^{-1/2})
$$

which is exactly what was to be shown:

$$
\bar{Y}_n = \mathbb{P}(X_1 \in A) + \mathcal{O}_p(n^{-1/2})
$$