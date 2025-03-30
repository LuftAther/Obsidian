### Problem 5 (Student's t-distribution)

Given $Z \sim \mathcal{N}(0,1)$ and independently $W \sim \chi^2(\nu)$ with $0 < \nu$ degrees of freedom.  

Let

$$
T = \frac{Z}{\sqrt{W / \nu}}
$$

which follows a Student's t-distribution $t(\nu)$ with $\nu$ degrees of freedom. Derive the pdf of $T \sim t(\nu)$.

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

### 2. Calculation of $f_{T}$
We  have
$$
T = \frac{Z}{\sqrt{W / \nu}} \quad \text{and} \quad U = W
$$
We konw from messurment theorie that: 
$$f_{X_1 / X_2}(z) = \int f_1(zx) f_{2}(x) |x| \, d\lambda(x)$$
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
Final Result: PDF of $T \sim t(\nu)$

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
## Note in more detiles:
### Deriving the PDF of $T$

Given $T = \frac{Z}{\sqrt{W / \nu}}$, we want to find the PDF of $T$.  

By the change of variables formula we know from messurment theorie:

$$
f_{X_1 / X_2}(z) = \int f_1(zx) f_2 |x| \, d\lambda(x)
$$

---

$$
f_T(t) = \int_{0}^{\infty} f_Z(tx) f_{\sqrt{W / \nu}}(x) \, dx
$$

$$
= \int_{0}^{\infty} \frac{1}{\sqrt{2\pi}} \exp \left( -\frac{t^2 x^2}{2} \right) f_W \left( g^{-1}(x) \right) \left| \frac{d}{dx} g^{-1}(x) \right| \, dx
$$

---
> ### Substitution
>$$
g(x) = \sqrt{\frac{x}{\nu}}, \quad g^{-1}(y) = \nu y^2, \quad \frac{d}{dy} g^{-1}(y) = 2 \nu y
$$

---
$$
f_T(t) = \frac{1}{\sqrt{2\pi}} \int_{0}^{\infty} x \exp \left( -\frac{t^2 x^2}{2} \right)
\left( \frac{(\frac{1}{2})^{\nu/2}}{ \Gamma(\nu/2)} \right) \left( \nu x^2 \right)^{\nu/2 - 1} \exp \left( -\frac{\nu x^2}{2} \right) \cdot 2\nu x \, dx
$$


The integral we want to evaluate is:

$$
f_T(t) = \alpha \int_0^{\infty} x(x^2)^{\frac{\nu + 1}{2}-1}\exp \left( -\frac{1}{2}x^2 (t^2 + \nu) \right) \, dx
$$

Where:

$$
\alpha = \frac{ \left( \frac{1}{2} \right)^{\nu/2} \nu^{(\nu/2) - 1} \cdot 2 \nu }{ \sqrt{2\pi} \, \Gamma \left( \nu / 2 \right) }

$$
---
>Substitute:
>$$
u = x^2, \quad \frac{du}{dx} = 2x, \quad dx = \frac{du}{2x}
$$
---

$$
= \frac{\alpha}{2} \int_0^{\infty} u^{\frac{\nu + 1}{2} - 1} \exp \left( -\frac{t^2 + \nu}{2} u \right) \, du
$$

---
Now we substitute:

$$
w = \frac{t^2 + \nu}{2} u, \quad \frac{dw}{du} = \frac{t^2 + \nu}{2}
$$

$$
du = \frac{2}{t^2 + \nu} dw
$$
---
$$
= \frac{\alpha}{2} \frac{2}{t^2 + \nu} \left( \frac{2}{t^2 + \nu} \right)^{\frac{\nu+1}{2} - 1} \int_{0}^{\infty} w^{\frac{\nu+1}{2} - 1} e^{-w} \, dw
$$
---
>Recognizing the Gamma Function
>$$
>\int_0^{\infty} w^{\frac{\nu + 1}{2} - 1} e^{-w} \, dw = \Gamma \left( \frac{\nu + 1}{2} \right)
>$$
---

$$
= \frac{\alpha}{2} \left( \frac{2}{t^2 + \nu} \right)^{\frac{\nu+1}{2}} \Gamma \left( \frac{\nu+1}{2} \right)
$$

$$
= \frac{1}{2} \frac{\left( \frac{\nu}{2} \right)^{\nu/2}}{\sqrt{2\pi} \, \Gamma \left( \frac{\nu}{2} \right)} \cdot 2 \left( \frac{2}{t^2 + \nu} \right)^{\frac{\nu+1}{2}} \Gamma \left( \frac{\nu+1}{2} \right)
$$

$$
= \frac{\Gamma \left( \frac{\nu+1}{2} \right)}{\Gamma \left( \frac{\nu}{2} \right) \sqrt{\nu \pi} \sqrt{2} \left( \frac{t^2 + \nu}{\nu} \right)^{\frac{\nu+1}{2}}}
$$

$$
= \frac{\Gamma \left( \frac{\nu+1}{2} \right)}{\Gamma \left( \frac{\nu}{2} \right) \sqrt{\nu \pi}} \nu^{\nu/2} \left( t^2 + \nu \right)^{-\frac{\nu+1}{2}}
$$

$$
= \frac{\Gamma \left( \frac{\nu+1}{2} \right)}{\Gamma \left( \frac{\nu}{2} \right) \sqrt{\nu \pi} \nu^{\nu/2} \left( 1 + \frac{t^2}{\nu} \right)^{\frac{\nu+1}{2}}}
$$

$$
= \frac{\Gamma \left( \frac{\nu+1}{2} \right)}{\Gamma \left( \frac{\nu}{2} \right) \sqrt{\nu \pi} \left( 1 + \frac{t^2}{\nu} \right)^{\frac{\nu+1}{2}}}
$$

---

### Final Probability Density Function of $T$

$$
f_T(t) = \frac{ \Gamma \left( \frac{\nu + 1}{2} \right) }{ \Gamma \left( \frac{\nu}{2} \right) \sqrt{\nu \pi} \left( 1 + \frac{t^2}{\nu} \right)^{\frac{\nu + 1}{2}} }
$$

This is the standard **Student's t-distribution** with $\nu$degrees of freedom.
