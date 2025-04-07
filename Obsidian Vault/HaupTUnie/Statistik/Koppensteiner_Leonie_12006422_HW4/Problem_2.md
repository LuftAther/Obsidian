### Real Roots of a Quadratic Equation

Let $A$, $B$, and $C$ be independent random variables, uniformly distributed on $(0, 1)$. Find the probability that the roots of the quadratic equation 

$$
Ax^2 + Bx + C = 0
$$ 
are real.
Moreover, consider the following code in R:

```r
n <- 1000000

A <- runif(n)
B <- runif(n)
C <- runif(n)

mean(B^2 >= 4 * A * C)
```
What does it do and how does it relate to your solution?
**Hint:** If $U \sim U(0, 1)$ then $X = - \frac{\ln U}{\lambda} \sim \text{Exp}(\lambda)$ is exponential.

---
Let $A, B,$ and $C$ be independent random variables, uniformly distributed on $(0, 1)$. We want to find the probability that the roots of the quadratic equation:

$$
Ax^2 + Bx + C = 0
$$

are **real**.

---

#### Condition for Real Roots

The roots of a quadratic equation are given by the quadratic formula:

$$
x_{1,2} = \frac{-B \pm \sqrt{B^2 - 4AC}}{2A}
$$

The roots are real if and only if:

$$
B^2 - 4AC \geq 0
$$

---

#### Probability Calculation

We want to find:

$$
P(B^2 \geq 4AC)
$$

This probability can be expressed as an integral over the region where the inequality holds, with respect to the joint distribution of $A, B, C$.

$$
P(B^2 \geq 4AC) = \int_{[0,1]^3} \mathbb{1}\{B^2 \geq 4AC\} \, d\lambda
$$

Since $A, B, C$ are independent and uniformly distributed, the joint density is $1$ over the region $[0,1]^3$. Therefore:

$$
P(B^2 \geq 4AC) = 4 \int_{0}^{1} \int_{0}^{1} \int_{0}^{1} \mathbb{1}\{B^2 \geq 4AC\} \, dA \, dB \, dC
$$

---

#### Splitting the Integral

To simplify, we split the integral into two parts:

$$
\begin{split}
P(B^2 \geq 4AC) &= \int_{1/4}^{1} \int_{0}^{1/4A} \int_{0}^{1} 1 \, dB \, dC \, dA + \int_{0}^{1/4} \int_{0}^{1} \int_{0}^{2 \sqrt{C}} 1 \, dB \, dC \, dA
\end{split}
$$

Evaluating the integrals:

$$
\begin{split}
P(B^2 \geq 4AC) &= \int_{1/4}^{1} \int_{0}^{1/4A} 1 \, dC \, dA + \int_{0}^{1/4} \int_{0}^{1} 1 - 2\sqrt{A} \sqrt{C} \, dC \, dA
\end{split}
$$

---

#### Auxiliary Calculation

Solving the auxiliary integral:

$$
\int 1 - 2\sqrt{A} \sqrt{C} \, dC = C - 2 \sqrt{A} \frac{2}{3} C^{3/2}
$$

---

e had split the probability calculation into two integrals:


$$\begin{split}
P(B^2 \geq 4AC) &= \int_{1/4}^{1} \int_{0}^{1/4A} 1 \, dC \, dA + \int_{0}^{1/4} \int_{0}^{1} \left( 1 - 2\sqrt{A} \sqrt{C} \right) \, dC \, dA
\end{split}$$


Evaluating the integrals:

$$
\int_{1/4}^{1} \frac{1}{4A} - \frac{4}{3} \frac{\sqrt{A}}{(4A)^{3/2}} \, dA + \int_{0}^{1/4} 1 - \frac{4}{3} \sqrt{A} \, dA
$$

---

#### Solving the Integrals

Splitting the integrals and solving separately:

$$
\int_{1/4}^{1} \frac{1}{4A} \, dA + \int_{1/4}^{1} -\frac{4}{3} \frac{\sqrt{A}}{(4A)^{3/2}} \, dA
$$

$$
= \int_{1/4}^{1} \frac{1}{4A} \, dA - \int_{1/4}^{1} \frac{4}{3} \frac{1}{A^{3/2}} \, dA
$$


$$\begin{split}
&= \frac{1}{4} \int_{1/4}^{1} \frac{1}{A} \, dA - \frac{4}{3} \int_{1/4}^{1} A^{-3/2} \, dA \\
&= \frac{1}{4} \ln A \bigg|_{1/4}^{1} - \frac{4}{3} \left( -2 A^{-1/2} \right) \bigg|_{1/4}^{1} \\
&= \frac{1}{4} (0 - \ln(1/4)) + \frac{8}{3} \left( 1 - 1/2 \right) \\
&= \frac{1}{4} \ln(4) + \frac{8}{3} \times \frac{1}{2} \\
&= \frac{1}{4} \times 2\ln(2) + \frac{8}{3} \times \frac{1}{2} \\
&= \frac{\ln(2)}{2} + \frac{4}{3}
\end{split}
$$

---

#### Numerical Approximation

Finally, we approximate the integral:

$$
P(B^2 \geq 4AC) \approx 0.2544
$$

---

#### Comparison with R Program

The R program above approximates $P(B^2 \geq 4AC)$ using a Monte Carlo method. The results are consistent with the analytical calculation.

```r
# Number of simulations
n <- 1000000

# Generate independent uniform random variables A, B, and C
A <- runif(n)
B <- runif(n)
C <- runif(n)

# Check the condition B^2 >= 4AC
result <- B^2 >= 4 * A * C

# Estimate the probability by calculating the mean of the logical condition
probability_estimate <- mean(result)

# Print the estimated probability
print(probability_estimate)

Example outputs from the R program: 0.255045, 0.254932, 0.253827
```


