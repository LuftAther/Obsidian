## The Pareto Mean

Let $X_1, \ldots, X_n$ be a random sample from a population with Pareto$(1, \theta)$ distribution and let
$$
\bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i \quad \text{and} \quad Y = \frac{n}{\sum_{i=1}^n \log X_i}.
$$
The Pareto$(a, \theta)$ distribution for $a > 0$ and $\theta > 1$ is a continuous distribution over the interval $[a, \infty)$ given by the pdf:
$$
f(x) =
\begin{cases}
\theta a^\theta x^{-\theta - 1}, & x \geq a \\
0, & x < a
\end{cases}
$$
This distribution is commonly used in economics as a model for the distribution of income, where $a$ represents the minimum possible income.

---
1. For $\theta > 2$, apply the Central Limit Theorem to obtain the limiting distribution:
$$
\sqrt{n} \left( \frac{\bar{X}_n - \frac{\theta}{\theta - 1}}{\frac{\theta}{\theta - 1}} \right) \xrightarrow{d} \mathcal{N}(0, \operatorname{Var}(X_i)).
$$
2. Show that
$$
\sqrt{n}(Y - \theta) \xrightarrow{d} \mathcal{N}(0, \theta^2) \quad \text{as } n \to \infty.
$$
3. Use the Delta method to show

$$
\sqrt{n} \left( \frac{Y}{Y - 1} - \frac{\theta}{\theta - 1} \right)
\xrightarrow{d}
\mathcal{N} \left( 0, \frac{\theta^2}{(\theta - 1)^4} \right).
$$
---
---
#### 1 For $\theta > 2$, apply the Central Limit Theorem to obtain the limiting distribution:
$\sqrt{n} \left( \frac{\bar{X}_n - \frac{\theta}{\theta - 1}}{\frac{\theta}{\theta - 1}} \right) \xrightarrow{d} \mathcal{N}(0, \operatorname{Var}(X_i))$.

 $$
 \mathbb{E}(X_i) := \int_0^\infty \theta a^{\theta}x^{-\theta} dx=\left[ \frac{\theta}{1-\theta} a^{\theta}x^{1-\theta}\right]_a^\infty \underbrace{=}_{\theta>2} \frac{a \theta}{\theta - 1}
$$
$\Rightarrow (\text{CLT}) \quad \sqrt{n} \left( \bar{X}_n - \frac{a \theta}{\theta - 1} \right) \xrightarrow{d} \mathcal{N}\left(0, \text{Var}(X_i)\right)$

---

#### 2 Show that $\sqrt{n}(Y - \theta) \xrightarrow{d} \mathcal{N}(0, \theta^2) \quad \text{as } n \to \infty$.

Let $L = \log X_i$
$$
\begin{split}
f_L = f_X(e^x) e^x&= \theta a^{\theta}e^{-x\theta-x} e^x \mathbb{1}_{\{x \leq \log a\}}\\
&= \theta a^{\theta} e^{-x \theta} \mathbb{1}_{\{x \geq a\}}\\
\end{split}
$$
$$
\begin{split}
\mathbb{E}(L) &= \int_{\log a}^\infty x \theta a^\theta e^{-x\theta} dx = \theta a^{\theta}-\left(\left[ \frac{1}{\theta} x e^{-x \theta} \right]_{\log a}^{\infty} + \frac{1}{\theta} \int_{\log a}^\infty e^{-x\theta} dx\right)\\
&= \log a + \theta a^{\theta} \frac{1}{\theta²}a^{-\theta} = \log a + \frac{1}{\theta} = \frac{\theta \log a +1}{\theta}
\end{split}
$$
$$
\begin{split}
\mathbb{E}(L^2)& = \int_{\log a}^\infty x^2 \theta a^\theta e^{-x\theta} dx = \theta e^{\theta}\left( -\frac{1}{\theta} \left[x^2 e^{-x\theta}\right]_{\log a}^{\infty} \right) + \frac{2}{\theta} \underbrace{\theta a^{\theta} \int_{\log a}^{\infty} x e^{-x \theta}dx}_{= \mathbb{E}(L)}\\
&= \frac{(\theta \log a)^2 + 2\theta \log a + 2}{\theta^2} = \frac{(\theta \log a + 1)^2 + 1}{\theta^2}
\end{split}
$$

$$
\begin{split}
\text{Var}(L) = \frac{(\theta \log a + 1)^2 + 1}{\theta^2} - \left( \frac{\theta \log a + 1}{\theta} \right)^2 = \frac{1}{\theta^2}\\
\Rightarrow (\text{CLT}) \quad \sqrt{n} \left( \frac{1}{Y_n} - \frac{\theta \log a + 1}{\theta} \right) \xrightarrow{d} \mathcal{N}\left(0, \frac{1}{\theta^2} \right)
\end{split}
$$

$$
\begin{split}
g(x) := \frac{1}{x} \Rightarrow g'(x) := - \frac{1}{x^2}, \quad (g'(\frac{\theta \log a + 1}{\theta}))^2 = \frac{\theta^4}{(1+\theta \log a)^4}\\
\Rightarrow \text{(delta method)} \quad \sqrt{n} \left( Y_n - \frac{\theta}{1+ \theta \log a}\right) \xrightarrow{d} \mathcal{N}\left(0, \frac{\theta^2}{(1+ \theta \log a)^4}\right)
\end{split}
$$
---

#### 3 Use the Delta method to show $\sqrt{n} \left( \frac{Y}{Y - 1} - \frac{\theta}{\theta - 1} \right)\xrightarrow{d}\mathcal{N} \left( 0, \frac{\theta^2}{(\theta - 1)^4} \right)$

 Let $g(x) := \frac{x}{x - 1} \Rightarrow g'(x) := -\frac{1}{(x - 1)^2}$

- $g\left( \frac{\theta}{\theta \log a + 1} \right) = \frac{\frac{\theta}{\theta \log a + 1}}{\frac{\theta}{\theta \log a + 1} - 1} = \frac{\theta}{\theta - (\theta \log a - 1)} = \frac{\theta}{\theta (1 - \log a 1) - 1}$

- $\left( g'\left( \frac{\theta}{\theta \log a + 1} \right) \right)^2  = \frac{1}{\left( \frac{\theta}{\theta \log a +1} -1 \right)^4} = \frac{1 (\theta \log a + 1)^4}{(\theta - (\theta \log a + 1)1)^4}$

$$
\Rightarrow (\text{delta}) \quad 
\sqrt{n} \left( \frac{Y_n}{Y_n - 1} - \frac{\theta}{\theta(1 - \log a) - 1} \right) 
\xrightarrow{d} 
\mathcal{N} \left( 0, \frac{\theta^2}{(\theta(1 - \log a) - 1)^4} \right)
$$
