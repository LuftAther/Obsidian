## Problem 2: Inverse Sampling

Let $X$ be a continuous random variable with values in $[-\pi, \pi]$ with density $f_X$, that is $X \sim f_X$, where

$$
f_X(x) \propto |\sin(x)|
$$

The symbol $\propto$ stands for "proportional to" and means that there exists a constant $a \in \mathbb{R}$ such that $f_X(x) = a |\sin(x)|$.

1. Determine the constant $a \in \mathbb{R}$.

2. Compute the cumulative distribution function (cdf) $F_X$.

3. Let $U \sim U(0,1)$, what is the distribution of $F_X^{-1}(U)$?

4. Use the last point to write an R function `rsin(n)` which draws $n$ independent and identically distributed samples from the distribution of $X$.

5. Create a histogram of 10,000 samples and add the density $f_X$ to the plot to visualize that your function does in fact generate samples drawn from the right distribution.


---

### 1. Determine the constant $a \in \mathbb{R}$
- $f_{X} \geq 0$
- $\int _{-\pi}^{\pi} f_{X} \overset{?}{=} 1$
We normalize the density so that the total integral over the domain equals 1:
$$
\int_{-\pi}^{\pi} f_X(x) dx \overset{?}{=}\int_{-\pi}^{\pi} a |\sin(x)| dx
$$

Since $|\sin(x)|$ is symmetric around 0:
$$
2a\int_{-\pi}^{\pi} |\sin(x)| dx = 2a \int_0^{\pi} \sin(x) dx = 2a [-\cos(x)]_0^{\pi} = -2a(-1 - 1) = 4a
$$

So:
$$
a \cdot 4 = 1 \Rightarrow a = \frac{1}{4}
$$

Thus:
$$
f_X(x) = \frac{1}{4} |\sin(x)|, \quad x \in [-\pi, \pi]
$$

---

### 2. Compute the cumulative distribution function (CDF) $F_X$

We define:
$$
F_X(x) = \int_{-\pi}^{x} f_X(t) dt = \int_{-\pi}^{x} \frac{1}{4} |\sin(t)| dt
$$

Because $|\sin(t)|$ has a known structure, we can compute this piecewise:
- From $-\pi$ to 0, $\sin(t) \leq 0 \Rightarrow |\sin(t)| = -\sin(t)$
- From 0 to $\pi$, $\sin(t) \geq 0 \Rightarrow |\sin(t)| = \sin(t)$

So:

- For $x \in [-\pi, 0]$:
$$
F_X(x) = \frac{1}{4} \int_{-t}^{0} -\sin(t) dt = \frac{1}{4} [\cos(t)]_{-\pi}^{x} = \frac{1}{4} (\cos(x) + 1)
$$

- For $x \in [0, \pi]$:
$$
F_X(x) = \frac{1}{4} \int_0^t \sin(t) dt = \frac{1}{4} [-\cos(t)]_0^t =  -\frac{1}{4} \cos(x)+ \frac{1}{4}
$$

So the full CDF is:
$$
F_X(x) = \begin{cases} 
0 & \text{if } x \leq -\pi, \\
\frac{1}{4} \cos(x) + \frac{1}{4} & \text{if } -\pi < x \leq 0, \\
-\frac{1}{4} \cos(x) + \frac{3}{4} & \text{if } 0 < x \leq \pi, \\
1 & \text{if } \pi < x.
\end{cases}
$$

---

### 3. Let $U \sim \mathcal{U}(0,1)$, what is the distribution of $F_X^{-1}(U)$?

By the inverse transform sampling theorem, $F_X^{-1}(U) \sim X$, i.e., it has the same distribution as $X$.

So:
- If we can compute or numerically approximate $F_X^{-1}(u)$, then we can sample from the distribution of $X$ using $U \sim \mathcal{U}(0,1)$.

$$
Y = F_X^{-1}(U)
$$

$$
f_Y(y) = f_U \left( F_X(y) \right) \left| F_X'(y) \right| 
$$

$$
= \frac{1}{1 - 0} \cdot \frac{1}{4} |\sin(x)| = f_X(y)
$$

$$
\implies Y \sim F_X
$$


---

### 4. R function `rsin(n)`

Here’s an R function that uses inverse transform sampling:

```r
rsin <- function(n) {
  u <- runif(n)
  x <- numeric(n)
  
  for (i in 1:n) {
    if (u[i] < 0.5) {
      x[i] <- acos(4 * u[i] - 1) * (-1)
    } else {
      x[i] <- acos(2 - 4 * u[i])
    }
  }
  
  return(x)
}
```

#### 5 Create a histogram

```
# F_X^{-1}
FXinv <- function(u){
    if (0 <  u & u <= 0.5){
        return (acos(4*u-1) - pi)
    }
    else if (0.5 < u & u < 1){
        return (acos(-4*u+3))
    }
    else {
        simpleError("FXinf: Input out of range (0,1) !")
    }
}

rsin <- function(n){
    return (sapply(runif(n), FXinv))
}

# plotting
# see https://www.datacamp.com/tutorial/make-histogram-basic-r
hist(rsin(10000), probability=TRUE, breaks=40, col="blue")
x <- seq(-pi,pi, length=128)
lines(x, 0.25*abs(sin(x)), col="red", lwd=3)
legend("top", legend = c("histogram", "density"), lty=c(1,1), col=c("blue", "red"))
```

![[Pasted image 20250330151740.png]]