### **Problem 5 — Moments after Multiple Successes**

In independent Bernoulli trials with success probability $p$, the variable $X$ counting the number of failures before the $m$-th success has a **negative binomial distribution** with the following probability mass function:

$$
\mathbb{P}(X = x) = \binom{m + x - 1}{m - 1} p^m (1 - p)^x, \quad x = 0, 1, 2, \dots
$$

We are asked to:

1. **Find the moment-generating function (MGF) of $X$**
2. **Find the first two moments of $X$**

---

### **a) Moment-Generating Function**

Let $q = 1 - p$ and consider the definition of the MGF:

$$
M_X(t) = \mathbb{E}[e^{tX}] = \sum_{x=0}^\infty \binom{m + x - 1}{m - 1} p^m q^x e^{tx}
= p^m \sum_{x=0}^\infty \binom{m + x - 1}{m - 1} (qe^t)^x
$$

We use the identity:

$$
\sum_{x=0}^\infty \binom{m + x - 1}{m - 1} z^x = \frac{1}{(1 - z)^m}, \quad \text{for } |z| < 1
$$

Let $z = qe^t$, which requires $qe^t < 1 \Rightarrow t < -\log q = -\log(1 - p)$.

Therefore, for $t < -\log(1 - p)$:

$$
\begin{split}
M_X(t)
&= p^m \cdot \frac{1}{(1 - qe^t)^m} \\
&= \left( \frac{p}{1 - (1 - p)e^t} \right)^m
\end{split}
$$

---

### **b) First Moment (Mean)**

We compute the first derivative of $M_X(t)$:

$$
\begin{split}
M_X(t) &= \left( \frac{p}{1 - qe^t} \right)^m \\
M_X'(t) &= m \cdot \left( \frac{p}{1 - qe^t} \right)^m \cdot \frac{qe^t}{1 - qe^t}
\end{split}
$$

Evaluate at $t = 0$:

- $e^0 = 1$
- $1 - q = p$

$$
\begin{split}
M_X'(0) &= m \cdot \left( \frac{p}{p} \right)^m \cdot \frac{q \cdot 1}{p} = \frac{mq}{p}
\end{split}
$$

✅ Therefore, the **expected value** is:

$$
\mathbb{E}[X] = \frac{m(1 - p)}{p}
$$

---

### **c) Second Moment and Variance**

Now compute the second derivative:

Recall:

$$
M_X'(t) = m \cdot \left( \frac{p}{1 - qe^t} \right)^m \cdot \frac{qe^t}{1 - qe^t}
$$

Differentiate again:

$$
\begin{split}
M_X''(t)
&= m \cdot q \cdot \frac{d}{dt} \left( \frac{e^t \left( \frac{p}{1 - qe^t} \right)^m }{1 - qe^t} \right) \\
&= \frac{mqe^t (mqe^t + 1) \left( \frac{p}{1 - qe^t} \right)^m }{(1 - qe^t)^2}
\end{split}
$$

Now evaluate at $t = 0$:

- $e^0 = 1$, $1 - q = p$

$$
\begin{split}
M_X''(0)
&= \frac{mq (mq + 1) \left( \frac{p}{p} \right)^m}{p^2} \\
&= \frac{mq(mq + 1)}{p^2}
\end{split}
$$

So:

$$
\mathbb{E}[X^2] = M_X''(0) = \frac{mq(mq + 1)}{p^2}
$$

Then, the **variance** is:

$$
\begin{split}
\text{Var}(X)
&= \mathbb{E}[X^2] - \left( \mathbb{E}[X] \right)^2 \\
&= \frac{mq(mq + 1)}{p^2} - \left( \frac{mq}{p} \right)^2 \\
&= \frac{mq}{p^2}
\end{split}
$$

So the **variance** of $X$ is:

$$
\text{Var}(X) = \frac{m(1 - p)}{p^2}
$$
