# Satz: 
Für endliches $\mu$ ist $\mathcal{F} \subset L^1(\mu)$ genau dann gleichgradig integrierbar, wenn es eine Funktion $H : [0, \infty) \to [0, \infty)$ gibt mit 
$$
\lim_{x \to \infty} \frac{H(x)}{x} = \infty
$$ 
und 
$$
\sup_{f \in \mathcal{F}} \int H(|f|) \, d\mu < \infty.
$$ 
$H$ kann sogar monoton wachsend und konvex gewählt werden.

# Beweis: 
("$\Leftarrow$") Es existiere $H$ mit den angegebenen Eigenschaften. Dann gilt 
$$
K_a := \inf_{x \geq a} H(x)
$$
für $x \uparrow \infty$, wenn $a \uparrow \infty$. Also ist für $a > 0$ 
$$
\sup_{f \in \mathcal{F}} \int_{|f| \geq a} |f| \, d\mu \leq \frac{1}{K_a} \sup_{f \in \mathcal{F}} \int_{|f| \geq a} H(|f|) \, d\mu \leq \frac{1}{K_a} \sup_{f \in \mathcal{F}} \int H (|f|) \, d\mu \quad \text{und} \quad a \to \infty \to 0.
$$

("$\Rightarrow$") Sei $\mathcal{F}$ gleichgradig integrierbar. Da $\mu(\Omega) < \infty$ gilt, gibt es (nach Satz 6.17) eine Folge $(a_n)_{n \in \mathbb{N}} \uparrow \infty$ mit
$$
\sup_{f \in \mathcal{F}} \int (|f| - a_n)^+ \, d\mu < 2^{-n}.
$$
Wir setzen 
$$
H(x) = \sum_{n=1}^{\infty} (x - a_n)^+ \quad \text{für jedes } x \geq 0.
$$
Dann ist $H$ als Summe konvexer Funktionen konvex. Ferner gilt für jedes $n \in \mathbb{N}$ und $x \geq 2a_n$, dass 
$$
\frac{H(x)}{x} \geq \sum_{k=1}^{n} (1 - \frac{a_k}{x})^+ \geq \frac{n}{2},
$$ 
also gilt $H(x)/x \uparrow \infty$.

Schließlich ist nach dem Satz über monotone Konvergenz für jedes $f \in \mathcal{F}$
$$
\int H(|f(\omega)|) \, \mu(d\omega) = \sum_{n=1}^{\infty} \int (|f| - a_n)^+ \, d\mu \leq \sum_{n=1}^{\infty} 2^{-n} = 1.
$$
