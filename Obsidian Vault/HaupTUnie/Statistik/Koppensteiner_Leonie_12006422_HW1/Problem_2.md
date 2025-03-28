## Problem 2: Inverse Sampling

Let $X$ be a continuous random variable with values in $[-\pi, \pi]$ and density:
$$
f_X(x) \propto |\sin(x)|
$$
This means there exists a constant $a \in \mathbb{R}$ such that:
$$
f_X(x) = a |\sin(x)|
$$

---

### 1. Determine the constant $a \in \mathbb{R}$

We normalize the density so that the total integral over the domain equals 1:
$$
\int_{-\pi}^{\pi} f_X(x) dx = 1 \Rightarrow \int_{-\pi}^{\pi} a |\sin(x)| dx = 1
$$

Since $|\sin(x)|$ is symmetric around 0:
$$
\int_{-\pi}^{\pi} |\sin(x)| dx = 2 \int_0^{\pi} \sin(x) dx = 2 [-\cos(x)]_0^{\pi} = 2(1 + 1) = 4
$$

So:
$$
a \cdot 4 = 1 \Rightarrow a = \frac{1}{4}
$$

Thus:
$$
f_X(x) = \frac{1}{4} |\sin(x)|, \quad x \in [-\pi, \pi]
$$

---

### 2. Compute the cumulative distribution function (CDF) $F_X$

We define:
$$
F_X(x) = \int_{-\pi}^{x} f_X(t) dt = \int_{-\pi}^{x} \frac{1}{4} |\sin(t)| dt
$$

Because $|\sin(t)|$ has a known structure, we can compute this piecewise:
- From $-\pi$ to 0, $\sin(t) \leq 0 \Rightarrow |\sin(t)| = -\sin(t)$
- From 0 to $\pi$, $\sin(t) \geq 0 \Rightarrow |\sin(t)| = \sin(t)$

So:

- For $x \in [-\pi, 0]$:
$$
F_X(x) = \frac{1}{4} \int_{-\pi}^{x} -\sin(t) dt = \frac{1}{4} [\cos(t)]_{-\pi}^{x} = \frac{1}{4} (\cos(x) + 1)
$$

- For $x \in [0, \pi]$:
$$
F_X(x) = F_X(0) + \frac{1}{4} \int_0^x \sin(t) dt = \frac{1}{4}(1) + \frac{1}{4} [-\cos(t)]_0^x = \frac{1}{4}(1 + \cos(0) - \cos(x)) = \frac{1}{4}(2 - \cos(x))
$$

So the full CDF is:
$$
F_X(x) = 
\begin{cases}
\frac{1}{4}(1 + \cos(x)), & x \in [-\pi, 0] \\
\frac{1}{4}(2 - \cos(x)), & x \in [0, \pi]
\end{cases}
$$

---

### 3. Let $U \sim \mathcal{U}(0,1)$, what is the distribution of $F_X^{-1}(U)$?

By the inverse transform sampling theorem, $F_X^{-1}(U) \sim X$, i.e., it has the same distribution as $X$.

So:
- If we can compute or numerically approximate $F_X^{-1}(u)$, then we can sample from the distribution of $X$ using $U \sim \mathcal{U}(0,1)$.

---

### 4. R function `rsin(n)`

Here’s an R function that uses inverse transform sampling:

```r
rsin <- function(n) {
  u <- runif(n)
  x <- numeric(n)
  
  for (i in 1:n) {
    if (u[i] < 0.5) {
      x[i] <- acos(4 * u[i] - 1) * (-1)
    } else {
      x[i] <- acos(2 - 4 * u[i])
    }
  }
  
  return(x)
}
