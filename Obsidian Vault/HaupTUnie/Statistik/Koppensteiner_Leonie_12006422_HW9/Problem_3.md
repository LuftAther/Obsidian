**Gamma Method of Moments**

Let $X_1, \ldots, X_n$ be a sample from $\text{Gamma}(\alpha, \beta)$.
- Find the method of moments estimators of the shape $\alpha$ and the scale $\beta$, and derive their joint asymptotic distribution.

---
### Method of Moments for the Gamma Distribution

Let $X_i \sim \text{Gamma}(\alpha, \beta)$.

The **population moments** of the Gamma distribution are:
$$
\begin{split}
\mathbb{E}(X_i) &= \alpha \beta \\
\mathbb{E}(X_i^2) &= \operatorname{Var}(X_i) + \mathbb{E}(X_i)^2 = \alpha \beta^2 + (\alpha \beta)^2
\end{split}
$$

We match these with the **sample moments**:
- First moment: $\bar{X}_n = \hat{\alpha} \hat{\beta}$
- Second moment: $\frac{1}{n} \sum_{i=1}^n X_i^2 = \hat{\alpha} \hat{\beta}^2 + (\hat{\alpha} \hat{\beta})^2$

---

### Step-by-step Derivation

From the first moment:
$$
\hat{\alpha} = \frac{\bar{X}_n}{\hat{\beta}}
$$

Substitute into the second moment:
$$
\begin{split}
\frac{1}{n} \sum_{i=1}^n X_i^2 &= \hat{\alpha} \hat{\beta}^2 + \bar{X}_n^2 \\
\Leftrightarrow \hat{\alpha} &= \frac{\frac{1}{n} \sum_{i=1}^n X_i^2 - \bar{X}_n^2}{\hat{\beta}^2} \\
&= \frac{S_n^2}{\hat{\beta}^2}
\end{split}
$$
where $S_n^2 = \frac{1}{n} \sum X_i^2 - \bar{X}_n^2$ is the uncorrected sample variance.

Now equating both expressions for $\hat{\alpha}$:
$$
\frac{\bar{X}_n}{\hat{\beta}} = \frac{S_n^2}{\hat{\beta}^2}
$$

Solve for $\hat{\beta}$:
$$
\begin{split}
\Leftrightarrow \hat{\beta} \bar{X}_n &= S_n^2 \\
\Leftrightarrow \hat{\beta} &= \frac{S_n^2}{\bar{X}_n}
\end{split}
$$

Plug into the expression for $\hat{\alpha}$:
$$
\hat{\alpha} = \frac{\bar{X}_n}{\hat{\beta}} = \frac{\bar{X}_n^2}{S_n^2}
$$


$\boxed{\hat{\alpha} = \frac{\bar{X}_n^2}{S_n^2}}$ $\boxed{\hat{\beta} = \frac{S_n^2}{\bar{X}_n}}$
### Asymptotic Distribution

Define:
$$
Y_n := \frac{1}{n} \sum_{i=1}^n X_i^2, \quad
S_n^2 := Y_n - \bar{X}_n^2
$$

**Needed later:**
Expectation of $X_1^n$ when $X_1 \sim \text{Gamma}(\alpha, \beta)$:
$$
\begin{split}
\mathbb{E}(X_1^n)
&= \int_0^\infty x^n \cdot \frac{1}{\Gamma(\alpha)\beta^\alpha} x^{\alpha-1} e^{-x/\beta} dx \\
&= \frac{1}{\Gamma(\alpha)\beta^\alpha} \int_0^\infty x^{\alpha - 1 + n} e^{-x/\beta} dx \\
&\text{Substitute } u = \frac{x}{\beta} \Rightarrow dx = \beta du \\
&= \frac{1}{\Gamma(\alpha)\beta^\alpha} \int_0^\infty (\beta u)^{\alpha + n - 1} e^{-u} \beta du \\
&= \frac{\beta^{\alpha+n}}{\Gamma(\alpha)\beta^\alpha} \int_0^\infty u^{\alpha + n - 1} e^{-u} du \\
&= \frac{\beta^n \Gamma(\alpha + n)}{\Gamma(\alpha)}
\end{split}
$$

---

Assume:
$$
\mathbb{V}(X_1) \leq \mathbb{E}(X_1^2) < \infty, \quad
\mathbb{V}(X_1^2) \leq \mathbb{E}(X_1^4) < \infty
$$

Then, by the **Central Limit Theorem**:
$$
\sqrt{n} 
\left(
\begin{pmatrix}
\bar{X}_n \\
Y_n
\end{pmatrix}
-
\begin{pmatrix}
\mathbb{E}(X_1) \\
\mathbb{E}(X_1^2)
\end{pmatrix}
\right)
\overset{d}{\longrightarrow}
\mathcal{N}(0, \Sigma)
$$

Where the covariance matrix $\Sigma$ is:
$$
\Sigma = \begin{pmatrix}
\mathbb{V}(X_1) & \text{Cov}(X_1, X_1^2) \\
\text{Cov}(X_1, X_1^2) & \mathbb{V}(X_1^2)
\end{pmatrix}
$$
### Applying the Delta Method

Define the transformation:
$$
g(x, y) =
\left(
\frac{x}{y - x^2}, \quad \frac{y - x^2}{x}
\right)
$$

Its Jacobian is:
$$
J_g(x, y) =
\begin{pmatrix}
\frac{2x y}{(y - x^2)^2} & \frac{-x^2}{(y - x^2)^2} \\
\frac{-x^2 + y}{x^2} & \frac{1}{x}
\end{pmatrix}
$$

Evaluate at the expected values:
$$
g\left(\mathbb{E}(X_1), \mathbb{E}(X_1^2)\right) =
\left(
\frac{\mathbb{E}(X_1)^2}{\mathbb{E}(X_1^2) - \mathbb{E}(X_1)^2}, \quad
\frac{\mathbb{E}(X_1^2) - \mathbb{E}(X_1)^2}{\mathbb{E}(X_1)}
\right) = (\alpha, \beta)
$$

Let $B$ be the Jacobian evaluated at the expectations:
$$
B := J_g\left(\mathbb{E}(X_1), \mathbb{E}(X_1^2)\right) =
\begin{pmatrix}
\frac{2 \mathbb{E}(X_1) \mathbb{E}(X_1^2)}{\mathbb{V}(X_1)^2} &
\frac{-\mathbb{E}(X_1)^2}{\mathbb{V}(X_1)^2} \\
\frac{-\mathbb{E}(X_1)^2 + \mathbb{E}(X_1^2)}{\mathbb{E}(X_1)^2} &
\frac{1}{\mathbb{E}(X_1)}
\end{pmatrix}
$$

From the multivariate CLT and the Delta Method:
$$
\sqrt{n}
\left(
\begin{pmatrix}
\hat{\alpha} \\
\hat{\beta}
\end{pmatrix}
-
\begin{pmatrix}
\alpha \\
\beta
\end{pmatrix}
\right)
\overset{d}{\longrightarrow}
\mathcal{N}\left(0, B \Sigma B^\top \right)
$$

Thus, the asymptotic distribution is:
$$
\begin{pmatrix}
\hat{\alpha} \\
\hat{\beta}
\end{pmatrix}
\approx
\mathcal{N}\left(
\begin{pmatrix}
\alpha \\
\beta
\end{pmatrix},
B \Sigma B^\top
\right)
$$
