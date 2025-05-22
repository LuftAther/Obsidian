
Consider a random sample of size $n$ from a population with cdf $F$ and pdf $f$.

1. Show that the pdf of the sample range $R = X_{(n)} - X_{(1)}$ is:

$$
f_R(r) = n(n - 1) \int_{-\infty}^{\infty} \left[ F(r + u) - F(u) \right]^{n - 2} f(r + u) f(u) \, du, \quad \text{for } r > 0
$$

2. Specialize this pdf for samples from the **standard uniform distribution** $U(0,1)$.  
   Then **run a simulation in R** and compare the result with your theoretical result (how is up to you).

---
### 1) 

![[Pasted image 20250517153925.png]]

![[Pasted image 20250517153937.png]]
![[Pasted image 20250517153950.png]]



Let:
$$
\begin{split}
g(u, v) = 
\begin{pmatrix}
v - u
\end{pmatrix}
\end{split}
$$

$$
g^{-1}(a, b) = 
\begin{pmatrix}
a \\
a + b
\end{pmatrix}
$$

Jacobian matrix:

$$
J_{g^{-1}}(a, b) = 
\begin{pmatrix}
0 & 1 \\
1 & 1
\end{pmatrix}
$$

Determinant:$\left| \det J_{g^{-1}}(a, b) \right| = |0 \cdot 1 - 1 \cdot 1| = 1$
![[Pasted image 20250517155636.png]]

Let: $Y := g(X_{(1)}, X_{(n)})$

Then the joint density of $Y = (r, u)$ is:

$$f_Y(r, u) = f_{X_{(1)}, X_{(n)}}(g^{-1}(r, u)) \cdot \underbrace{\left|\det J_{g^{-1}}(r, u) \right|}_{=1} = n(n - 1) \left( F(r + u) - F(u) \right)^{n - 2} f(u) f(r + u)$$
Now marginalize to get the pdf of the range $R$:

$$f_R(r) = \int_{-\infty}^{\infty} f_Y(r, u) \, du = n(n - 1) \int_{-\infty}^{\infty} \left( F(r + u) - F(u) \right)^{n - 2} f(u) f(r + u) \, du$$
### 2) 
We consider  $U(0,1)$
The pdf and cdf of the uniform distribution on $[0,1]$ are:
$f(x) = \mathbf{1}_{[0,1]}(x)$

$$
F(x) = \begin{cases}
0 & x < 0 \\
x & 0 \le x < 1 \\
1 & 1 \le x
\end{cases}
$$

Now compute the pdf of the range $R$: 
$$f_R(r) = n(n - 1) \int_{-\infty}^{\infty} \left((r + u) - u\right)^{n - 2} \mathbf{1}_{[0,1]}(r + u) \, \mathbf{1}_{[0,1]}(u) \, du$$

Since $r + u \le 1$ and $u \in [0, 1] \Rightarrow u \in [0, 1 - r]$:
$$= n(n - 1) \int_{0}^{1 - r} r^{n - 2} \, du= n(n - 1) \, r^{n - 2} (1 - r), \quad r \in [0, 1]$$

```r
# Simulate the sampling distribution of the sample range
n <- 100
sample_ranges <- replicate(1000, diff(range(runif(n))))

# Plot histogram and theoretical density
hist(sample_ranges, probability = TRUE, breaks = 20, col = heat.colors(30),
     main = "Sample histogram and limit density",
     xlab = "Sample range", ylab = "Probability")

# Theoretical density curve for U(0,1)
r <- seq(0, 1, length = 512)
lines(r, n * (n - 1) * r^(n - 2) * (1 - r))
```

![[Pasted image 20250517164108.png]]