## Problem 3: Heads and Tails

Consider a sequence of independent coin flips, where each flip results in heads (H) with probability $p$, and tails (T) with probability $1 - p$.

Let the random variable $X$ be the **length of the initial run** of **identical outcomes** (either all heads or all tails), starting from the first flip.

For example:
- $X = 4$ if the first 4 flips are HHHH and the 5th is T (i.e., a run of 4 heads followed by a tail).
- $X = 4$ also if the first 4 flips are TTTT and the 5th is H (i.e., a run of 4 tails followed by a head).

---

### 1. Determine the distribution of $X$

We determine the **probability mass function (PMF)** of $X$.

Let’s assume the first flip is:
- Heads with probability $p$
- Tails with probability $1 - p$

Let $X = k$ for $k \in \mathbb{N}$. Then, the first $k$ flips must all be the same, and the $(k+1)$-th flip must differ.

So, we have two cases:

#### Case 1: Initial run of heads
$$
\mathbb{P}(X = k \mid \text{starts with heads}) = p^k (1 - p)
$$

#### Case 2: Initial run of tails
$$
\mathbb{P}(X = k \mid \text{starts with tails}) = (1 - p)^k p
$$

Thus, the full PMF is:
$$
\mathbb{P}(X = k) = p^k (1 - p) + (1 - p)^k p, \quad k \in \mathbb{N}
$$

This represents the probability that the first $k$ tosses are the same (either all H or all T), and the $(k+1)$-th toss is different.

---

### 2. Compute the expectation $\mathbb{E}[X]$

We use the definition of expected value:
$$
\mathbb{E}[X] = \sum_{k=1}^\infty k \cdot \mathbb{P}(X = k)
= \sum_{k=1}^\infty k \cdot \left( p^k (1 - p) + (1 - p)^k p \right)
$$

Split into two sums:
$$
\mathbb{E}[X] = (1 - p) \sum_{k=1}^\infty k p^k + p \sum_{k=1}^\infty k (1 - p)^k
$$

Each of these is the expected value of a **geometric distribution shifted by 1**.

Recall the identity:
$$
\sum_{k=1}^\infty k q^k = \frac{q}{(1 - q)^2}, \quad \text{for } 0 < q < 1
$$

Apply it:
- First sum:
  $$
  \sum_{k=1}^\infty k p^k = \frac{p}{(1 - p)^2}
  $$
- Second sum:
  $$
  \sum_{k=1}^\infty k (1 - p)^k = \frac{1 - p}{p^2}
  $$

Now plug in:
$$
\mathbb{E}[X] = (1 - p) \cdot \frac{p}{(1 - p)^2} + p \cdot \frac{1 - p}{p^2}
= \frac{p}{1 - p} + \frac{1 - p}{p}
$$

Combine the two terms:
$$
\mathbb{E}[X] = \frac{p^2 + (1 - p)^2}{p(1 - p)}
$$

This is the expected length of the first run of identical coin flips.

---

### Final Result

- **PMF**: $\mathbb{P}(X = k) = p^k(1 - p) + (1 - p)^k p$
- **Expected value**:
  $$
  \mathbb{E}[X] = \frac{p^2 + (1 - p)^2}{p(1 - p)}
  $$

---
