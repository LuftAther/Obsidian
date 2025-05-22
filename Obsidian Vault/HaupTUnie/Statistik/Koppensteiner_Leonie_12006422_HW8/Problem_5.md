Find the **asymptotic distribution** of the **sample median** and **quantiles** of a random sample drawn from $\mathrm{Exp}(\lambda)$.

![[Pasted image 20250517151409.png]]
$$
\sqrt{n} \left( \frac{np}{n} - p \right) = 0 \longrightarrow 0
$$

$$
\sqrt{n} \left( \frac{np + 1}{n} - p \right) = \frac{1}{\sqrt{n}} \longrightarrow 0
$$

Let $k_n$ be the indexes of any $p$-quantile for $n$ samples (e.g., $np$, $np + 1$ or $\lceil  np\rceil$).

Then:

$$
\sqrt{n} \left( \frac{k_n}{n} - p \right) \longrightarrow 0
$$

*follows from the sandwich theorem.*
$$
\sqrt{n} \left( X_{(k_n)} - x_p \right) \overset{d}{\longrightarrow} \mathcal{N} \left( 0, \frac{p(1 - p)}{\lambda^2 e^{-2 \lambda x_p}} \right)
$$

$$
\Rightarrow \underbrace{X_{(k_n)}}_{quantile} \approx \mathcal{N} \left( x_p, \frac{p(1 - p)}{\lambda^2 e^{-2 \lambda x_p}}\cdot \frac{1}{n} \right)
$$

Now use the exponential distribution:

$$
F(x) = 1 - e^{-\lambda x}
$$

Solve for the quantile:

$$\begin{align*}
p &= 1 - e^{-\lambda x} \\
p - 1 &= -e^{-\lambda x} \\
\ln(1 - p) &= -\lambda x \\
x &= -\frac{\ln(1 - p)}{\lambda}
\end{align*}$$

So the quantile is:

$$
F^{-1}(p) = -\frac{\ln(1 - p)}{\lambda}
$$

Compute the exponential term:

$$\begin{align*}
e^{-2 \lambda x_p}
&= \exp\left(-2 \lambda \cdot \left(-\frac{\ln(1 - p)}{\lambda}\right)\right) \\
&= \exp\left(\ln(1 - p)^2\right) = (1 - p)^2
\end{align*}$$

Thus:

$$
\Rightarrow X_{(k_n)} \approx \mathcal{N} \left( x_p, \frac{p(1 - p)}{\lambda^2 (1 - p)^2} \cdot \frac{1}{n} \right)
$$

$$
\Rightarrow X_{(k_n)} \approx \mathcal{N} \left( -\frac{\ln(1 - p)}{\lambda}, \frac{p}{n \lambda^2 (1 - p)} \right)
$$
**Special case** $p = \frac{1}{2}$: *median*

$$
X_{\underbrace{(k_n)}_{Median}} \approx \mathcal{N} \left( -\frac{\ln(1/2)}{\lambda}, \frac{1}{n \lambda^2} \right)
$$
