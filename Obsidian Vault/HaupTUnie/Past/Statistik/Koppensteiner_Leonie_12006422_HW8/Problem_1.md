If $X_1, \ldots, X_n$ is a random sample **without replacement** from a finite population of size $N$, and each $X_i$ has variance $\sigma^2$, show that:

$$
\mathrm{Var}\left(\sum_{i=1}^n X_i\right) = n\sigma^2 \cdot \frac{N - n}{N - 1}
$$

The factor $\frac{N - n}{N - 1}$ is called the *finite population correction*.

---

We can rewrite: 
$$
\begin{split}
Var\left( \sum_{i = 1}^{n} X_{i} \right) &= \sum_{i,j}^n Cov(X_{i},X_{j})\\
&= \sum_{i=1}^n Var(X_{i}) + \sum_{j,i = 1, j \not=i}^{n} Cov(X_{i},X_{j})\\
&=\sum_{i=1}^n Var(X_{i}) + 2 \sum_{j=1}^{n-1} \sum_{i=j+1}^n Cov(X_{i},X_{j})

\end{split}

$$


Let $c := \mathrm{Cov}(X_1, X_2)$ ($\forall i \neq j : Cov(X_{i},X_{j} = c )$. Since all $X_k$ are equally distributed and come from a symmetric sampling setu:

- $\mathbb{E}(X_i)$ is the same for all $i$
- The joint distributions are the same for all pairs $\Rightarrow \mathbb{E}(X_i X_j)$ the same


$$
\Rightarrow \mathrm{Var}\left( \sum_{i=1}^n X_i \right) = n \sigma^2 + n(n - 1) c
$$

From the identity:

$$
\sum_{i=1}^N X_i = \text{constant}
\Rightarrow \mathrm{Var}\left( \sum_{i=1}^N X_i \right) = N \sigma^2 + N(N - 1) c = 0
$$

Solve for $c$:

$$
N \sigma^2 + N(N - 1) c = 0 \Rightarrow c = - \frac{\sigma^2}{N - 1}
$$

Now substitute $c$ back into our variance expression:

$$
\mathrm{Var} \left( \sum_{i=1}^n X_i \right) = n \sigma^2 + n(n - 1) \cdot \left( - \frac{\sigma^2}{N - 1} \right) = n \sigma^2 \left( 1 - \frac{n - 1}{N - 1} \right)
$$

Simplify:

$$
= n \sigma^2 \cdot \frac{N - n}{N - 1}
$$

which is the **finite population correction**.
