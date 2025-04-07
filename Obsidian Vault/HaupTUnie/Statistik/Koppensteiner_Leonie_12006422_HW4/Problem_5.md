### Few Repeated Digits

Let $N$ be a discrete uniform random variable with values in the range $1$ to $99887$ (inclusive) such that no digit (without leading zeros) occurs more than two times in $N$. Define $d_k(n)$ to be the $k$-th digit of an integer $n$, for example:

- $d_1(1) = 1$
- $d_1(1234) = 1$
- $d_2(1234) = 2$
- If $k$ exceeds the number of digits, it is zero $d_2(1) = 0$.

Let $X_1 = d_1(N)$ and $X_2 = d_2(N)$.

1. Compute the joint probability $P(X_1, X_2)$, the conditional probabilities $P(X_1 | X_2)$ and $P(X_2 | X_1)$ as well as the marginal probabilities $P(X_1)$ and $P(X_2)$.
2. Are $X_1$ and $X_2$ independent?
3. Compute the expectations $\mathbb{E}[X_1]$, $\mathbb{E}[X_2]$, $\mathbb{E}[X_1 X_2]$ and the covariance $\text{Cov}(X_1, X_2)$.
**Use R for your computations, but all results need to be exact (provided as fractions).**

**Hint:** The total number of values $N$ can take is $91953$.

---
## Problem 5: Few Repeated Digits

### Given:
- Let $N$ be a discrete uniform random variable with values in the range $1$ to $99887$ (inclusive).
- No digit (without leading zeros) occurs more than two times in $N$.
- Define $d_k(n)$ to be the $k$'th digit of an integer $n$, for example:
  - $d_1(1) = 1$, $d_1(1234) = 1$
  - $d_2(1234) = 2$ but if $k$ exceeds the number of digits, it is zero ($d_2(1) = 0$).
- Let $X_1 = d_1(N)$ and $X_2 = d_2(N)$.

---

### 1. Joint Probability, Conditional Probability, and Marginal Probabilities

#### Marginal Probabilities

Since $N$ is a discrete uniform random variable ranging from $1$ to $99887$, and every number must follow the constraint of **no digit repeating more than twice**, the total number of valid values $N$ can take is $91953$.

- Probability of any valid number $N$:

$$
P(N) = \frac{1}{91953}
$$

- The **marginal probabilities** $P(X_1)$ and $P(X_2)$ are calculated by counting all occurrences of each digit $0$ through $9$ in the respective positions across all valid numbers.

- The probability for each $X_1 = x$ is:

$$
P(X_1 = x) = \frac{\text{Number of valid } N \text{ where } d_1(N) = x}{91953}
$$

- Similarly, for $X_2 = y$:

$$
P(X_2 = y) = \frac{\text{Number of valid } N \text{ where } d_2(N) = y}{91953}
$$

#### Joint Probability

The **joint probability** $P(X_1 = x, X_2 = y)$ is the probability of having a valid number $N$ where:

$$
P(X_1 = x, X_2 = y) = \frac{\text{Number of valid } N \text{ where } d_1(N) = x \text{ and } d_2(N) = y}{91953}
$$

#### Conditional Probabilities

Using the definition of conditional probability:

$$
P(X_1 = x \mid X_2 = y) = \frac{P(X_1 = x, X_2 = y)}{P(X_2 = y)}
$$

$$
P(X_2 = y \mid X_1 = x) = \frac{P(X_1 = x, X_2 = y)}{P(X_1 = x)}
$$

---

### 2. Independence of $X_1$ and $X_2$

To check whether $X_1$ and $X_2$ are independent, we need to verify if:

$$
P(X_1 = x, X_2 = y) = P(X_1 = x) P(X_2 = y)
$$

If this equality holds for all $x, y \in \{0, 1, \ldots, 9\}$, then $X_1$ and $X_2$ are independent. Otherwise, they are dependent.

---

### 3. Expectations, Covariance, and Correlation

#### Expectations

$$
\mathbb{E}[X_1] = \sum_{x=0}^{9} x P(X_1 = x)
$$

$$
\mathbb{E}[X_2] = \sum_{y=0}^{9} y P(X_2 = y)
$$

#### Joint Expectation

$$
\mathbb{E}[X_1 X_2] = \sum_{x=0}^{9} \sum_{y=0}^{9} xy \, P(X_1 = x, X_2 = y)
$$

#### Covariance

$$
\text{Cov}(X_1, X_2) = \mathbb{E}[X_1 X_2] - \mathbb{E}[X_1] \mathbb{E}[X_2]
$$

---


