**Mean Squared Error (MSE)**
Suppose $X_1, \ldots, X_n$ is a random sample from $U(0, \theta)$.
1. Show:
$$
\mathbb{E}[X_{(n)}] = \frac{n}{n+1} \theta, \quad \mathrm{Var}(X_{(n)}) = \frac{n\theta^2}{(n+1)^2(n+2)}
$$

2. Find multiples of $X_n$ and $X_{(n)}$ which are unbiased for $\theta$ and compute their MSE.

---
## 1) Show: $\mathbb{E}[X_{(n)}] = \frac{n}{n+1} \theta, \quad \mathrm{Var}(X_{(n)}) = \frac{n\theta^2}{(n+1)^2(n+2)}$

---
**Samplind Distripution of the Maximus (PPP-Slides)**
The cdf of $X_{(n)} = \max(X_1, \dots, X_n)$ is
$$
F_{X_{(n)}}(x) = \mathbb{P}(\max(X_1, \dots, X_n) \le x) \\
= \mathbb{P}(\text{all } X_i \le x) \\
= (\mathbb{P}(X_1 \le x))^n \\
= (F_{X_1}(x))^n
$$

with pdf
$$
f_{X_{(n)}}(x) = \frac{dF_{X_{(n)}}(x)}{dx} = n(F_{X_1}(x))^{n-1} f_{X_1}(x)
$$

---
$$
\begin{split}
\mathbb{E}(X_{(n)}) &= \int_0^\theta x \cdot n(F_{X_1}(x))^{n-1} f_{X_1}(x)dx\\
&= n \int_0^\theta x \left(\frac{x}{\theta}\right)^{n-1} \cdot \frac{1}{\theta} dx\\
&= \frac{n}{\theta^n} \int_0^\theta x^n \, dx = \frac{n}{\theta^n} \cdot \frac{x^{n+1}}{n+1} \Bigg|_0^\theta = \frac{\theta n}{n+1}
\end{split}
$$

$$
\begin{split}
\mathbb{E}(X_{(n)}^2) = \int_0^\theta x^2 \cdot n(F_{X_1}(x))^{n-1} f_{X_1}(x) \, dx\\
= \dots = \frac{n}{\theta^n} \cdot \frac{x^{n+2}}{n+2} \Bigg|_0^\theta = \frac{n \theta^2}{n+2}
\end{split}
$$


$$
\begin{split}
\operatorname{Var}(X_{(n)}) &= \mathbb{E}(X_{(n)}^2) - \left( \mathbb{E}(X_{(n)}) \right)^2\\
&= \frac{n \theta^2}{n+2} - \left( \frac{\theta n}{n+1} \right)^2\\
&= \theta^2 \cdot \frac{n(n+1)^2 - n^2(n+2)}{(n+2)(n+1)^2}\\
&= \frac{n \theta^2 \left( n^2 + 2n + 1 - n^2 - 2n \right)}{(n+2)(n+1)^2}\\
&= \frac{n \theta^2}{(n+2)(n+1)^2}
\end{split} 
$$
---

## 2) Find multiples of $X_n$ and $X_{(n)}$ which are unbiased for $\theta$ and compute their MSE.

$$
\begin{split}
\mathbb{E}(X_{(n)}) = \frac{n}{n+1} \theta \iff \mathbb{E}\left(\frac{n+1}{n} X_{(n)}\right) = \theta\\
\mathbb{E}(\bar{X}_n) = \mathbb{E}(X_1) = \frac{0 + \theta}{2} = \frac{\theta}{2} \iff \mathbb{E}(2\bar{X}_n) = \theta
\end{split}
$$
### MSE:

$$
\mathbb{E}\left( \left( \frac{n+1}{n} X_{(n)} - \theta \right)^2 \right) = \operatorname{Var}\left( \frac{n+1}{n} X_{(n)} \right)
= \left( \frac{n+1}{n} \right)^2 \operatorname{Var}(X_{(n)})
$$

Using previously derived:
$$
\operatorname{Var}(X_{(n)}) = \frac{n \theta^2}{(n+2)(n+1)^2}
$$

So:
$$
\text{MSE} = \left( \frac{n+1}{n} \right)^2 \cdot \frac{n \theta^2}{(n+2)(n+1)^2} = \frac{\theta^2}{n(n+2)}
$$

$$
\mathbb{E}((2\bar{X}_n - \theta)^2) = \operatorname{Var}(2\bar{X}_n) = 4 \operatorname{Var}(\bar{X}_n)
$$

Since $X_i \overset{\text{iid}}{\sim} U(0,\theta)$:
$$
\operatorname{Var}(\bar{X}_n) = \frac{1}{n^2} \sum_{i=1}^n \operatorname{Var}(X_i) = \frac{1}{n^2} \cdot n \cdot \frac{\theta^2}{12} = \frac{\theta^2}{12n}
$$

So:
$$
\text{MSE} = 4 \cdot \frac{\theta^2}{12n} = \frac{\theta^2}{3n}
$$
