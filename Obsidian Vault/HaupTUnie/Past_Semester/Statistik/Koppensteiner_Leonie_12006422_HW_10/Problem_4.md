### Poisson response exponential family

Suppose that $X_i$ are independent $\text{Poisson}(\lambda_i)$, with $\lambda_i = \alpha + \beta t_i$, where $t_i$ are observed constants for $i = 1, \ldots, n$, and $\alpha, \beta$ are unknown parameters. 

Show that the joint distribution for $X_1, \ldots, X_n$ belongs to the exponential family and identify the natural parameter and statistics.

---
---

![[Pasted image 20250531070712.png]]
### Poisson PMF and Exponential Family Representation

Let the Poisson pmf be defined as:

$$
f(x) = \frac{\lambda^x}{x!} e^{-\lambda}, \quad x \in \mathbb{N}_0, \; \lambda > 0
$$

Let $X := (X_1, \dots, X_n)$ be i.i.d. $\text{Poisson}(\lambda_i)$ (possibly non-identical $\lambda_i$).  
Then the joint pmf is:

$$
f_X(x) = \prod_{i=1}^n f_{X_i}(x_i)
= \prod_{i=1}^n \frac{\lambda_i^{x_i}}{x_i!} e^{-\lambda_i}
$$

Break it into factors:

$$
= \left( \prod_{i=1}^n e^{-\lambda_i} \right)
  \left( \prod_{i=1}^n \frac{1}{x_i!} \right)
  \left( \prod_{i=1}^n \exp\left( \log(\lambda_i^{x_i}) \right) \right)
$$

Simplifying the exponent:

$$
= \left( \prod_{i=1}^n e^{-\lambda_i} \right)
  \left( \prod_{i=1}^n \frac{1}{x_i!} \right)
  \exp\left( \sum_{i=1}^n x_i \log(\lambda_i) \right)
$$

We can now write it in the exponential family form:

$$
f_X(x) = c(\lambda) \cdot h(x) \cdot \exp\left( \sum_{i=1}^n x_i \log(\lambda_i) \right)
$$

where:
- $c(\lambda) = \prod_{i=1}^n e^{-\lambda_i}$
- $h(x) = \prod_{i=1}^n \frac{1}{x_i!}$
- the natural parameter is $\eta_i = \log(\lambda_i)$
- the sufficient statistic is $T_i(x) = x_i$

 $c > 0$ and $h > 0$ — exponential family form is valid.
 
![[Pasted image 20250531070543.png]]![[Pasted image 20250531070612.png]

### Natural Parameter and Natural Statistic (Poisson Exponential Family)

We consider a Poisson model:

$$
X_i \sim \text{Poisson}(\lambda_i)
$$

**Natural Parameter:**

From the canonical exponential family form:

$$
\psi_i = \log(\lambda_i)
$$

So the **natural parameter vector** is:

$$
\Psi =
\begin{pmatrix}
\log(\lambda_1) \\
\vdots \\
\log(\lambda_n)
\end{pmatrix}
$$

---

#### Natural Statistic:

Since the identity function $T(x) = x$ maps $x$ directly, the **natural statistic** is:

$$
Y = \text{id}(x) = x
$$

---

This aligns with the general exponential family representation:

$$
f(x \mid \psi) = h(x) \exp\left( \langle Y, \psi \rangle - b(\psi) \right)
$$

Source: [StatisticsHowTo – Canonical Statistics and Natural Parameters](https://www.statisticshowto.com/canonical-statistic-natural/)
