## Problem 4: Log-normal Distribution

A random variable $Y$ is **log-normal distributed** if $X = \ln(Y) \sim \mathcal{N}(\mu, \sigma^2)$.

---

### 1. Determine the density $f_Y(y; \mu, \sigma^2)$

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
