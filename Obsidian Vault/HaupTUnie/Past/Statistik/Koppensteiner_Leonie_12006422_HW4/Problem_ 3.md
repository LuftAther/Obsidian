## Conditional moments

Let $X, Y, Z$ be three random variables with finite variances, prove that

1. $\mathrm{Cov}(X, Y) = \mathrm{Cov}(X, \mathbb{E}(Y \mid X))$.
2. $X$ and $Y - \mathbb{E}(Y \mid X)$ are uncorrelated.
3. $\mathrm{Var}(Y - \mathbb{E}(Y \mid X)) = \mathbb{E}(\mathrm{Var}(Y \mid X))$.
4. $\mathrm{Cov}(X, Y) = \mathbb{E}(\mathrm{Cov}(X, Y \mid Z)) + \mathrm{Cov}(\mathbb{E}(X \mid Z), \mathbb{E}(Y \mid Z))$.

---

## 1. $\mathrm{Cov}(X, Y) = \mathrm{Cov}(X, \mathbb{E}(Y \mid X))$.

By the definition of covariance:

$$
\operatorname{Cov}(X, \mathbb{E}[Y \mid X]) = \mathbb{E}\left[ X \cdot \mathbb{E}[Y \mid X] \right] - \mathbb{E}[X] \cdot \mathbb{E}[\mathbb{E}[Y \mid X]]
$$

Recall the **law of iterated expectations**:

![[Pasted image 20250416120527.png]]

- $\mathbb{E}[\mathbb{E}[Y \mid X]] = \mathbb{E}[Y]$

Now rewrite the first term using the **tower property**:

$$
\mathbb{E}\left[ X \cdot \mathbb{E}[Y \mid X] \right]
= \mathbb{E} \left[ \mathbb{E}[X Y \mid X] \right] = \mathbb{E}[X Y]
$$

So we have:

$$
\operatorname{Cov}(X, \mathbb{E}[Y \mid X]) = \mathbb{E}[X Y] - \mathbb{E}[X] \cdot \mathbb{E}[Y]
= \operatorname{Cov}(X, Y)
$$

This tells us:  
> The covariance between a variable and the conditional expectation of another variable (given it) is just the regular covariance between them.

## 2. $X$ and $Y - \mathbb{E}(Y \mid X)$ are uncorrelated.

Start with the definition of covariance:

$\operatorname{Cov}(X, Y - \mathbb{E}[Y \mid X]) = \mathbb{E}\left[X \cdot (Y - \mathbb{E}[Y \mid X])\right] - \mathbb{E}[X] \cdot \mathbb{E}[Y - \mathbb{E}[Y \mid X]]$

Now we simplify each term:

####  First Term:

$$
\mathbb{E}[X \cdot (Y - \mathbb{E}[Y \mid X])] = \mathbb{E}[XY - X \cdot \mathbb{E}[Y \mid X]]
= \mathbb{E}[XY] - \mathbb{E}[X \cdot \mathbb{E}[Y \mid X]]
$$

But from **Part 1** we know:

$\mathbb{E}[X \cdot \mathbb{E}[Y \mid X]] = \mathbb{E}[XY]\Rightarrow \text{this term becomes } 0$

#### Second Term:

$$
\mathbb{E}[Y - \mathbb{E}[Y \mid X]] = \mathbb{E}[Y] - \mathbb{E}[\mathbb{E}[Y \mid X]] = \mathbb{E}[Y] - \mathbb{E}[Y] = 0
$$

So: $\mathbb{E}[X] \cdot \mathbb{E}[Y - \mathbb{E}[Y \mid X]] = \mathbb{E}[X] \cdot 0 = 0$

### Final Result:

$$
\operatorname{Cov}(X, Y - \mathbb{E}[Y \mid X]) = 0 - 0 = 0
$$

This confirms that:

> The residual $Y - \mathbb{E}[Y \mid X]$ is **uncorrelated** with the predictor $X$.

## 3. $\mathrm{Var}(Y - \mathbb{E}(Y \mid X)) = \mathbb{E}(\mathrm{Var}(Y \mid X))$.

We start by expanding the variance:

$$
\operatorname{Var}(Y - \mathbb{E}[Y \mid X]) 
= \mathbb{E}\left[ (Y - \mathbb{E}[Y \mid X])^2 \right] - \left( \mathbb{E}[Y - \mathbb{E}[Y \mid X]] \right)^2
$$

Now apply the **law of iterated expectations** to the first term:

$$
= \mathbb{E}\left( \mathbb{E}\left[ (Y - \mathbb{E}[Y \mid X])^2 \mid X \right] \right)
- \left( \mathbb{E}[Y] - \mathbb{E}[\mathbb{E}[Y \mid X]] \right)^2
$$

But since:

$$
\begin{split}
\mathbb{E}[\mathbb{E}[Y \mid X]] &= \mathbb{E}[Y] \quad \Rightarrow \text{second term is } 0\\
&\text{ we know that } \mathbb{E}[\mathbb{E}[X|Y]] = \mathbb{E}[X]
\end{split}
$$

So now we consider the first part of the term:  $\mathbb{E}\left( \mathbb{E}\left[ (Y - \mathbb{E}[Y \mid X])^2 \mid X \right] \right)$ 

$$\begin{split}
\mathbb{E}\left( \mathbb{E}\left[ (Y - \mathbb{E}[Y \mid X])^2 \mid X \right] \right)
&= \mathbb{E}\left( \operatorname{Var}(Y \mid X) \right) \\
&= \mathbb{E}\left( \mathbb{E}[Y^2 \mid X] - \left( \mathbb{E}[Y \mid X] \right)^2 \right) \\
&= \mathbb{E}[Y^2] - \mathbb{E}\left[ \left( \mathbb{E}[Y \mid X] \right)^2 \right]
\end{split}$$

$$
\operatorname{Var}(Y - \mathbb{E}[Y \mid X]) = \mathbb{E}\left[ \operatorname{Var}(Y \mid X) \right]
$$

Weil Baum [^1]

---

###  Note (Conditional Parallel Axis Theorem)
$$
\mathbb{E}[(Y - a(X))^2 \mid X] = \operatorname{Var}(Y \mid X) + (a(X) - \mathbb{E}[Y \mid X])^2
$$

Setting  $a(X) = \mathbb{E}[Y \mid X]$, the second term vanishes.

![[Pasted image 20250416122321.png]]

[^1]: We show:
	
	$$
	\operatorname{Var}(Y) = \mathbb{E}[\operatorname{Var}(Y \mid X)] + \operatorname{Var}(\mathbb{E}[Y \mid X])
	$$
	$$
	\begin{split}
	\operatorname{Var}(Y) 
	&= \mathbb{E}[Y^2] - (\mathbb{E}[Y])^2 \\
	&= \mathbb{E}\left[ \operatorname{Var}(Y \mid X) + (\mathbb{E}[Y \mid X])^2 \right] - (\mathbb{E}[\mathbb{E}[Y \mid X]])^2 \\
	&= \mathbb{E}[\operatorname{Var}(Y \mid X)] + \mathbb{E}[(\mathbb{E}[Y \mid X])^2] - (\mathbb{E}[Y])^2 \\
	&= \mathbb{E}[\operatorname{Var}(Y \mid X)] + \operatorname{Var}(\mathbb{E}[Y \mid X])
	\end{split}
	$$
---

## 4. $\mathrm{Cov}(X, Y) = \mathbb{E}(\mathrm{Cov}(X, Y \mid Z)) + \mathrm{Cov}(\mathbb{E}(X \mid Z), \mathbb{E}(Y \mid Z))$.

tart with the right-hand side:

$$
\begin{split}
\mathbb{E}[\operatorname{Cov}(X, Y \mid Z)] + \operatorname{Cov}(\mathbb{E}[X \mid Z], \mathbb{E}[Y \mid Z])
&= \mathbb{E}\left( \mathbb{E}[XY \mid Z] - \mathbb{E}[X \mid Z] \cdot \mathbb{E}[Y \mid Z] \right) \\
&\quad + \mathbb{E}\left[\mathbb{E}[X \mid Z] \cdot \mathbb{E}[Y \mid Z]\right] - \mathbb{E}[X] \cdot \mathbb{E}[Y] \\
&= \mathbb{E}[XY] - \mathbb{E}[\mathbb{E}[X \mid Z] \cdot \mathbb{E}[Y \mid Z]] \\
&\quad + \mathbb{E}[\mathbb{E}[X \mid Z] \cdot \mathbb{E}[Y \mid Z]] - \mathbb{E}[X] \cdot \mathbb{E}[Y] \\
&= \mathbb{E}[XY] - \mathbb{E}[X] \cdot \mathbb{E}[Y] \\
&= \operatorname{Cov}(X, Y)
\end{split}
$$