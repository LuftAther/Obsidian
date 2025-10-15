## Cumulant generating function

Let the moment generating function $M_X$ of a given random variable $X$ be well defined in some neighborhood of zero. The cumulant generating function of $X$ is

$$
K_X(s) = \log M_X(s),
$$

and can be represented by the Taylor expansion

$$
K_X(s) = \sum_{n=0}^{\infty} \kappa_n \frac{s^n}{n!},
$$

where $\kappa_n$ is the *n*th cumulant of $X$ for $n \geq 1$.

1. Compute the cumulant generating function of $X \sim \mathcal{N}(\mu, \sigma^2)$, i.e. find the cumulants $\kappa_n, \, n \geq 1$.
2. To which moments do the first three cumulants relate? Show that this holds in general (for the first three) assuming the moment generating function exists.

---

##  1. Compute the cumulant generating function of $X \sim \mathcal{N}(\mu, \sigma^2)$, i.e. find the cumulants $\kappa_n, \, n \geq 1$.

Let $X \sim \mathcal{N}(\mu, \sigma^2)$. We want to compute the cumulant generating function: $K_X(s) = \log M_X(s)$
By using the identity: $M_{aX + b}(s) = e^{bs} \cdot M_X(as)$
We can rewrite the therm to : $K_X(s) = \log(M_X(s)) = \log\left(e^{\mu s} \cdot M_{N(0,1)}(\sigma s)\right)$

 We start from the definition of the MGF  :

$$
M_X(s) = \mathbb{E}[e^{sX}] = \int_{-\infty}^{\infty} e^{sx} \cdot \frac{1}{\sqrt{2\pi} \sigma} \cdot \exp\left(-\frac{(x - \mu)^2}{2\sigma^2} \right) dx
$$


Now we can pull out $e^{\mu s}$ and rewrite the exponent:

$$
\log \left( e^{\mu s} \cdot \int_{-\infty}^{\infty} \frac{1}{\sqrt{2\pi}} \cdot \exp\left(-\frac{1}{2}(x^2 - 2\sigma s x)\right) dx \right)
$$

We complete the square in $x$:  $x^2 - 2\sigma s x = (x - \sigma s)^2 - \sigma^2 s^2$

So the integral becomes:

$$
\int \exp\left(-\frac{1}{2}(x - \sigma s)^2\right) dx \cdot \exp\left( \frac{\sigma^2 s^2}{2} \right)
$$

Now we get:

$$
K_X(s) = \log\left(e^{\mu s} \cdot \exp\left( \frac{\sigma^2 s^2}{2} \right) \cdot \underbrace{\int \frac{1}{\sqrt{2\pi}} \exp\left( -\frac{(x - \sigma s)^2}{2} \right) dx}_{\text{ Normal density function } \Rightarrow 1} \right)
$$

We finally get:

$$
K_X(s) = \log \left( \exp\left( \mu s + \frac{\sigma^2 s^2}{2} \right) \right) = \mu s + \frac{\sigma^2 s^2}{2}
$$

Comparing with the Taylor expansion:

$$
K_X(s) = \sum_{n=1}^{\infty} \kappa_n \frac{s^n}{n!}
$$

We identify:
- $\kappa_0 = 0$
- $\kappa_1 = \mu$
- $\kappa_2 = \sigma^2$
- $\kappa_n = 0$ for all $n \geq 3$

This matches the known fact that the **normal distribution has only the first two non-zero cumulants** (mean and variance), and all higher cumulants vanish.

### 2. To which moments do the first three cumulants relate? Show that this holds in general (for the first three) assuming the moment generating function exists.


We want to show how the **first and second cumulants** relate to the **first and second raw moments** $m_1 = \mathbb{E}[X]$ and $m_2 = \mathbb{E}[X^2]$.

###  First Cumulant: $\kappa_1$

We compute:

$$
\kappa_1 = K_X'(0) = \left. \frac{d}{ds} \log M_X(s) \right|_{s=0}
$$

Using the chain rule:

$$
\kappa_1 = \left. \frac{1}{M_X(s)} \cdot M_X'(s) \right|_{s=0} = \frac{M_X'(0)}{M_X(0)}
$$

Since:

- $M_X(0) = \mathbb{E}[e^{0}] = 1$
- $M_X'(0) = \mathbb{E}[X] = m_1$

We get:

$$
\kappa_1 = m_1 = \mathbb{E}[X]
$$

**$\Rightarrow$The first cumulant is the mean.**

###  Second Cumulant: $\kappa_2$

We compute:

$$
\kappa_2 = K_X''(0) = \left. \frac{d^2}{ds^2} \log M_X(s) \right|_{s=0}
$$

Using the quotient rule:

$$
K_X''(s) = \frac{M_X''(s) \cdot M_X(s) - (M_X'(s))^2}{M_X(s)^2}
$$

Evaluating at $s = 0$:

- $M_X(0) = 1$
- $M_X'(0) = m_1$
- $M_X''(0) = \mathbb{E}[X^2] = m_2$

Then:

$$
\kappa_2 = M_X''(0) - (M_X'(0))^2 = m_2 - m_1^2
$$

**The second cumulant is the variance**:

$$
\kappa_2 = \operatorname{Var}(X)
$$

####  Conclusion

- $\kappa_1 = \mathbb{E}[X] = m_1$ (mean)
- $\kappa_2 = \mathbb{E}[X^2] - (\mathbb{E}[X])^2 = \operatorname{Var}(X)$

This holds **for any distribution** as long as the moment generating function exists in a neighborhood of 0.
