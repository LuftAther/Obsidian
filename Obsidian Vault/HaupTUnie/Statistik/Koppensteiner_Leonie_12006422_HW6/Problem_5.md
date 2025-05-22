## Problem 5: Difference of Means

If $\bar{X}_1$and $\bar{X}_2$are the sample means of size $n$of two independent samples from a population with finite variance $\sigma^2 \), find a value for $n$such that

$$
\mathbb{P}\left(|\bar{X}_1 - \bar{X}_2| < \frac{\sigma}{m}\right) \approx 99\%
$$

for fixed $m \in \mathbb{N} \). Justify your calculations.

---

Let the two sample means be defined as:

$$
\bar{X}_1 := \frac{1}{n} \sum_{i=1}^n X_{1,i} \quad \text{and} \quad \bar{X}_2 := \frac{1}{n} \sum_{i=1}^n X_{2,i}
$$

Let us define the difference: $Y_i := X_{1,i} - X_{2,i}$
Then: $\mathbb{E}(Y_i) = \mathbb{E}(X_{1,i}) - \mathbb{E}(X_{2,i}) = 0$
And since $X_{1,i}$ and $X_{2,i}$ are independent:
$$
\operatorname{Var}(Y_i) = \operatorname{Var}(X_{1,i} - X_{2,i}) = \operatorname{Var}(X_{1,i}) + \operatorname{Var}(X_{2,i}) = 2\sigma^2
$$
So it holds that : $\bar{Y}_n = \bar{X}_1 - \bar{X}_2$ 
$$
\Rightarrow
\mathbb{P}\left(|\bar{X}_1 - \bar{X}_2| < \frac{\sigma}{m} \right) = \mathbb{P}\left(|\bar{Y}_n| < \frac{\sigma}{m} \right)
$$

Apply the Central Limit Theorem (CLT):

$$
\bar{Y}_n \sim \mathcal{N}\left(0, \frac{2\sigma^2}{n} \right)
$$

Then:

$$
\mathbb{P}\left(|\bar{Y}_n| < \frac{\sigma}{m} \right)
= \mathbb{P}\left(\left| \frac{\sqrt{n} \bar{Y}_n}{\sqrt{2} \sigma} \right| < \frac{\sqrt{n}}{\sqrt{2} m} \right)
$$

Let $Z \sim \mathcal{N}(0,1)$, then:

$$
\mathbb{P}\left(|Z| < m \cdot \sqrt{\frac{n}{2}} \right)
= 2\Phi\left(m \cdot \sqrt{\frac{n}{2}}\right) - 1
$$

We want this probability to be approximately $0.99$, so:

$$
2\Phi\left(m \cdot \sqrt{\frac{n}{2}} \right) - 1 \approx 0.99 \quad \Rightarrow \quad \Phi\left(m \cdot \sqrt{\frac{n}{2}} \right) \approx 0.995
$$

From standard normal tables:

$$
m \cdot \sqrt{\frac{n}{2}} \approx 2.576
$$

Solving for $n$:

$$
\sqrt{\frac{n}{2}} \approx \frac{2.576}{m}
\quad \Rightarrow \quad
\frac{n}{2} \approx \left( \frac{2.576}{m} \right)^2
\quad \Rightarrow \quad
n \approx 2 \cdot \left( \frac{2.576}{m} \right)^2
$$

**Answer:**

$$
n \approx 2 \cdot \left( \frac{2.576}{m} \right)^2
$$

This is the required sample size to ensure:

$$
\mathbb{P}(|\bar{X}_1 - \bar{X}_2| < \frac{\sigma}{m}) \approx 0.99
$$

![[Pasted image 20250503001747.png]]