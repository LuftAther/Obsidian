## Delta Method

Let $X_1, X_2, \ldots$ be i.i.d. Bernoulli trials with success probability $p$ and denote by $\bar{X}_n$ the sample mean of the first $n$ variables.
1. Show that
$$
\sqrt{n}(\bar{X}_n - p) \xrightarrow{d} \mathcal{N}(0, p(1 - p)).
$$
2. In the case of $p \neq \frac{1}{2}$, show that the variance estimate $\bar{X}_n(1 - \bar{X}_n)$ satisfies
$$
\sqrt{n}(\bar{X}_n(1 - \bar{X}_n) - p(1 - p)) \xrightarrow{d} \mathcal{N}(0, p(1 - p)(1 - 2p)^2).
$$
3. On the other hand, if $p = \frac{1}{2}$, show that
$$
n(\bar{X}_n(1 - \bar{X}_n) - p(1 - p)) \xrightarrow{d} \frac{1}{4} \chi^2(1).
$$

4. Perform a simulation with 10,000 replications in R for the variance estimate $\bar{X}_n(1 - \bar{X}_n)$ and plot the histograms with their theoretical limiting distribution.  
   Do this simulation for different values of $p$, namely $0.1$, $0.25$, $0.49$ and $0.5$.
---
---
##### 1. Show that $\sqrt{n}(\bar{X}_n - p) \xrightarrow{d} \mathcal{N}(0, p(1 - p)).$

The variables are iid, $\mathbb{E}(X_1) = p$ and $\mathbb{V}(X_1) = p(1 - p)$.

Therefore, we can directly apply the CLT to obtain 
$$
\sqrt{n}(\bar{X}_n - p) \xrightarrow{d} \mathcal{N}(0, p(1 - p)).
$$

---
##### 2. In the case of $p \neq \frac{1}{2}$, show that the variance estimate $\bar{X}_n(1 - \bar{X}_n)$ satisfies $\sqrt{n}(\bar{X}_n(1 - \bar{X}_n) - p(1 - p)) \xrightarrow{d} \mathcal{N}(0, p(1 - p)(1 - 2p)^2).$

Assume that $p \neq \frac{1}{2}$. We use the Delta Method: Let $g(x) := x(1 - x)$. Then $g'(x) = 1 - 2x$. From the last task, we know that 
$$
\sqrt{n}(\bar{X}_n - p) \xrightarrow{d} \mathcal{N}(0, p(1 - p)).
$$
Apart from that, $g'(p) = 1 - 2p$ is zero if and only if $p = 1/2$, which is also required for the Delta Method.

By applying the Delta Method in this setting, we obtain
$$
\begin{split}
&\sqrt{n}(\bar{X}_n(1 - \bar{X}_n) - p(1 - p)) \\
&= \sqrt{n}(g(\bar{X}_n) - g(p)) \xrightarrow{d} \mathcal{N}(0, (1 - 2p)^2 p(1 - p))\\
&= \mathcal{N}(0, p(1 - p)(1 - 2p)^2)
\end{split}
$$
---

##### 3. On the other hand, if $p = \frac{1}{2}$, show that $n(\bar{X}_n(1 - \bar{X}_n) - p(1 - p)) \xrightarrow{d} \frac{1}{4} \chi^2(1).$

Assume that $p = \frac{1}{2}$. As opposed to the last task, $g'(p) = 0$. Therefore, we need the second order Delta Method.
Note that $g''(p) = -2 \neq 0$, which is required.
We apply the Delta Method to the convergence result from the first task to obtain
$$
\sqrt{n}(\bar{X}_n(1 - \bar{X}_n) - p(1 - p)) = \sqrt{n}(g(\bar{X}_n) - g(p)) \xrightarrow{d} \frac{\sigma^2 g''(p)}{2} \chi^2_1 = p(1 - p)\frac{-2}{2} \chi^2_1 = -\frac{1}{4} \chi^2_1
$$
---
##### 5. Perform a simulation with 10,000 replications in R for the variance estimate $\bar{X}_n(1 - \bar{X}_n)$ and plot the histograms with their theoretical limiting distribution.  Do this simulation for different values of $p$, namely $0.1$, $0.25$, $0.49$ and $0.5$.

```
# Number of observations in each sample (how many Bernoulli trials per estimator)
n <- 10000

# Number of Monte Carlo replications (i.e., how many variance estimators we simulate)
sample_size <- 10000

# Allocate space to store the estimated variances
var_estimates <- rep(0, sample_size)

# Loop over different values of p (success probability in Bernoulli trials)
for (p in c(0.1, 0.25, 0.49, 0.5)) {

  # Simulate 'sample_size' estimators of the variance for each p
  for (i in 1:sample_size) {
    # Generate n independent Bernoulli(p) samples
    samples <- rbinom(n, 1, p)

    # Compute the sample mean
    mean <- sum(samples) / n

    # Compute the variance estimator: X̄(1 - X̄)
    var_estimates[i] <- mean * (1 - mean)
  }

  # Center and scale the estimator based on whether p = 0.5 or not
  if (p != 0.5) {
    # For p ≠ 0.5: Use the Delta Method (first order), scaled by √n
    error <- sqrt(n) * (var_estimates - p * (1 - p))
  } else {
    # For p = 0.5: First derivative of g(x) = x(1 - x) vanishes at p,
    # so we use the second-order Delta Method, scale by n
    error <- n * (var_estimates - p * (1 - p))
  }

  # Plot the histogram of estimator errors
  hist(error, breaks=20, probability=TRUE,
       main=sprintf("p = %s", p),
       xlab="Estimator error",
       ylab="Density")

  # Define a grid for overlaying theoretical density
  x <- seq(min(error), max(error), length=1000)

  # Overlay theoretical limit distribution
  if (p != 0.5) {
    # Normal distribution predicted by CLT + Delta Method
    lines(x, dnorm(x, mean=0, sd=sqrt(p * (1 - p) * (1 - 2*p)^2)), col="#309898")
  } else {
    # Chi-squared distribution scaled by 1/4 (Second-order Delta Method)
    # Transform: If Z ~ χ²(1), then -1/4 * Z ~ distribution of interest
    lines(x, dchisq(-4 * x, 1) * 4, col="#309898")  # Jacobian correction included
  }
}

```



![[Pasted image 20250509102122.png]]]]

