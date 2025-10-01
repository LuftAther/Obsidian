## Stirling’s Formula

Stirling’s Formula is an approximate formula for the factorial:
$$
n! = n \cdot (n - 1) \cdot \ldots \cdot 2 \cdot 1
$$
given by
$$
n! \approx \sqrt{2 \pi n} \left( \frac{n}{e} \right)^n
$$
where $e = \exp(1)$. Derive Stirling’s Formula in the following two steps:

---

  1. Argue that for $X_i \overset{\text{iid}}{\sim} \text{Exp}(1)$, one gets
$$
\mathbb{P} \left( \sqrt{n}(\bar{X}_n - 1) \leq x \right)
\xrightarrow{n \to \infty}
\Phi(x)
$$ 
where $\Phi$ is the cumulative distribution function (cdf) of the standard normal distribution.

 2. Show that differentiation of both sides in step 1 yields Stirling’s formula if evaluated at $x = 0$,  and give an argument why this is a valid approach.
---
---

#### 1 Argue that for $X_i \overset{\text{iid}}{\sim} \text{Exp}(1)$, one gets $\mathbb{P} \left( \sqrt{n}(\bar{X}_n - 1) \leq x \right)\xrightarrow{n \to \infty}\Phi(x)$ where $\Phi$ is the cumulative distribution function (cdf) of the standard normal distribution.

Let  
$E(X_1) = \frac{1}{\lambda} = 1$,  
$\operatorname{Var}(X_1) = \frac{1}{\lambda^2} = 1$,  
$X_1, \dots$ i.i.d.

From the **Central Limit Theorem (CLT)**:

$$
\sqrt{n}(\bar{X}_n - 1) \xrightarrow{d} \mathcal{N}(0,1)
$$

Therefore, by definition of convergence in distribution:

$$
P\left(\sqrt{n}(\bar{X}_n - 1) \le x\right) \to \Phi(x)
$$
---
### 2 Show that differentiation of both sides in step 1 yields Stirling’s formula if evaluated at $x = 0$,  and give an argument why this is a valid approach.

Let  $Y_n := \sqrt{n} \left( \bar{X}_n - 1 \right)$

From 1., we know that  $F_{Y_n} \xrightarrow{pw} F_{\mathcal{N}(0,1)}$

\* We also assume  $f_{Y_n} \xrightarrow{pw} f_{\mathcal{N}(0,1)}$
Let $X \sim \text{Gamma}(\alpha, \lambda)$, $\beta > 0$.
Then:  
$$
\begin{split}
f_{\beta X + \delta}(x) &= f_X\left(\frac{x - \delta}{\beta}\right) \cdot \frac{1}{\beta}\\
&= \frac{\lambda^\alpha}{\Gamma(\alpha)} \left( \frac{x - \delta}{\beta} \right)^{\alpha - 1} 
\exp\left( -\lambda \left( \frac{x - \delta}{\beta} \right) \right)\cdot \frac{1}{\beta}\\
\end{split}
$$
Recall that

$$
\underbrace{\text{Exp}(\lambda) + \dots + \text{Exp}(\lambda)}_{n \text{ times, i.i.d.}} = \text{Gamma}(n, \lambda)
$$
By choosing  
$\beta = \frac{1}{\sqrt{n}}, \quad \delta = \sqrt{n}, \quad \alpha = n, \quad \lambda = 1$,  
we obtain:

$$
f_{Y_n}(0) = f_{\frac{1}{\sqrt{n}} \cdot \text{Gamma}(n,1) - \sqrt{n}}(0)
$$

Using the transformation formula:

$$
= \frac{1}{\Gamma(n)} \left( \frac{0 + \sqrt{n}}{\frac{1}{\sqrt{n}}} \right)^{n-1} 
\exp\left(-1 \cdot \left( \frac{0 + \sqrt{n}}{\frac{1}{\sqrt{n}}} \right) \right) \cdot \sqrt{n}
$$

$$
= \frac{1}{(n - 1)!} \cdot n^{n - 1} \cdot e^{-n} \cdot \sqrt{n}
$$
We are approximating the density:
$$
f_{Y_n}(0) \approx f_{\mathcal{N}(0,1)}(0)
$$
$$
\begin{split}
&\Leftrightarrow \frac{1}{(n+1)!} \cdot n^{n-1} \cdot e^{-n} \cdot \sqrt{n} \approx \frac{1}{\sqrt{2\pi}} \cdot 1\\
&\Leftrightarrow n^{n-1} e^{-n} \sqrt{2\pi n} \approx (n+1)!  \quad |\cdot n \text{ Stirling's approximation}\\
&\Leftrightarrow \sqrt{2\pi n} \left( \frac{n}{e} \right)^n \approx n!
\end{split}
$$
