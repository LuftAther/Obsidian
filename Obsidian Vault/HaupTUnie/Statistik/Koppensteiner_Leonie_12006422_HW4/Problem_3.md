### Characteristic function

Show that the characteristic function $\phi : \mathbb{R} \to \mathbb{C}$ of a scalar random variable $X$ with cdf $F$ has the following properties:

1. Its absolute value is bounded by 1, that is 
$$
|\phi(t)| \leq \phi(0) = 1 \quad \text{for all } t \in \mathbb{R}.
$$
2. $\phi$ is uniformly continuous if $\mathbb{E}|X|$ is finite.
3. $\phi$ is real-valued if $X$ is symmetric around zero.
4. If $\mathbb{E}|X|^n$ exists for some $n \in \mathbb{N}$, then $\phi$ is $n$-times differentiable and for $r \leq n$:
$$
\phi^{(r)}(t) = \int_{\mathbb{R}} (ix)^r e^{itx} \, dF(x), \quad \phi^{(r)}(0) = i^r \mathbb{E}[X^r].
$$

---
#### Characteristic Function Definition

The characteristic function of a random variable $X$ is defined by:

$$
\phi(t) = \mathbb{E} \left( e^{itX} \right) = \int_{-\infty}^{\infty} e^{itx} dF(x)
$$

---

#### 1. Boundedness

We want to show:

$$
|\phi(t)| \leq \phi(0) = 1 \quad \text{for all } t \in \mathbb{R}
$$

$$\begin{split}
|\phi(t)| &= \left| \mathbb{E} \left( e^{itX} \right) \right| \\
&= \left| \int_{-\infty}^{\infty} e^{itx} dF(x) \right| \\
&\leq \int_{-\infty}^{\infty} \left| e^{itx} \right| dF(x) \\
&= \int_{-\infty}^{\infty} dF(x) \\
&= 1
\end{split}$$

Thus, we have shown that:

$$
|\phi(t)| \leq 1
$$

✅

---

#### 2. Uniform Continuity

We want to show that $\phi(t)$ is uniformly continuous if $\mathbb{E}|X| < \infty$.

By definition:

$$
\phi(t) = \int_{-\infty}^{\infty} e^{itx} dF(x)
$$

Now, consider:

$$
\begin{split}
|\phi(t+h) - \phi(t)| &= \left| \int_{-\infty}^{\infty} \left( e^{i(t+h)x} - e^{itx} \right) dF(x) \right| \\
&= \left| \int_{-\infty}^{\infty} e^{itx} \left( e^{ihx} - 1 \right) dF(x) \right| \\
&\leq \int_{-\infty}^{\infty} \left| e^{ihx} - 1 \right| dF(x)
\end{split}
$$

Using the inequality:

$$
\left| e^{ihx} - 1 \right| \leq |h x|
$$

Therefore, by the **Dominated Convergence Theorem**, as $h \to 0$:

$$
\phi(t+h) \to \phi(t)
$$

This shows that $\phi(t)$ is uniformly continuous. ✅

---

#### 3. Symmetry

We want to show that $\phi(t)$ is real-valued if $X$ is symmetric around zero.

#### Symmetry Proof

If $X$ is symmetric around zero, then:

$$
f_X(x) = f_X(-x)
$$

Now, consider the characteristic function evaluated at $-t$:

$$
\phi(-t) = \int_{-\infty}^{\infty} e^{-itx} dF(x)
$$

By complex conjugation and the definition of the characteristic function:

$$
\phi(-t) = \int_{-\infty}^{\infty} e^{-itx} dF(x) = \int_{-\infty}^{\infty} \overline{e^{itx}} dF(x) = \overline{\phi(t)}
$$

Therefore:

$$
\phi(t) = \overline{\phi(t)}
$$

This implies that $\phi(t)$ is **real-valued**

---

#### 4. Differentiability and Moments

We want to show that if $\mathbb{E} |X|^n$ exists for some $n \in \mathbb{N}$, then $\phi(t)$ is $n$-times differentiable.

#### Differentiability Proof

The $r$-th derivative of the characteristic function is:

$$
\phi^{(r)}(t) = \frac{d^r}{dt^r} \int_{-\infty}^{\infty} e^{itx} dF(x)
$$

By differentiating under the integral sign:

$$
\phi^{(r)}(t) = \int_{-\infty}^{\infty} \frac{\partial^r}{\partial t^r} \left( e^{itx} \right) dF(x)
$$

Evaluating the derivative:

$$
\phi^{(r)}(t) = \int_{-\infty}^{\infty} (ix)^r e^{itx} dF(x)
$$

Now, evaluating the derivative at $t = 0$:

$$
\phi^{(r)}(0) = \int_{-\infty}^{\infty} (ix)^r e^{0} dF(x) = \int_{-\infty}^{\infty} (ix)^r dF(x)
$$

Therefore, we have:

$$
\phi^{(r)}(0) = i^r \mathbb{E} \left( X^r \right)
$$

---

#### Conclusion

If $\mathbb{E}|X|^n < \infty$, then $\phi(t)$ is $n$-times differentiable, and:

$$
\phi^{(r)}(0) = i^r \mathbb{E} \left( X^r \right)
$$
