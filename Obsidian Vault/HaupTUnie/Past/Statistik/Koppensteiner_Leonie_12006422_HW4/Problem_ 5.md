## Hospitals and births

There are two hospitals in a city. 55 babies are born every day in the larger hospital, while 18 babies are born in the smaller hospital every day. Over a year, each hospital recorded the days when more than 70% of babies born have the same gender (either boys or girls with 50-50 chance of being a boy or a girl).

1. Let $L_i$ be the Bernoulli random variable that takes the value 1 if more than 70% of babies born on the $i$th day in the larger hospital were of the same gender and similarly $S_i$ for the smaller hospital.  
   Find the distributions of $L_i$ and $S_i$.
2. Let $L$ be the number of days on which more than 70% of babies born in the larger hospital were of the same gender and similarly $S$ for the smaller hospital.  
   What is the distribution of $L$ and $S$? Compute the expected value and the variance of $L$ and $S$.
3. What is the correlation between $L$ and $S$?


---
## 1.  Let $L_i$ be the Bernoulli random variable that takes the value 1 if more than 70% of babies born on the $i$ th day in the larger hospital were of the same gender and similarly $S_i$ for the smaller hospital.  Find the distributions of $L_i$ and $S_i$.

We define:

- $L_i$: indicator for "more than 70% of babies born in the larger hospital on day $i$ are of the same gender"
- $S_i$: same for the smaller hospital


###  Distribution of $L_i$ (Larger Hospital)

More than 70% of 55 babies $\Rightarrow$ at least 39 of them are of the same gender  
(i.e., either $\geq 39$ female or $\geq 39$ male)
Let $Y \sim \operatorname{Bin}(55, 1/2)$
Then:

$$
\mathbb{P}(L_i = 1) = \sum_{j = 39}^{55} \left( \mathbb{P}(j \text{ female}) + \mathbb{P}(j \text{ male}) \right)
$$

By symmetry:

$$
= 2 \cdot \sum_{j = 39}^{55} \mathbb{P}(Y = j)
$$

Using the cumulative distribution function:

$$
= 2 \cdot (1 - F_{\operatorname{Bin}(55, \frac{1}{2})}(38)) \approx 0.00267
$$

Alternative expression:

$$
\mathbb{P}(L_i = 1) = 2 \cdot \sum_{j = 39}^{55} \binom{55}{j} \left( \frac{1}{2} \right)^j \left( \frac{1}{2} \right)^{55 - j}
= \frac{1}{2^{55}} \sum_{j = 39}^{55} \binom{55}{j}
$$

Numerically:

$$
\mathbb{P}(L_i = 1) = \frac{R}{2^{54}}, \quad \text{where } R = 480\,491\,300\,000\,000
$$

### Distripution of $S_{i}$ (Small Hospital): 

More than 70% of 18 babies $\Rightarrow$ at least 13 of them are of the same gender
Let $Y \sim \operatorname{Bin}(18, 1/2)$
Then:

$$
\mathbb{P}(S_i = 1) = 2 \cdot \sum_{j = 13}^{18} \binom{18}{j} \left( \frac{1}{2} \right)^j \left( \frac{1}{2} \right)^{18 - j}
= \frac{1}{2^{117}} \sum_{j = 13}^{18} \binom{18}{j}
$$

So we get:
$$
\mathbb{P}(S_i = 1) = \frac{12\,616}{2^{17}}
$$

---
## 2. Let $L$ be the number of days on which more than 70% of babies born in the larger hospital were of the same gender and similarly $S$ for the smaller hospital. What is the distribution of $L$ and $S$? Compute the expected value and the variance of $L$ and $S$.


Let $L$ and $S$ be the total number of days (out of 365) where the large or small hospital had more than 70% of births being the same gender.

### Distribution of $L$

Since each $L_i \sim \operatorname{Bernoulli}(p)$ with

$$
p = \frac{480\,491\,300\,000\,000}{2^{54}} \approx 0.00267,
$$

and all days are independent:

$$
L \sim \operatorname{Binomial}(365, \frac{480\,491\,300\,000\,000}{2^{54}})
$$

- **Expected value:**

$$
\mathbb{E}(L) = 365 \cdot \frac{480\,491\,300\,000\,000}{2^{54}} \approx 0.97
$$

- **Variance:**

$$
\operatorname{Var}(L) = 365 \cdot \frac{480\,491\,300\,000\,000}{2^{54}} \left(1 - \frac{480\,491\,300\,000\,000}{2^{54}}\right) \approx 0.97
$$
### Distribution of $S$

Similarly, since:

$$
p = \frac{12\,616}{2^{17}} \approx 0.0963,
$$

we have:

$$
S \sim \operatorname{Binomial}(365, \frac{12\,616}{2^{17}})
$$

- **Expected value:**

$$
\mathbb{E}(S) = 365 \cdot \frac{12\,616}{2^{17}} \approx 35.132
$$

- **Variance:**

$$
\operatorname{Var}(S) = 365 \cdot \frac{12\,616}{2^{17}} \left(1 - \frac{12\,616}{2^{17}}\right) \approx 31.75
$$

-----


### 3. What is the correlation between $L$ and $S$?

Let:

- $L = \sum_{i=1}^{365} L_i$
- $S = \sum_{i=1}^{365} S_i$

We want to compute the correlation:

$$
\rho(L, S) = \frac{\operatorname{Cov}(L, S)}{\sqrt{\operatorname{Var}(L)} \cdot \sqrt{\operatorname{Var}(S)}}
$$

---

###  Covariance of $L$ and $S$

By the bilinearity of covariance:

$$
\operatorname{Cov}(L, S) = \operatorname{Cov} \left( \sum_{i=1}^{365} L_i, \sum_{j=1}^{365} S_j \right)
= \sum_{i=1}^{365} \sum_{j=1}^{365} \operatorname{Cov}(L_i, S_j)
$$

Since the hospitals are **independent**, $L_i$ and $S_j$ are independent for all $i, j$, and thus:

$$
\operatorname{Cov}(L_i, S_j) = 0 \quad \Rightarrow \quad \operatorname{Cov}(L, S) = 0
$$

---

###  Correlation

Therefore:

$$
\rho(L, S) = \frac{0}{\sqrt{\operatorname{Var}(L)} \cdot \sqrt{\operatorname{Var}(S)}} = 0
$$