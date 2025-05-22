##  Mean of Squares and Squared Mean

Given an i.i.d. sequence $X_1, X_2, \ldots$ with finite fourth moment, meaning $\mathbb{E}[X_1^4] < \infty$.  
Let:

- $Y_k = X_k^2$ for $k = 1, 2, \ldots$
- $\bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i$
- $\bar{Y}_n = \frac{1}{n} \sum_{i=1}^n Y_i$
What is the **approximate distribution** of the difference:
$$
\bar{Y}_n - \bar{X}_n^2
$$
for large $n$?

---
---
$$
\begin{split}
\infty > \mathbb{E}(X_1^4) &= \mathbb{E}((X_1^2)^2) \geq \mathbb{E}(X_1^2)^2 \geq \mathbb{E}(X_1)^4\\
\Rightarrow \mathrm{Var}(X_1^2) &= \mathbb{E}(X_1^4) - \mathbb{E}(X_1^2)^2 < \infty ;\\
\mathrm{Var}(X_1) &= \mathbb{E}(X_1^2) - \mathbb{E}(X_1)^2 < \infty
\end{split}
$$
$$
X_1, \ldots \quad \text{and} \quad X_1^2, \ldots \quad \text{are i.i.d.}
$$

Therefore, we can apply **WLLN**[^2] to obtain:

$$
\begin{split}
\overline{Y}_n \to \mu_Y := \mathbb{E}(Y_1)\\
\overline{X}_n \to \mu_X := \mathbb{E}(X_1)
\end{split}
$$
As convergence in probability to a constant and convergence in distribution to a constant are the sample, Slutsky gives us:

$$
\overline{Y}_n - \overline{X}_n^2 \xrightarrow{d} \mu_Y - \mu_X^2
$$



[^2]: ![[Pasted image 20250509092319.png]]
