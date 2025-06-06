## Geometric Exponential Family

Consider independent Bernoulli trials with success probability $p$ and let $X$ be the number of failures before the first success. Then:
$$
\mathbb{P}(X = x) = p(1 - p)^x, \quad x \in \{0, 1, 2, \dots\}
$$
(1) Show that the distributions form an exponential family.
(2) Write the pmfs in canonical form, identifying the natural parameter $\phi$ and function $b(\phi)$.
(3) Find the mean of the geometric distribution using a differential identity.
(4) Suppose $X_1, \dots, X_n$ are i.i.d. from $\text{Geom}(p)$. Show that the joint distribution is an exponential family and compute $\mathbb{E}(T)$ and $\text{Var}(T)$ for $T = \sum X_i$.

---
---

### 1) Geometric

For $x \in \mathbb{N}_0$:

$$
\begin{split}
\mathbb{P}(X = x) &= p (1 - p)^x \\
&= \exp\left( \ln(p (1 - p)^x) \right) \\
&= \exp\left( \ln(p) + x \cdot \ln(1 - p) \right)
\end{split}
$$
### Exponential Family

A family of pdfs or pmfs is called an **exponential family of distributions** if it can be written in the form

$$
f(x \mid \theta) = h(x) \, c(\theta) \, \exp\left( \sum_{i=1}^k w_i(\theta) \, t_i(x) \right)
$$

**Where:**

- $h(x) \geq 0$ and $t_1(x), \dots, t_k(x)$ are real-valued functions of the observation $x$ (they must not depend on $\theta$),
- $c(\theta) \geq 0$ and $w_1(\theta), \dots, w_k(\theta)$ are real-valued functions of the parameter vector $\theta$ (they must not depend on $x$).
- 
---
### 2) Natural Statistics and Natural Parameters

Let
- $y_i = t_i(x)$  
- $\psi_i = w_i(\theta)$

The log-likelihood in terms of **natural parameters** and **statistics** has the form:

$$
\ell(\psi) = y^\top \psi - b(\psi)
$$

The $k$-parameter vector $\psi$ is the **natural parameter**, and the set

$$
\left\{ f_\psi(x) = \exp\left( \sum_{i=1}^k \psi_i t_i(x) - b(\psi) \right) h(x) : \int f_\psi(x) dx = 1 \right\}
$$

is called a **$k$-parameter exponential family in canonical form**.
We identify:

$$
y = x, \quad \phi = \ln(1 - p)
$$

Then:

$$
\begin{split}
b(\phi) &= -\ln(p) \\
        &= -\ln\left(1 - \exp(\phi)\right)
\end{split}
$$

### Canonical Form

$$
\left\{
\mathbb{P}(X = x) = \exp\left( \ln(1 - p)x - (-\ln(1 - e^{\phi})) \right)
\ \middle|\ p \in [0,1]
\right\}
$$
---
### 3) MLE

The **log-likelihood derivative identities** give:

$$
\mathbb{E}_\psi(Y) = \nabla b(\psi), \quad \text{Var}_\psi(Y) = -\nabla^2 b(\psi)
$$

We compute the expectation of the sufficient statistic:

$$
\begin{split}
\mathbb{E}(X) &= \mathbb{E}(Y) = b'(\phi) = \frac{d}{d\phi} \left( -\ln(1 - e^{\phi}) \right) \\
&= -\frac{1}{1 - e^{\phi}} \cdot (-e^{\phi}) \\
&= \frac{e^{\phi}}{1 - e^{\phi}} = \frac{1 - p}{p} \quad \text{(since } \phi = \ln(1 - p) \text{)}
\end{split}
$$
---
### 4) Joint Distribution and Natural Statistic

Given i.i.d. geometric observations, the joint distribution is:

$$
\begin{split}
f(x \mid p) &= \prod_{i=1}^n \exp\left( \phi x_i - b(\phi) \right) \\
&= \exp\left( \phi \sum_{i=1}^n x_i - n b(\phi) \right)
\end{split}
$$

This confirms that the geometric distribution belongs to the exponential family (we look at the joint distribution).

---

### Natural Statistic

$$
T(X_1, \dots, X_n) = \sum_{i=1}^n X_i
$$

From the **log-likelihood derivative identities**:

$$
\mathbb{E}_\psi(Y) = \nabla b(\psi), \quad \text{Var}_\psi(Y) = -\nabla^2 b(\psi)
$$

→ In our case, we use $n b(\phi)$ instead of $b(\psi)$.

### Expectation of $T$

$$
\begin{split}
\mathbb{E}(T) &= n b'(\phi) = n \cdot \frac{1 - p}{p}
\end{split}
$$

### Variance of $T$

$$
\begin{split}
\text{Var}(T) &= n b''(\phi) = n \cdot \frac{d}{d\phi} \left( \frac{e^\phi}{1 - e^\phi} \right) \\
&= n \cdot \frac{e^\phi(1 - e^\phi) - (-e^\phi) \cdot e^\phi}{(1 - e^\phi)^2} \\
&= n \cdot \frac{e^\phi}{(1 - e^\phi)^2} = n \cdot \frac{1 - p}{p^2}
\end{split}
$$

where $\phi = \ln(1 - p)$.
wh