Sei $f$ eine reell- oder komplexwertige Funktion auf $[a, b]$, die über $[a, b]$ Riemann-integrierbar ist. Für $x \in [a, b]$ definiere
$$
F(x) := \int_a^x f(t) \, dt.
$$
Dann ist die Funktion $F : [a, b] \rightarrow \mathbb{R}$ (bzw. $\mathbb{C}$) stetig auf $[a, b]$.

Ist $f$ in einem Punkt $x_0$ stetig, so ist $F$ bei $x_0$ differenzierbar, und es gilt
$$
F'(x_0) = f(x_0).
$$

**Beweis.** Als erstes sei bemerkt, dass gemäß unserer Definition 8.2.1 die Funktion $f$ als Riemann-integrierbare Funktion auch beschränkt ist. Für $a \leq x < y \leq b$ folgt wegen (8.10)
$$
|F(y) - F(x)| = \left| \int_x^y f(t) \, dt \right| \leq \|f\|_{\infty} \cdot (y - x).
$$
Insbesondere ist $F$ stetig.

Sei nun $f$ stetig bei einem $x_0 \in [a, b)$. Ist $\epsilon > 0$ gegeben, so existiert $\delta > 0$, sodass
$$
|f(t) - f(x_0)| \leq \epsilon \quad \text{für alle } t \in [a, b] \text{ mit } |t - x_0| < \delta.
$$
Insbesondere gilt für $x_0 < x < \min(x_0 + \delta, b)$ wegen (8.10) und (8.7)
$$
\frac{F(x) - F(x_0)}{x - x_0} - f(x_0) = \frac{1}{x - x_0} \int_{x_0}^x (f(t) - f(x_0)) \, dt \leq \sup_{t \in [x_0, x]} |f(t) - f(x_0)| \leq \epsilon.
$$
Also folgt $F'_+(x_0) = \lim_{x \to x_0^+} \frac{F(x) - F(x_0)}{x - x_0} = f(x_0)$. Entsprechend zeigt man $F'_-(x_0) = f(x_0)$, wenn $x_0 \in (a, b]$.
$\square$
