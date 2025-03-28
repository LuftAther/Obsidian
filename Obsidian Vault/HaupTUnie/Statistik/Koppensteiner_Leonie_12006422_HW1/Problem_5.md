## Problem 5: Student’s t-distribution

Let:
- $Z \sim \mathcal{N}(0, 1)$, a standard normal variable,
- $W \sim \chi^2(\nu)$, a chi-squared variable with $\nu > 0$ degrees of freedom,
- and $Z$ and $W$ are independent.

Define the random variable:
$$
T = \frac{Z}{\sqrt{W / \nu}}
$$

Then $T \sim t(\nu)$, a Student's t-distribution with $\nu$ degrees of freedom.

---

### Goal: Derive the PDF of $T \sim t(\nu)$

Let’s derive the probability density function of $T$ using a **change of variables and convolution** approach.

---

### 1. Joint distribution of $Z$ and $W$

- The PDF of $Z \sim \mathcal{N}(0, 1)$ is:
$$
f_Z(z) = \frac{1}{\sqrt{2\pi}} e^{-z^2 / 2}
$$

- The PDF of $W \sim \chi^2(\nu)$ is:
$$
f_W(w) = \frac{1}{2^{\nu/2} \Gamma(\nu/2)} w^{\nu/2 - 1} e^{-w/2}, \quad w > 0
$$

Because $Z$ and $W$ are independent, the joint PDF is:
$$
f_{Z,W}(z, w) = f_Z(z) \cdot f_W(w)
$$

---

### 2. Change of variables

Let:
$$
T = \frac{Z}{\sqrt{W / \nu}} \quad \text{and} \quad U = W
$$

We want to find the marginal distribution of $T$. This requires the Jacobian of the transformation and integrating out $U$.

Solving for $Z$:  
$$
Z = T \sqrt{U / \nu}
$$

So the joint density of $T$ and $U$ is:
$$
f_{T,U}(t, u) = f_Z\left( t \sqrt{\frac{u}{\nu}} \right) \cdot f_W(u) \cdot \left| \frac{dZ}{dT} \right|
= \frac{1}{\sqrt{2\pi}} \exp\left( -\frac{t^2 u}{2\nu} \right) \cdot \frac{1}{2^{\nu/2} \Gamma(\nu/2)} u^{\nu/2 - 1} e^{-u/2} \cdot \sqrt{\frac{u}{\nu}}
$$

Now integrate out $u$ to get the marginal PDF of $T$:

$$
f_T(t) = \int_0^\infty f_{T,U}(t, u) \, du
$$

This integral simplifies to the **standard form of the t-distribution PDF**:

---

### Final Result: PDF of $T \sim t(\nu)$

$$
f_T(t) = \frac{\Gamma\left(\frac{\nu + 1}{2}\right)}{\sqrt{\nu \pi} \, \Gamma\left(\frac{\nu}{2}\right)} \cdot \left(1 + \frac{t^2}{\nu} \right)^{-(\nu + 1)/2}
$$

This is the probability density function of the Student's t-distribution with $\nu$ degrees of freedom.

---

### Properties

- Symmetric about 0
- Heavier tails than the normal distribution
- For $\nu \to \infty$, $t(\nu) \to \mathcal{N}(0, 1)$

---
