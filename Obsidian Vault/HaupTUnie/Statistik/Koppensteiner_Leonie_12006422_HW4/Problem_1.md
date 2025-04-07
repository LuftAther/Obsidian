
###  Sum of Exponentials

Let $X_i \sim \text{Exp}(\lambda)$, $i = 1, 2, \ldots$ be independent and identically distributed (iid) exponential random variables with rate $\lambda > 0$.
1. Derive the distribution of 
   $$
   Y_k = \sum_{i=1}^{k} X_i
   $$

   for $k = 1, 2, \ldots$, by computing its pdf $f_{Y_k}$.
2. Compute the moment generating function (mgf) of $X_1$ as well as $Y_k$ for $k = 1, 2, \ldots$.
3. Use the moment generating functions to compute the first two moments and the variance of both $X_1$ and $Y_k$ for $k = 1, 2, \ldots$

---
---
#### 1. Derive the distribution of 

$$
Y_k = \sum_{i=1}^{k} X_i
$$

for $k = 1, 2, \ldots$, by computing its pdf $f_{Y_k}$.

---

PDF of an Exponential Distribution
Since $X_i \sim \text{Exp}(\lambda)$, the probability density function (pdf) is:

$$
f(x) = \lambda e^{-\lambda x}, \quad x \geq 0
$$
Using the theorem for the sum of independent continuous random variables with densities $f_X$ and $f_Y$:
![[Pasted image 20250405125100.png|400]]
$$
f_{X+Y}(z) = \int_{-\infty}^{\infty} f_X(x) f_Y(z - x) \, dx
$$
we can write for k = 2: $Y_{2} := X_{1}+X_{2} \quad x \geq 0 \quad y-x \geq 0 \Leftrightarrow y \geq x$

$$
\begin{split}
f_{Y_2}(y) &= \int_{0}^{y} f_{x_{1}}(x) f_{x_{2}}(y-x)\, dx \\
f_{Y_2}(y) &= \int_{0}^{y} \lambda e^{-\lambda x} \lambda e^{-\lambda(y - x)} \, dx\\
&= \lambda^2 e^{-\lambda y} \int_{0}^{y} dx = \lambda^2 ye^{-\lambda y} \\
&= \lambda² e^{-\lambda y}y\\
&= \text{ Gamma}(2, \lambda) \quad \Gamma(2) = 1
\end{split}
$$
![[Pasted image 20250405131950.png|400]]

$$
\begin{split}
f_{Y_3}(y) &= \int_{0}^{y} \lambda^2 x e^{-\lambda x} \lambda e^{-\lambda(y - x)} \, dx\\
&= \lambda^3 e^{-\lambda y} \int_{0}^{y} x \, dx \\
\int_{0}^{y} x \, dx = \frac{x^2}{2} \bigg|_{0}^{y} = \frac{y^2}{2}\\
 &= \lambda^3 e^{-\lambda y} \frac{y^2}{2} ( = \Gamma(3,\lambda))
\end{split}
$$


Since:$\Gamma(3) = 2! = 2$
Therefore: $f_{Y_3}(y) = \lambda^3 e^{-\lambda y} \frac{y^2}{2}$

By repeating this process for $Y_k$ (summing $k$ independent exponential variables), we find:

$$
f_{Y_k}(y) = \frac{\lambda^k y^{k-1} e^{-\lambda y}}{(k-1)!}, \quad y > 0
$$
This is recognized as the **Gamma Distribution** with shape parameter $k$ and rate parameter $\lambda$:
$$
Y_k \sim \text{Gamma}(k, \lambda)
$$

---

#### 2. Compute the moment generating function (mgf) of $X_1$ as well as $Y_k$ for $k = 1, 2, \ldots$.
---
![[Pasted image 20250405133223.png]]

- MGF of $X_1$

Since $X_1 \sim \text{Exp}(\lambda)$, its pdf is: $f_{X_1}(x) = \lambda e^{-\lambda x}, \quad x > 0$

So, the moment generating function is: $M_{X_1}(t) = \int_{0}^{\infty} e^{tx} \lambda e^{-\lambda x} \, dx$

$$
= \lambda \int_{0}^{\infty} e^{-(\lambda - t)x} \, dx
$$

Evaluating the integral:

$$
M_{X_1}(t) = \lambda \left( \frac{1}{\lambda - t} \right) \quad \text{for } t < \lambda
$$
$= \frac{\lambda}{\lambda - t}$

---

- MGF of $Y_k$

Since $Y_k = X_1 + X_2 + \ldots + X_k$ and the $X_i$ are independent:
$M_{Y_k}(t) = \mathbb{E}(e^{t Y_k}) = \mathbb{E}(e^{t(X_1 + X_2 + \ldots + X_k)})$

By the independence of the $X_i$, the MGF factors into a product:
$$M_{Y_k}(t) = \mathbb{E}(e^{t X_1}) = \mathbb{E}(e^{t(X_{1} + X_2 +\ldots +X_{k})} = \mathbb{E}(e^{t X_1}) \cdot \mathbb{E}(e^{tx_{2}}) \cdot \ldots \cdot \mathbb{E}(e^{tx_{k}}) = (\frac{\lambda}{\lambda - t})^k, \quad \text{for } t < \lambda$$
So:
- You correctly calculated the MGF of a single exponential random variable $X_1$. 
- You also correctly applied the property of independence to derive the MGF of $Y_k$. 
- Your conclusion that $M_{Y_k}(t) = \left( \frac{\lambda}{\lambda - t} \right)^k$ is accurate.

---
#### 3. Use the moment generating functions to compute the first two moments and the variance of both $X_1$ and $Y_k$ for $k = 1, 2, \ldots$
---
Using the MGF of $X_1$:

$$
M_{X_1}(t) = \frac{\lambda}{\lambda - t}
$$

The $n$-th moment is obtained by differentiating the MGF $n$ times and then evaluating at $t = 0$.

- **First Moment (Mean) of $X_{1}$:**
$$
\begin{split}
\mathbb{E}[X_1] = M_{X_1}'(0) = \frac{d}{dt} \left( \frac{\lambda}{\lambda - t} \right) \bigg|_{t = 0} \\
= \frac{\lambda}{(\lambda - t)^2} \bigg|_{t = 0} = \frac{1}{\lambda}
\end{split}
$$
- **Second Moment:**

$$
\mathbb{E}[X_1^2] = M_{X_1}''(0)
$$

Taking the derivative again:
$$
\begin{split}
\frac{d}{dt} \left( \frac{\lambda}{(\lambda - t)^2} \right) &= \frac{2\lambda}{(\lambda - t)^3}\\
\text{ evaluating at t = 0}\\
\mathbb{E}[X_1^2] &= \frac{2}{\lambda^2}
\end{split}
$$

- **Variance of $X_1$:**
$$
\begin{split}
\text{Var}(X_1) &= \mathbb{E}[X_1^2] - \left( \mathbb{E}[X_1] \right)^2\\
&= \frac{2}{\lambda^2} - \left( \frac{1}{\lambda} \right)^2\\
&= \frac{2 - 1}{\lambda^2} = \frac{1}{\lambda^2}
\end{split}
$$



Using the MGF of $Y_k$:
- **First Moment (Mean) of $Y_{k}$:**
$$
\begin{split}
\mathbb{E}[Y_k] = M_{Y_k}'(0) = \frac{d}{dt} \left( \frac{\lambda}{\lambda - t} \right)^k \bigg|_{t = 0}\\
= k \left( \frac{\lambda}{\lambda - t} \right)^{k-1} \frac{\lambda}{(\lambda - t)^2} \bigg|_{t = 0}\\
= \frac{k}{\lambda}
\end{split}
$$

- **Second Moment:**
$$
\begin{split}
\mathbb{E}[Y_k^2] &= M_{Y_k}''(0) \\
\text{Using the chain rule for the derivative:}\\
M_{Y_k}''(t) &= \frac{k \lambda}{(\lambda - t)} \left( \frac{\lambda}{\lambda - t} \right)^{k-1} \left( \frac{k \lambda}{(\lambda - t)^2} + \frac{(k-1) \lambda^2}{(\lambda - t)^3} \right)\\
\text{evaluating at} t = 0\\
\mathbb{E}[Y_k^2]&= \frac{k(k+1)}{\lambda^2}

\end{split}

$$



- **Variance of $Y_k$:**

$$\begin{split}
\text{Var}(Y_k) &= \mathbb{E}[Y_k^2] - \left( \mathbb{E}[Y_k] \right)^2\\

&= \frac{k(k+1)}{\lambda^2} - \left( \frac{k}{\lambda} \right)^2\\

&= \frac{k}{\lambda^2}
\end{split}$$
![[Pasted image 20250405141303.png|400]]