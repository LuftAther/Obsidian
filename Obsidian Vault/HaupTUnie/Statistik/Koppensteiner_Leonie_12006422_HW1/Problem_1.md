## Problem 1: Transforms and Moments

Let $X \sim \mathcal{N}(0, 1)$ be standard normal distributed.

---

### 1. Compute $\mathbb{E}[X^2]$ directly, then use the PDF of $Y = X^2$ and compute $\mathbb{E}[Y]$

#### a. Direct computation of $\mathbb{E}[X^2]$

Since $X$ is standard normal:
- Mean: $\mathbb{E}[X] = 0$
- Variance: $\text{Var}(X) = 1$

We know:
$$
\mathbb{E}[X^2] = \text{Var}(X) + (\mathbb{E}[X])^2 = 1 + 0 = 1
$$

#### b. Compute $\mathbb{E}[Y]$ where $Y = X^2$

Let $Y = X^2$. Then $Y \sim \chi^2(1)$, which is a chi-squared distribution with 1 degree of freedom.

The PDF of $Y$ is:
$$
f_Y(y) = \frac{1}{\sqrt{2\pi y}} e^{-y/2}, \quad y > 0
$$

The expected value is:
$$
\mathbb{E}[Y] = \int_0^\infty y f_Y(y) \, dy = 1
$$

This matches the previous result.

---

### 2. Find the PDF of $|X|$ and compute $\mathbb{E}[|X|]$

#### a. PDF of $|X|$

The standard normal distribution is symmetric around 0, so the absolute value $|X|$ follows the folded normal distribution:
$$
f_{|X|}(x) = 2 f_X(x) = \frac{2}{\sqrt{2\pi}} e^{-x^2/2}, \quad x \ge 0
$$

#### b. Compute $\mathbb{E}[|X|]$

We compute:
$$
\mathbb{E}[|X|] = \int_0^\infty x f_{|X|}(x) \, dx = \int_0^\infty x \cdot \frac{2}{\sqrt{2\pi}} e^{-x^2/2} dx
$$

Substitution: $u = \frac{x^2}{2} \Rightarrow du = x dx$

Then:
$$
\mathbb{E}[|X|] = \frac{2}{\sqrt{2\pi}} \int_0^\infty e^{-u} du = \frac{2}{\sqrt{2\pi}} = \sqrt{\frac{2}{\pi}}
$$

Therefore:
$$
\mathbb{E}[|X|] = \sqrt{\frac{2}{\pi}} \approx 0.7979
$$