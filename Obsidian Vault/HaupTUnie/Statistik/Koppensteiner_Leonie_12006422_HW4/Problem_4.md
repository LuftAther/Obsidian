### Cauchy distribution

Let $X$ be a standard Cauchy random variable with density
$$
f_X(x) = \frac{1}{\pi (1 + x^2)}
$$
1. Show that the expectation of $X$ does not exist.
2. Does the moment generating function exist? If **yes**, compute it. If **no**, prove it does not exist.
3. Let $U$, $V$ be two independent standard normal random variables, show that $\frac{U}{V}$ is Cauchy distributed.

---
> We know from messurment theory thst if $\int_{A} f \,dx$ doesn not exists, then $\int_{- \infty}^{\infty} f \,dx$ doese not exist
#### 1. Show that the expectation of $X$ does not exist.

We want to compute the expectation:

$$
\mathbb{E}(X) = \int_{-\infty}^{\infty} \frac{x}{\pi(1 + x^2)} \, dx
$$

---
Substitute $u = x^2 + 1$. Then:
$$
du = 2x \, dx \implies \frac{du}{2x} = dx
$$
---
$$
\int \frac{x}{\pi (x^2 + 1)} \, dx = \frac{1}{2\pi} \int \frac{1}{u} \, du
$$

>$\int \frac{1}{u} \, du = \ln(u)$

$\Rightarrow \frac{1}{2\pi} \ln(u)$
---
Back-substitution:
$$
u = x^2 + 1 \implies \frac{1}{2\pi} \ln(x^2 + 1)
$$
---

$$
\int \frac{x}{\pi (x^2 + 1)} \, dx = \frac{\ln(x^2 + 1)}{2\pi} + C
$$
And then we get: 
$$
\mathbb{E}(X) = \frac{1}{2\pi} \int_{1}^{\infty} u^{-1} \, du = \frac{1}{2\pi} \ln u \bigg|_{1}^{\infty} = \infty
$$
Therefore, the expectation **does not exist** because the integral diverges to infinity.

---

#### 2. Does the moment generating function exist?


We need to check if the moment generating function (MGF) exists for a Cauchy random variable.

---
#### Moment Generating Function Definition
The MGF of a random variable $X$ is defined by:

$$
M_X(t) = \mathbb{E}(e^{tX}) = \frac{1}{\pi} \int_{-\infty}^{\infty} \frac{e^{tx}}{1 + x^2} \, dx
$$

#### Claim:
The MGF $M_X(t)$ exists for **no** $t \in \mathbb{R}$. .
#### Proof:

- **Case 1: $t > 0$**

$$
\begin{split}
M_X(t) &= \frac{1}{\pi} \int_{-\infty}^{\infty} \frac{e^{tx}}{1 + x^2} \, dx \\
&= \frac{1}{\pi} \int_{0}^{\infty} \frac{e^{tx}}{1 + x^2} \, dx + \frac{1}{\pi} \int_{-\infty}^{0} \frac{e^{tx}}{1 + x^2} \, dx
\end{split}
$$

We'll focus on the integral from $0$ to $\infty$ which diverges.

---
 substitute:
$$
\begin{split}
u &= tx, \quad \frac{du}{dx} = t, \quad dx = \frac{du}{t} \\
\end{split}
$$
---
$$
\begin{split}
M_X(t) &= \frac{1}{\pi} \int_{0}^{\infty} \frac{e^{tx}}{1 + x^2} \, dx \\
&= \frac{t}{2\pi} \int_{\alpha}^{\infty} \frac{e^u}{u^2} \, du, \quad \text{where } \alpha = \max \{1, t\} 
\end{split}
$$
---
substitut:
$$
\begin{split}
v &= \frac{u}{2}, \quad dv = \frac{du}{2} \\
\end{split}
$$
---
$$
\begin{split}
M_X(t) &= \frac{t}{2\pi} \int_{\alpha/2}^{\infty} e^{v} \, dv \\
&= \frac{1}{\pi} \int_{\alpha/2}^{\infty} e^{v} \, dv \\
&= \frac{1}{\pi} \left( e^{\infty} - e^{\alpha/2} \right) \\
&= \infty
\end{split}
$$

Since the integral diverges, the MGF does not exist for $t > 0$. 

- **Case 2: $t < 0$**

We want to compute:

$$
M_X(t) = \frac{1}{\pi} \int_{-\infty}^{\infty} \frac{e^{tx}}{1 + x^2} \, dx
$$

Let's split the integral from $-\infty$ to $\infty$ into two parts. We focus on the negative side because $t < 0$ will cause divergence there.

$$
\begin{split}
M_X(t) &= \frac{1}{\pi} \int_{-\infty}^{0} \frac{e^{tx}}{1 + x^2} \, dx + \frac{1}{\pi} \int_{0}^{\infty} \frac{e^{tx}}{1 + x^2} \, dx
\end{split}
$$
---
 substitut:
 $$
  u = -x, du = -dx, \text{ and } x = -u
$$
---

  
  the integral becomes:

$$
\begin{split}
M_X(t) &= \frac{1}{\pi} \int_{0}^{\infty} \frac{e^{-tu}}{1 + u^2} \, du
\end{split}
$$

Now, rewrite the integral as:

$$
\begin{split}
M_X(t) &= \frac{1}{\pi} \int_{0}^{\infty} \frac{e^{-|t|u}}{1 + u^2} \, du
\end{split}
$$

Since $t < 0$, the term $e^{-|t|u}$ grows rapidly as $u \to \infty$, causing the integral to **diverge**. Therefore, the MGF does not exist for $t < 0$. 

- **Case 3: $t = 0$**

For $t = 0$, the MGF reduces to the integral of the Cauchy distribution:

$$
\begin{split}
M_X(0) &= \frac{1}{\pi} \int_{-\infty}^{\infty} \frac{1}{1 + x^2} \, dx
\end{split}
$$

Recognizing this as the integral of the standard Cauchy distribution:

$$
\begin{split}
M_X(0) &= \frac{1}{\pi} \int_{-\infty}^{\infty} \frac{1}{1 + x^2} \, dx = \frac{1}{\pi} \left( \tan^{-1}(x) \right) \bigg|_{-\infty}^{\infty} 
\end{split}
$$

$$
\begin{split}
M_X(0) &= \frac{1}{\pi} \left( \frac{\pi}{2} - \left( -\frac{\pi}{2} \right) \right) \\
&= \frac{1}{\pi} \cdot \pi = 1
\end{split}
$$

So, the MGF exists only for $t = 0$. 

---

### Conclusion

- **Case 1:** $t > 0$ $\implies$ The integral diverges.
- **Case 2:** $t < 0$ $\implies$ The integral diverges.
- **Case 3:** $t = 0$ $\implies$ The integral converges to $1$.

The MGF **only exists for $t = 0$**

---
#### 3. Let $U$, $V$ be two independent standard normal random variables, show that $\frac{U}{V}$ is Cauchy distributed.

---
We want to show that the random variable:

$$
Z = \frac{U}{V}
$$

where $U$ and $V$ are independent standard normal random variables, follows a standard Cauchy distribution.

---

- Joint Distribution of $U$ and $V$

Since $U$ and $V$ are independent standard normal variables, their joint distribution is:

$$
f_{U,V}(u, v) = \frac{1}{2\pi} \exp \left( -\frac{u^2 + v^2}{2} \right)
$$

- Finding the Distribution of $Z = \frac{U}{V}$

By the change of variables technique, we consider:

$$
\begin{split}
f_{U/V}(z) &= \int_{-\infty}^{\infty} f_{U,V}(zv, v) |v| \, dv \\
&= \int_{-\infty}^{\infty} \frac{1}{2\pi} \exp \left( -\frac{(zv)^2 + v^2}{2} \right) |v| \, dv \\
&= \frac{1}{2\pi} \int_{-\infty}^{\infty} \exp \left( -\frac{v^2(z^2 + 1)}{2} \right) |v| \, dv
\end{split}
$$
Simplification Using Polar Coordinates

Switching to polar coordinates:

$$
\begin{split}
u &= x \sqrt{1 + z^2}, \quad \frac{du}{dx} = \sqrt{1 + z^2}, \quad dx = \frac{du}{\sqrt{1 + z^2}} \\
\end{split}
$$

The integral becomes:

$$
\begin{split}
f_{U/V}(z) &= \frac{1}{\pi} \int_{0}^{\infty} \exp \left( -\frac{u^2}{2} \right) \, du \\
&= \frac{1}{\pi} \left( - e^{-u^2 / 2} \right) \bigg|_{0}^{\infty} \\
&= \frac{1}{\pi} \left(0 - (-1)\right) \\
&= \frac{1}{\pi}
\end{split}
$$


- The pdf of $Z$ is:

$$
f_Z(z) = \frac{1}{\pi} \frac{1}{1 + z^2}
$$

This is the standard Cauchy distribution. ✅

$$
\boldsymbol{Z = \frac{U}{V} \sim \text{Cauchy}(0,1)}
$$

-The final result shows that the ratio of two independent standard normal random variables is **Cauchy distributed**.