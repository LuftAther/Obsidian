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
