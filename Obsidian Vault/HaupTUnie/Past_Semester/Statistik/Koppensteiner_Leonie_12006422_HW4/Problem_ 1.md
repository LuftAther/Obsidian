##  Rejection sampling

Derive a rejection sampling algorithm to sample random values $X \in \mathbb{R}$ from a distribution with density [^1]

$$
f_X(x) = \frac{1}{\tau \pi} \, \mathrm{sinc} \left( \left( \frac{x - \mu}{\tau} \right)^2 \right)
$$

with location parameter $\mu \in \mathbb{R}$ and scale $\tau > 0$. Implement your algorithm in **R**. To test your algorithm, generate a sample of 100 000 random numbers and plot the simulated pdf and the actual pdf.

---

[^1]: $\mathrm{sinc}(x) = \frac{\sin(\pi x)}{\pi x}$ denotes the normalized sinc function.

---
we trieyed everythin even the paranormal distripution


![[Pasted image 20250415164625.png]]

We have: $f_X(x) = \frac{1}{\tau \pi} \, \mathrm{sinc} \left( \left( \frac{x - \mu}{\tau} \right)^2 \right)$

where:
- $\mu \in \mathbb{R}$ is the **location parameter**
- $\tau > 0$ is the **scale parameter**
- $\mathrm{sinc}(x) = \frac{\sin(\pi x)}{\pi x}$

And we want to simulate random values from this distribution using **rejection sampling**, implement the algorithm in **R**, and compare your simulated PDF with the actual one.

![[Pasted image 20250416104211.png]]

----

- **Key Idea**
	Rejection sampling is a method used to generate random samples from a **target density** $\pi(x)$, especially when it's difficult to sample from directly.
	We use an **easy-to-sample proposal distribution** $p(x)$ and a constant $M > 1$ such that:

$$
\pi(x) \leq M \cdot p(x) \quad \text{for all } x
$$

	Then we generate candidate values from $p(x)$ and accept them with a probability that ensures the samples follow $\pi(x)$.

- **Algorithm Steps**
	1. Sample $x \sim p(x)$
	2. Sample $y \sim \text{Uniform}(0, 1)$
	3. If $y \leq \frac{\pi(x)}{M \cdot p(x)}$, accept $x$ as a sample from $\pi(x)$
	4. Otherwise, reject $x$ and repeat
-  **Notes**
	- $p(x)$ must be **greater than or equal** to $\pi(x) / M$ everywhere.
	- The constant $M$ must be **large enough** to cover the shape of $\pi(x)$.
	- The **efficiency** of the method is roughly $1/M$.

- **When to Use**
	Use rejection sampling when:
	- You cannot invert the cumulative distribution function (CDF) of $\pi(x)$
	- You can find a suitable $p(x)$ that dominates $\pi(x)$
---

###  Choosing the Proposal Distribution

To apply rejection sampling, we need a proposal distribution $g(x)$ such that:

$$
f(x) \leq M \cdot g(x)
$$

We choose the **Student's t-distribution** with small degrees of freedom (e.g. $\nu = 0.5$) because:
- It is **heavy-tailed**: its density decreases slowly for large $|x|$
- Our **target distribution** (like $\mathrm{sinc}^2$) also decays slowly
- We need the proposal $p(x)$ to satisfy:  $\pi(x) \leq M \cdot p(x) \quad \text{for all } x$
- Common choices like the normal or exponential decay too fast and can't cover the tails effectively
Furthermore the t-distribution is:
- Easy to sample from
- Symmetric (matches many bell-shaped targets)
- Heavy-tailed enough to dominate $\pi(x)$ with a **reasonable constant $M$**



##  Derivation of the Rejection Bound $M$

We want to sample from the density:

$$
f(x) = \frac{1}{\pi} \cdot \mathrm{sinc}(x^2) = \frac{\sin^2(x^2)}{\pi x^2}
$$

Since this density is not easy to sample from directly, we use **rejection sampling** with a **Student’s t-distribution** as the proposal:

$$
g(x) = \alpha(\nu) \cdot \left(1 + \frac{x^2}{\nu}\right)^{-\frac{\nu+1}{2}}
$$

where

$$
\alpha(\nu) := \frac{1}{\sqrt{\nu \pi}} \cdot \frac{\Gamma\left(\frac{\nu+1}{2}\right)}{\Gamma\left(\frac{\nu}{2}\right)}
$$

###  Rejection Condition

We require: $f(x) \leq M \cdot g(x)$ or
$$\frac{\sin^2(x^2)}{\pi x^2} \leq M \cdot \alpha(\nu) \cdot \left(1 + \frac{x^2}{\nu} \right)^{-\frac{\nu + 1}{2}} \underbrace{\Rightarrow}_{* \pi} \frac{\sin^2(x^2)}{x^2} \leq M \cdot \pi \cdot \alpha(\nu) \cdot \left(1 + \frac{x^2}{\nu} \right)^{-\frac{\nu + 1}{2}}$$
Rewriting: $M \geq \frac{\sin^2(x^2)}{x^2} \cdot \frac{1}{\pi \cdot \alpha(\nu)} \cdot \left(1 + \frac{x^2}{\nu} \right)^{\frac{\nu + 1}{2}}$

Now we can analyse the therm:

$$
h(x) := \frac{\sin^2(x^2)}{x^2} \cdot \left(1 + \frac{x^2}{\nu} \right)^{\frac{\nu + 1}{2}}
$$

- For **large $|x|$**, $\sin^2(x^2) \leq 1$ and oscillates
- So $\frac{\sin^2(x^2)}{x^2}$ decays like $\sim \frac{1}{x^2}$
- Meanwhile, the $t$-density denominator:
  $$
  \left(1 + \frac{x^2}{\nu} \right)^{\frac{\nu + 1}{2}} \approx \left(\frac{x^2}{\nu}\right)^{\frac{\nu+1}{2}} \sim x^{\nu+1}
  $$
  → which **grows slower** than $x^2$ if $\nu < 1$

Therefore, for large $x$ we get:

$$
\frac{1}{x^2} \leq \frac{1}{x^{\nu+1}} \quad \text{if } \nu < 1
$$

So the inequality **can be satisfied with a finite $M$**, if $\nu$ is small enough.

Now we want to  find the **maximum** of:

$$
\frac{\sin^2(x^2)}{x^2 \cdot \left(1 + \frac{x^2}{\nu} \right)^{-\frac{\nu + 1}{2}}}
$$
So we consider

1. **For $|x| > x_0$** (e.g. $x_0 = 4$):  
   We show that:
   $$
   x^2 \geq \left(1 + \frac{x^2}{\nu} \right)^{\frac{\nu + 1}{2}}
   $$

   ⇒ This ensures the t-distribution dominates $f(x)$ in the tails.

2. **For $|x| \leq x_0$**:  
   We numerically bound the expression:
   $$
   \inf_{|x| \leq x_0} \left(1 + \frac{x^2}{\nu} \right)^{-\frac{\nu+1}{2}} \approx \text{some constant} > 0
   $$

From both parts, we obtain:

$$
M \cdot \pi \cdot \alpha(\nu) \cdot \min_{x \in \mathbb{R}} \left(1 + \frac{x^2}{\nu} \right)^{-\frac{\nu+1}{2}} \geq 1
$$

So the **minimal $M$** must satisfy:

$$
M \geq \frac{1}{\pi \cdot \alpha(\nu) \cdot \min_x \left(1 + \frac{x^2}{\nu} \right)^{-\frac{\nu+1}{2}}}
$$

And for a given $\nu$, we can plug in the numerical values:

$$
M = \frac{1}{\pi \cdot \text{min\_value} \cdot \alpha(\nu)}
$$

This general formula works for **any choice of $\nu$** (in practice, you choose small $\nu$ like $0.5$).

--- 
With $\nu = 0.5$ just ... because

The PDF of the t-distribution with $\nu = 0.5$ is:

$$
g(x) = \frac{1}{\sqrt{0.5\pi}} \cdot \frac{\Gamma(0.5)}{\Gamma(0.25)} \cdot \left(1 + \frac{x^2}{0.5}\right)^{-3/4}
$$


### Deriving the Bounding Constant $M$
We want:

$$
f(x) = \frac{\mathrm{sinc}(x)^2}{\pi} \leq M \cdot g(x)
$$

Through analysis (in the solution), the bound is derived as:

$$
M = \frac{1}{\pi \cdot 0.07 \cdot \alpha(1/2)}
$$

where:

$$
\alpha\left(\frac{1}{2}\right) = \frac{1}{\sqrt{0.5\pi}} \cdot \frac{\Gamma\left(\frac{3}{4}\right)}{\Gamma\left(\frac{1}{4}\right)}
$$

So putting it all together:

$$
M = \frac{\sqrt{\pi/2} \cdot \Gamma(0.25)}{\pi \cdot 0.07 \cdot \Gamma(0.75)}
$$

### R code

```r
# sinc function definition
sinc <- function(x){
  return (ifelse(x == 0, 1, sin(x)/x))
}

# rejection sampling for sinc^2 distribution
rsinc <- function(n, mu = 0, tau = 1){
  stopifnot(tau > 0)  # ensure tau is positive

  # compute bounding constant M
  M <- (sqrt(pi/2) * gamma(0.25)) / (pi * 0.07 * gamma(0.75))

  sinc_samples <- c()

  while (TRUE){
    student_sample <- rt(1, df = 0.5)
    u <- runif(1)

    # rejection condition
    if (M * dt(student_sample, df = 0.5) * u <= sinc(student_sample)^2 / pi){
      sinc_samples <- c(sinc_samples, student_sample)
    }

    if (length(sinc_samples) == n){
      return(tau * sinc_samples + mu)  # transform sample
    }
  }
}
```

#### Visualisation: [^2]

```r
# parameters
mu <- 10
tau <- pi
n <- 100000

samples <- rsinc(n, mu, tau)

# plot histogram vs. true density
from <- -50
to <- 50
hist(samples[(samples >= from) & (samples <= to)], 
     breaks = to - from, probability = TRUE,
     xlim = c(from, to), ylim = c(0, 0.4),
     xlab = "x", main = "Histogram vs. Density")

x <- seq(max(min(samples), from), min(max(samples), to), length = 512)
lines(x, sinc((x - mu)/tau)^2 / (pi * tau), col = "red", lwd = 2)
legend("topright", legend = c("True density"), col = "red", lty = 1)

```

[^2]: Visualization works only with the first code block
