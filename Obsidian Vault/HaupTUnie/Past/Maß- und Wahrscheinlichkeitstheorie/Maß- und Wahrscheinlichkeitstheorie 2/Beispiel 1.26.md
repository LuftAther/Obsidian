Angenommen, unser Messraum ist ein Wahrscheinlichkeitsraum (wir schreiben also $\mathbb{P}$ anstelle von $\mu$) und $F$ ist eine Familie von Zufallsvariablen $X$, die einer Exponentialverteilung mit Parameter $\lambda \in [A, B]$ für einige $A, B \in [0,1)$ folgen. Untersuchen wir, ob diese Familie  gleichgradig integrierbar ist. Erinnern wir uns daran, dass eine exponentialverteilte Zufallsvariable mit Parameter $\lambda$ eine Dichtefunktion bezüglich des Lebesgue-Maßes auf $\mathbb{R}$ besitzt, die durch $\varphi(x) = \lambda e^{-\lambda x} , 1_{x>0}$ gegeben ist. Äquivalent gilt $P(X > z) = e^{-\lambda z}$ für $z > 0$. Beachten Sie auch, dass
$$\int |X| \, 1_{\{|X| > a\}} \, dP = \mathbb{E}[|X| \, 1_{\{|X| > a\}}] = \int_a^{\infty} \lambda x e^{-\lambda x} \, dx = \frac{1}{\lambda} \int_{a \lambda}^{\infty} y e^{-y} \, dy = \frac{a \lambda + 1}{\lambda} e^{-\lambda a}\tag{1.23}$$
Beachten Sie, dass dieser Ausdruck gegen null strebt, wenn $a \to \infty$, aber divergiert, wenn $\lambda \to 0$. Daher sehen wir, dass wenn $A > 0$ (sodass $\lambda > A$), unsere Familie $\mathcal{F}$  gleichgradig integrierbar ist, da dieser Ausdruck klein gemacht werden kann, indem ein großes $a$ gewählt wird (das gleiche für jedes $\lambda$). Wenn jedoch $A = 0$, ist $\mathcal{F}$ nicht  gleichgradig integrierbar.

### Beispiel 1.27. 

Sei $(\Omega, \mathcal{A}, \mu)$ der Raum $\mathbb{R}$ mit der Borel-$\sigma$-Algebra und dem Lebesgue-Maß. Sei $(f_n)_{n \geq 1}$ die Folge von Funktionen definiert durch $f_n(x) = 1$ für $x \in [n, n+1]$ und $f_n(x) = 0$ sonst. Wir zeigen, dass diese Familie von Funktionen nicht  gleichgradig integrierbar ist. Betrachten wir, warum. Angenommen, sie wäre es, dann könnte man für $\epsilon > 0$ eine positive integrierbare Funktion $g_\epsilon$ finden, sodass
$$\sup_{n \in \mathbb{N}} \int_{|f_n| > g_\epsilon} |f_n| \, d\mu < \epsilon\tag{1.24}$$

Andererseits ist die Menge ${|f_n| > g_\epsilon}$ die Menge von $x \in [n, n+1]$, für die $0 \leq g_\epsilon(x) < 1$. Auf dieser Menge gilt $|f_n| = 1$, sodass

$$\int_{|f_n| > g_\epsilon} |f_n| \, d\mu = \mu\left( [n, n+1] \cap \{ x \in \mathbb{R} : g_\epsilon(x) < 1 \} \right) = 1 - \mu\left( [n, n+1] \cap \{ x \in \mathbb{R} : g_\epsilon(x) > 1 \} \right)$$

Bezeichnen wir mit $m_n$ das Lebesgue-Maß der Menge $[n, n+1] \cap { x \in \mathbb{R} : g_\epsilon(x) > 1 }$. Behauptung: d $m_n$ gegen null strebt, wenn $n \to \infty$. Tatsächlich gilt $\int g , d\mu > \sum_{n > 0} m_n$, und da $g$ per Annahme integrierbar ist, ist die Reihe konvergent. Folglich: Für beliebiges $\epsilon > 0$ können wir $n$ groß genug wählen, sodass $\int_{|f_n| > g_\epsilon} |f_n| , d\mu$ beliebig nahe an $1$ liegt, was ([[1.24]]) widerspricht.
