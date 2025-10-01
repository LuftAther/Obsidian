## Problem 4: Sample Deviation

Suppose the unbiased sample variance $S_n^2$ is calculated from a random sample $X_1, \ldots, X_n$ drawn from a population with non-zero finite variance $\sigma^2$. We know that $\mathbb{E}[S_n^2] = \sigma^2$, show that

$$
\mathbb{E}[S_n] < \sigma \quad \text{where} \quad S_n = \sqrt{S_n^2}
$$

Assume further that $X_1, \ldots, X_n$ are i.i.d. draws from a normal distribution $\mathcal{N}(\mu, \sigma^2)$. Find a function $g_n$ of $S_n^2$ such that

$$
\mathbb{E}[g_n(S_n^2)] = \sigma
$$

Hint: Consider

$$
g_n(S_n^2) = c(n) \sqrt{S_n^2}
$$

---

## Solution to Problem 4: Sample Deviation

Let the sample variance be defined as:

$$
S_n^2 = \frac{1}{n-1} \sum_{i=1}^n (X_i - \bar{X}_n)^2
$$

We know that: $\mathbb{E}(S_n^2) = \sigma^2$

Let $S_n := \sqrt{S_n^2}$ and consider the function $g(x) = x^2$. We now apply **Jensen's inequality**, which states:

![[Pasted image 20250502234153.png]]

Using $g(x) = x^2$, which is convex, we get:

$$
\mathbb{E}(g(S_n)) = \mathbb{E}(S_n^2) = \sigma^2 \geq g(\mathbb{E}(S_n)) = \left(\mathbb{E}(S_n)\right)^2
$$
(strict inequality holds unless $S_n$ is almost surely constant, which is not the case).



We wanr to show that $\mathbb{E}(g(S_{n})) \not= g(\mathbb{E}(S_{n}))$
The tangent line $a x + b$ at $x = \mathbb{E}[S_n]$ is given by:

- $a = 2 \mathbb{E}[S_n]$
- $b = (\mathbb{E}[S_n])^2$

Then:

$$
\mathbb{P}_{S_n}(g(S_n) = a S_n + b) = \mathbb{P}_{S_n}(S_n^2 = 2 \mathbb{E}[S_n] S_n + (\mathbb{E}[S_n])^2)
$$

This is equivalent to:

$$
\mathbb{P}_{S_n}(S_n^2 - 2 \mathbb{E}[S_n] S_n - (\mathbb{E}[S_n])^2 = 0)
$$

Solving the quadratic equation:

$$
x^2 - 2 \mathbb{E}[S_n] x - (\mathbb{E}[S_n])^2 = 0
$$

gives:

$$
x_{1,2} = \mathbb{E}[S_n] \pm \sqrt{(\mathbb{E}[S_n])^2 + (\mathbb{E}[S_n])^2} = \mathbb{E}[S_n] \pm \sqrt{2}|\mathbb{E}[S_n]| = (1 \pm \sqrt{2}) \mathbb{E}[S_n]
$$

- The root $(1 - \sqrt{2}) \cdot \mathbb{E}(S_n) < 0$, but $S_n > 0$ almost surely.
- So the only valid solution is $(1 + \sqrt{2}) \cdot \mathbb{E}(S_n)$.

Therefore:

$$
\mathbb{P}_{S_n}(S_n = (1 + \sqrt{2}) \cdot \mathbb{E}(S_n)) \neq 1
$$

because $S_n$ is not deterministic. If it were:

$$
S_n \sim \delta_{(1 + \sqrt{2}) \mathbb{E}(S_n)} \Rightarrow \mathbb{E}(S_n) = (1 + \sqrt{2}) \cdot \mathbb{E}(S_n)
$$

which implies: $1 = 1 + \sqrt{2}$ witch is a contradiction.
Thus, the inequality is **strict**:
$$
\sigma^2 > (\mathbb{E}[S_n])^2 \Rightarrow \sigma > \mathbb{E}[S_n]
$$
and we get $g(x): = \frac{\sigma}{\mathbb{E}(\sqrt{S²_{n} })} \sqrt{ x }$