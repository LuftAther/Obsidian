Under i.i.d. sampling, every $k$-th sample moment is asymptotically normal if population moments of order $2k$ exist.

Show that:

$$
\sqrt{n} \left( \frac{1}{n} \sum_{i=1}^n X_i^k - \mathbb{E}[X_1^k] \right) \overset{d}{\longrightarrow} \mathcal{N}\left(0, \mathbb{E}[X_1^{2k}] - \left(\mathbb{E}[X_1^k]\right)^2\right)
$$

Assuming that moments of order 4 exist, use the above formula to show that:

$$
\sqrt{n} \left( \frac{n-1}{n} S_n^2 - \mathrm{Var}(X_1) \right) \overset{d}{\longrightarrow} \mathcal{N}(0, \mu_4 - \mu_2^2)
$$

where $\mu_2$, $\mu_4$ are the second and fourth *central* moments.

---
We assume that **moments of order $2k$ exist**, so:

$\mathrm{Var}(X_1^k)$ exists  and therfore  the central limit theorem (CLT) implies:

$$\sqrt{n} \left( \frac{1}{n} \sum_{i=1}^n X_i^k - \mathbb{E}[X_1^k] \right) \overset{d}{\longrightarrow} \mathcal{N}(0, \mathrm{Var}(X_1^k))$$

Let $\mu_n = \mathbb{E}[(X_1 - \mathbb{E}[X_1])^2]$ be the **second central moment**.

We use the known decomposition: $\frac{n - 1}{n} s_n^2 = \frac{1}{n} \sum (X_i - \bar{X})^2 = \frac{1}{n} \sum X_i^2 - \bar{X}^2$[^1]

With: $\bar{X} = \frac{1}{n} \sum X_i \quad \text{and} \quad \bar{Y} = \frac{1}{n} \sum X_i^2$
This setup is used to derive the asymptotic distribution of $s_n^2$ and ultimately:

$$\sqrt{n} \left( \frac{n - 1}{n} s_n^2 - \mathrm{Var}(X_1) \right) \overset{d}{\longrightarrow} \mathcal{N}(0, \mu_4 - \mu_2^2)$$

where $\mu_4$ is the 4th central moment.
From the **multivariate central limit theorem (CLT)**, we have:

$$
\sqrt{n} 
\left(\begin{pmatrix}
\bar{X} \\
\bar{Y}
\end{pmatrix}
-
\begin{pmatrix}
\mathbb{E}(X_1) \\
\mathbb{E}(X_1^2)
\end{pmatrix}\right)
\overset{d}{\longrightarrow} \mathcal{N}
\left(
0,
\Sigma
\right)
$$

where the asymptotic covariance matrix $\Sigma$ is:

$$
\Sigma =
\begin{pmatrix}
\mathrm{Var}(X_i) & \mathrm{Cov}(X_i, X_1^2) \\
\mathrm{Cov}(X_i, X_i^2) & \mathrm{Var}(X_i)
\end{pmatrix}
$$
With $Var(x_{1})= \mathbb{E}(X_{1}²)-\mathbb{E}(X_{1}^2)$
Let $g(x, y) = y - x^2$.
Then we have:

- $\nabla g(x, y) = \left( \frac{\partial g}{\partial x}, \frac{\partial g}{\partial y} \right) = (-2x, 1)$
- $g(\bar{X}, \bar{Y}) = \frac{n - 1}{n} s_n^2$
- $g(\mu, \mu_Y) = \mathrm{Var}(X_1) = (-2\mu, 1)$

Apply the **delta method** to $g(\bar{X}, \bar{Y})$ using the multivariate CLT:
$$
\sqrt{n} \left( g(\bar{X}, \bar{Y}) - \mathrm{Var}(X_1) \right)
\overset{d}{\longrightarrow}
\mathcal{N}(0, \nabla g(\mu, \mu_Y)^\top \Sigma \nabla g(\mu, \mu_Y))
$$

So we get $\sqrt{n} \left( \frac{n - 1}{n} s_n^2 - \mathrm{Var}(X_1) \right)\overset{d}{\longrightarrow}\mathcal{N}(0, \sigma^2)$
$\sqrt{n} \left( \frac{n - 1}{n} s_n^2 - \mathrm{Var}(X_1) \right) \overset{d}{\longrightarrow} \mathcal{N}(0, \mu_4 - \mu_2^2)$
with:
$$
\sigma^2 = \nabla g^\top \Sigma \nabla g = (-2\mu, 1)
\begin{pmatrix}
\mathrm{Var}(X^2) & \mathrm{Cov}(X^2, X) \\
\mathrm{Cov}(X^2, X) & \mathrm{Var}(X)
\end{pmatrix}
\begin{pmatrix}
-2\mu \\
1
\end{pmatrix}
$$
$\sqrt{n} \left( \frac{n - 1}{n} s_n^2 - \mathrm{Var}(X_1) \right) \overset{d}{\longrightarrow} \mathcal{N}(0, \mu_4 - \mu_2^2)$
The computation of the asymptotic variance gives:

$$
\begin{split}
= 4\mu^2 \, \mathrm{Var}(X_i) - 4\mu \mathrm{Cov}(X_i, X_i^2) + \mathrm{Var}(X_i^2)\\
= 4\mu^2 (\mathbb{E}(X_i^4) - \mathbb{E}(X_i^2)^2) - 4\mu (\mathbb{E}(X_i^3) - \mathbb{E}(X_i^2)\mathbb{E}(X_i)) + \mathbb{E}(X_i^4) - \mathbb{E}(X_i^2)^2\\
 = 4 \mathbb{E}(X_i)^2 \mathbb{E}(X_i^4)
- 4 \mathbb{E}(X_i)^2 \mathbb{E}(X_i^2)^2\\
- 4 \mathbb{E}(X_i) \mathbb{E}(X_i^3)
+ 4 \mathbb{E}(X_i)^2 \mathbb{E}(X_i^2)
+ \mathbb{E}(X_i^4)
- \mathbb{E}(X_i^2)^2
\end{split}
$$

$$
\begin{split}
\mu_4 - \mu_2^2 &= \mathbb{E}\left[(X_i - \mathbb{E}(X_i))^4\right] - \left(\mathbb{E}\left[(X_i - \mathbb{E}(X_i))^2\right]\right)^2\\
&= \mathbb{E}\left(X_i^4 - 4 X_i^3 \mathbb{E}(X_i) + 6 X_i^2 \mathbb{E}(X_i)^2
- 4 X_i \mathbb{E}(X_i)^3 + \mathbb{E}(X_i)^4\right)\\
& - \left( \mathbb{E}(X_i^2) - \mathbb{E}(X_i)^2 \right)^2\\
&= \mathbb{E}(X_i^4)
- 4 \mathbb{E}(X_i^3) \mathbb{E}(X_i)
+ 6 \mathbb{E}(X_i^2) \mathbb{E}(X_i)^2
- 4 \mathbb{E}(X_i) \mathbb{E}(X_i)^3\\
&+ \mathbb{E}(X_i)^4
- \mathbb{E}(X_i^2)^2
+ 2 \mathbb{E}(X_i^2) \mathbb{E}(X_i)^2
- \mathbb{E}(X_i)^4

\end{split}
$$
$$
\Rightarrow \sqrt{n} \left( \frac{n - 1}{n} s_n - \mathrm{Var}(X_1) \right)
\overset{d}{\longrightarrow} \mathcal{N}(0, \mu_4 - \mu_2^2)
$$

[^1]: Internet
