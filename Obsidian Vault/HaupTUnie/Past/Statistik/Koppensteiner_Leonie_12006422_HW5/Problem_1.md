## Problem 1: Transforms and Moments

Let $X \sim \mathcal{N}(0,1)$ be standard normal distributed.

1. Compute $\mathbb{E}[X^2]$ directly, then use the pdf of $Y = X^2$ and compute $\mathbb{E}[Y]$.
2. Find the pdf of $|X|$ and compute $\mathbb{E}[|X|]$.

---
#### 1.a. Direct computation of $\mathbb{E}[X^2]$

Since $X$ is standard normal:
- Mean: $\mathbb{E}[X] = 0$
- Variance: $\text{Var}(X) = 1$

We know:
$$
\mathbb{E}[X^2] = \text{Var}(X) + (\mathbb{E}[X])^2 = 1 + 0 = 1
$$
$\mathbb{E}(X²) = \int_{\mathbb{R}} x^2 f_{X}(x)dx = \frac{1}{\sqrt{ 2 \pi }} \int_{\mathbb{R}} \underset{\text{ ableiten} }x \underbrace{x \exp(\frac{-x^2}{2})}_{\text{ Itegrieren }}dx$
> $\int x e^{\frac{-x^2}{2}}dx = -e^{\frac{-x^2}{2}}+c$

$$
= \frac{1}{\sqrt{2\pi}} \left( -x e^{-\frac{x^2}{2}} \bigg|_{-\infty}^{\infty} + \int_{\mathbb{R}} e^{-\frac{x^2}{2}} \, dx \right)
$$

$$
= \left. u = \frac{x}{\sqrt{2}} \quad \frac{du}{dx} = \frac{1}{\sqrt{2}} \Rightarrow dx = \sqrt{2} \, du \right| 
= \frac{1}{\sqrt{\pi}} \int_{\mathbb{R}} e^{-u^2} \, du
$$

$$
= \frac{2}{\sqrt{\pi}} \int_0^{\infty} e^{-u^2} \, du = \text{erf}(\infty) = 1
$$


#### 1.b. Compute $\mathbb{E}[Y]$ where $Y = X^2$

Let $Y = X^2$. Then $Y \sim \chi^2(1)$, which is a chi-squared distribution with 1 degree of freedom.
-
Wir setzen $Y = X^2 \sim \chi^2(1)$.

The chi-squared distribution with 1 degree of freedom is equivalent to a Gamma distribution with parameters:
![[HaupTUnie/Past/Statistik/Koppensteiner_Leonie_12006422_HW1/chi.png|400]]
$$
\chi^2(1) \overset{d}{=} \text{Gamma}(\alpha = \tfrac{1}{2}, \, \beta = 2)
$$
where $\beta$ is the der **Skale parameter** ist.

---
We know from the Lecture:

> **Gamma: Expectation**

For $X \sim \text{Gamma}(\alpha, \beta)$, we have:
$$
\mathbb{E}(X) = \int_{-\infty}^{+\infty} x f_X(x) \, dx 
= \frac{1}{\Gamma(\alpha) \, \beta^\alpha} \int_0^{+\infty} x^\alpha e^{-x / \beta} \, dx
$$

**Substitution:** $x = \beta u \Rightarrow dx = \beta \, du$
$$
= \frac{\beta}{\Gamma(\alpha)} \int_0^{+\infty} u^\alpha e^{-u} \, du
$$

Integration by parts:
$$
= \frac{\beta}{\Gamma(\alpha)} \left[ -u^\alpha e^{-u} \bigg|_0^{+\infty} + \alpha \int_0^{+\infty} u^{\alpha - 1} e^{-u} \, du \right]
$$

$$
= \frac{\beta}{\Gamma(\alpha)} \cdot \alpha \Gamma(\alpha)
= \alpha \beta
$$
Therefore:
$$
\mathbb{E}(X^2) = \mathbb{E}(Y) = \alpha \beta = \tfrac{1}{2} \cdot 2 = 1
$$
---
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