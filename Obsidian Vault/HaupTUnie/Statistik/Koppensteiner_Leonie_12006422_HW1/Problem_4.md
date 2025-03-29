## Log-normal Distribution

A random variable $Y$ is **log-normal distributed** if $X = \ln(Y) \sim \mathcal{N}(\mu, \sigma^2)$.
**Problem 4** *(log-normal distribution)*.  
A random variable $Y$ is *log-normally distributed* if $X = \ln(Y)$ is normally distributed.

1. Determine the density $f_Y(y; \mu, \sigma^2)$ of $Y$ if $X = \ln(Y) \sim \mathcal{N}(\mu, \sigma^2)$.

2. Plot the density $f_Y(y; \mu, \sigma^2)$ for different values of $\mu$ and $\sigma^2$.

3. Compute all moments $\mathbb{E}[Y^k]$ for $k \in \mathbb{N}$ of $Y$ for the special case of $\mu = 0$ and $\sigma^2 = 1$, where

$$
f_Y(y) = f_Y(y; 0, 1) = \frac{1}{\sqrt{2\pi} y} e^{-(\ln y)^2 / 2}
$$

4. Let $f_Z(z) = (1 + \sin(2\pi \ln z)) f_Y(z)$ on $(0, \infty)$ and show that all moments of $Z \sim f_Z$, that is $\mathbb{E}[Z^k]$, are identical to the moments of $Y$.  
In other words, show that $\mathbb{E}[Z^k] = \mathbb{E}[Y^k]$ for $k = 1, 2, \dots$ if $Z \sim f_Z$ and $Y \sim f_Y$.


---

### 1. Determine the density $f_Y(y; \mu, \sigma^2)$ if $X = \ln(Y) \sim \mathcal{N}(\mu, \sigma^2)$

Let $X = \ln(Y) \sim \mathcal{N}(\mu, \sigma^2)$. To find the density of $Y$, use a **change of variables**:

$$
f_Y(y) = f_X(\ln y) \cdot \left| \frac{d}{dy} \ln y \right| = \frac{1}{y} f_X(\ln y)
$$

The density of a normal variable $X \sim \mathcal{N}(\mu, \sigma^2)$ is:

$$
f_X(x) = \frac{1}{\sqrt{2\pi \sigma^2}} \exp\left( -\frac{(x - \mu)^2}{2\sigma^2} \right)
$$

Substitute $x = \ln y$, then:

$$
f_Y(y; \mu, \sigma^2) = \frac{1}{y \sqrt{2\pi \sigma^2}} \exp\left( -\frac{(\ln y - \mu)^2}{2\sigma^2} \right), \quad y > 0
$$

---

### 2. Plot the density $f_Y(y; \mu, \sigma^2)$

In R, you can use:

```r
curve(dlnorm(x, meanlog = 0, sdlog = 1), from = 0.01, to = 5, col = "blue", lwd = 2)
curve(dlnorm(x, meanlog = 1, sdlog = 0.5), from = 0.01, to = 5, col = "red", add = TRUE)
curve(dlnorm(x, meanlog = -1, sdlog = 1.5), from = 0.01, to = 5, col = "green", add = TRUE)
legend("topright", legend = c("μ=0, σ²=1", "μ=1, σ²=0.25", "μ=-1, σ²=2.25"),
       col = c("blue", "red", "green"), lwd = 2)
```

### 3. Compute all moments $\mathbb{E}[Y^k]$ for $k \in \mathbb{N}$ of $Y$ for the special case of $\mu = 0$ and $\sigma^2 = 1$, where

$$
f_Y(y) = f_Y(y; 0, 1) = \frac{1}{\sqrt{2\pi} y} e^{-(\ln y)^2 / 2}
$$



We compute the $k$-th moment of $Y \sim \text{LogNormal}(0, 1)$:

$$
m_k = \mathbb{E}(Y^k) 
= \frac{1}{\sqrt{2\pi}} \int_0^{\infty} y^{k-1} \exp\left( -\frac{(\ln y)^2}{2} \right) dy
$$

Substitution:  Let $u = \ln y \Rightarrow \frac{du}{dy} = \frac{1}{y}, \quad dy = y \, du$

$$
= \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} e^{u(k-1)} \cdot e^{-u^2/2} \cdot e^u \, du 
= \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} \exp\left( -\frac{1}{2}(u^2 - 2ku) \right) du
$$

Complete the square by using a construktiv 0:

$$
= \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} \exp\left( -\frac{1}{2}(u^2 - 2ku + k^2) \right) \cdot \exp\left( \frac{k^2}{2} \right) du
$$

$$
= \frac{e^{k^2/2}}{\sqrt{2\pi}} \int_{-\infty}^{\infty} \exp\left( -\frac{1}{2}(u - k)^2 \right) du
$$

$$
= e^{k^2/2} \int_{-\infty}^{\infty} f_H(u) \, du = e^{k^2/2}
\quad \text{where} \quad H \sim \mathcal{N}(k, 1)
$$

Since the normal density integrates to 1, we conclude:

$$
\mathbb{E}(Y^k) = e^{k^2 / 2}
$$
---
### 4. Let $f_Z(z) = (1 + \sin(2\pi \ln z)) f_Y(z)$ on $(0, \infty)$ and show that all moments of $Z \sim f_Z$, that is $\mathbb{E}[Z^k]$, are identical to the moments of $Y$.  

In other words, show that $\mathbb{E}[Z^k] = \mathbb{E}[Y^k]$ for $k = 1, 2, \dots$ if $Z \sim f_Z$ and $Y \sim f_Y$.

We want to show that all moments of $Z \sim f_Z$, i.e., $\mathbb{E}[Z^k]$, are identical to the moments of $Y \sim f_Y$.  
So, we need to show that $\mathbb{E}[Z^k] = \mathbb{E}[Y^k]$ for $k = 1, 2, \ldots$.

$$
m_k = \mathbb{E}(Z^k) = \frac{1}{\sqrt{2\pi}} \int_0^{\infty} \frac{1 + \sin(2\pi \ln z)}{z} \exp\left( -\frac{(\ln z)^2}{2} \right) z^k \, dz
$$

$$
= \underbrace{  \frac{1}{\sqrt{2\pi}} \int_0^{\infty} \exp\left( -\frac{(\ln z)^2}{2} \right) z^{k - 1} \, dz}_{= \mathbb{E}(y^k)} + \underbrace{ \frac{1}{\sqrt{2\pi}} \int_0^{\infty} \sin(2\pi \ln z) \exp\left( -\frac{(\ln z)^2}{2} \right) z^{k - 1} \, dz}_{\overset{!}{=} 0}
$$

Breaking the integral into two parts:

$$
= \mathbb{E}(Y^k) + \frac{1}{\sqrt{2\pi}} \int_0^{\infty} \sin(2\pi \ln z) \exp\left( -\frac{(\ln z)^2}{2} \right) z^{k - 1} \, dz
$$

Now, note that the second integral has an **odd function** in the integrand:

$$
\sin(2\pi \ln z)
$$

Since the integrand is odd and integrated over the entire positive real line (due to the symmetry of the Gaussian distribution in the logarithmic domain), this integral evaluates to zero:

$$
\int_0^{\infty} \sin(2\pi \ln z) \exp\left( -\frac{(\ln z)^2}{2} \right) z^{k - 1} \, dz = 0
$$

Thus:

$$
m_k = \mathbb{E}(Z^k) = \mathbb{E}(Y^k)
$$

We have shown that:

$$
\mathbb{E}(Z^k) = \mathbb{E}(Y^k) \quad \text{for} \quad k = 1, 2, \ldots
$$
### Integral Evaluation for Part 4

We want to evaluate the integral:

$$
\int_0^{\infty} \sin(2\pi \ln z) \exp \left( -\frac{(\ln z)^2}{2} \right) z^{k-1} \, dz
$$

**Substitution:**  
Let $u = \ln z$ so that:

$$
\frac{du}{dz} = \frac{1}{z}, \quad dz = z \, du = e^u \, du
$$

The integral becomes:

$$
= \int_{-\infty}^{\infty} e^{uk} \sin(2\pi u) \exp\left( -\frac{u^2}{2} \right) \, du
$$

$$
= \int_{-\infty}^{\infty} \sin(2\pi u) \exp \left( -\frac{u^2}{2} + ku \right) \, du
$$

---

Now, we notice that the integrand involves the product of a sinusoidal function $\sin(2\pi u)$ and a Gaussian-like term $\exp \left( -\frac{u^2}{2} + ku \right)$. This integral is over the entire real line.

By symmetry, this integral is **zero** because the integrand is an odd function when considered over the symmetric interval $(-\infty, \infty)$.

$$
\therefore \int_{-\infty}^{\infty} \sin(2\pi u) \exp \left( -\frac{u^2}{2} + ku \right) \, du = 0
$$

Thus, the contribution from the oscillatory term vanishes.
### Proof of Symmetry Property

We want to prove that a certain expression involving the exponential function is symmetric.  

Let $\alpha \in \mathbb{R}$. The claim is that the following expression is symmetric with respect to $k$:

$$
\exp \left( -\frac{(k + \alpha)^2}{2} + k(k + \alpha) \right) = \exp \left( -\frac{(k - \alpha)^2}{2} + k(k - \alpha) \right)
$$

We proceed by simplifying both sides.

#### Left-Hand Side

$$
- \frac{(k + \alpha)^2}{2} + k(k + \alpha) = - \frac{1}{2} (k^2 + 2\alpha k + \alpha^2) + k^2 + \alpha k
$$

$$
= -\frac{1}{2}k^2 - \alpha k - \frac{1}{2}\alpha^2 + k^2 + \alpha k
$$

$$
= \frac{1}{2}k^2 - \frac{1}{2}\alpha^2
$$

#### Right-Hand Side

$$
- \frac{(k - \alpha)^2}{2} + k(k - \alpha) = - \frac{1}{2} (k^2 - 2\alpha k + \alpha^2) + k^2 - \alpha k
$$

$$
= -\frac{1}{2}k^2 + \alpha k - \frac{1}{2}\alpha^2 + k^2 - \alpha k
$$

$$
= \frac{1}{2}k^2 - \frac{1}{2}\alpha^2
$$

#### Comparison

Both sides simplify to the same result:

$$
\frac{1}{2}k^2 - \frac{1}{2}\alpha^2
$$

$$
\therefore \quad 0 = 0
$$

The expression is symmetric as claimed.
### Important Remark

The assumption: $\mathbb{E}(X^k) = \mathbb{E}(Y^k)$ implies $f_X = f_Y$ **only if** 

$$
\operatorname{supp}(f_X), \operatorname{supp}(f_Y)
$$

are compact, which is **not the case here**.
