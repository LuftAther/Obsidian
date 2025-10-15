## Grenzwert bestimmen

### Aufgabenstellung:
Bestimmen Sie den Grenzwert der Folge $a_n := \sqrt{n^2 + 3n} - n$, indem Sie zu $\varepsilon > 0$ ein $N(\varepsilon)$ angeben.

---

### Definitionen:
- $\varepsilon$-**Umgebung** von $a$: $U_{\varepsilon}(a) = (a - \varepsilon, a + \varepsilon) = \{x \in \mathbb{R} \mid |x - a| < \varepsilon\}$
- Eine reelle Zahl $a$ heißt **Grenzwert** (oder **Limes**) der Folge $(a_n)_{n \geq 0}$, falls in jeder $\varepsilon$-Umgebung von $a$ fast alle Folgenglieder $a_n$ liegen, d. h., falls  
$$
\forall \varepsilon > 0 \; \exists N(\varepsilon) \in \mathbb{N} \; \forall n > N(\varepsilon) : |a_n - a| < \varepsilon
$$
- Eine Folge $(a_n)_{n \geq 0}$ heißt **konvergent**, falls sie einen Grenzwert $a$ besitzt. In diesem Fall konvergiert die Folge gegen $a$, und man schreibt  
$$
\lim_{n \to \infty} a_n = a \quad \text{oder} \quad a_n \to a.
$$

---

### Vorarbeit (Grenzwert bestimmen)

$$
\begin{split}
a_n &= \sqrt{n^{2} + 3n} - n = \sqrt{n^{2} + 3n} - n \cdot \underbrace{ \frac{\sqrt{n^{2} + 3n} + n}{\sqrt{n^{2} + 3n} + n} }_{= 1} \\
&= \frac{(\sqrt{n^2 + 3n} - n)(\sqrt{n^2 + 3n} + n)}{\sqrt{n^2 + 3n} + n}
= \frac{n^2 + 3n - n^2}{\sqrt{n^2 + 3n} + n}
= \frac{3n}{\sqrt{n^2 + 3n} + n}\\
&= \frac{3n}{\sqrt{n^{2}(1 + \frac{3}{n})} + n}
= \frac{3n}{n(\sqrt{1 + \frac{3}{n}} + 1)}
= \frac{3}{\sqrt{1 + \frac{3}{n}} + 1}
\end{split}
$$

Betrachten wir nun den Limes der Folge, so erhalten wir mit $\lim_{n \to \infty} \frac{1}{n} = 0$:

$$
a_n = \frac{3}{\sqrt{1 + \frac{3}{n}} + 1}
\quad \Rightarrow \quad
\lim_{n \to \infty} a_n = \frac{3}{2}
$$

---

### Beweis

Wir setzen in die Definition für den Grenzwert ein:

$$
\begin{split}
|a_n - \frac{3}{2}|
&= \left| \frac{3n}{\sqrt{n^2 + 3n} + n} - \frac{3}{2} \right|
= \left| \frac{3(\sqrt{n^2 + 3n} - n)}{2(\sqrt{n^2 + 3n} + n)} \right| \\
\text{Umschreiben mit } \sqrt{n^2 + 3n} - n = \frac{3n}{\sqrt{n^2 + 3n} + n}:\\
&= \left| a_n - \frac{3}{2} \right| = \frac{3}{2} \cdot \frac{3n}{(\sqrt{n^2 + 3n} + n)^2} \\
\text{Abschätzung ergibt:} \\
&\sqrt{n^2 + 3n} + n \geq 2n
\quad \Rightarrow \quad
(\sqrt{n^2 + 3n} + n)^2 \geq 4n^2 \\
&\Rightarrow |a_n - \frac{3}{2}| \leq \frac{9n}{2 \cdot 4n^2} = \frac{9}{8n}
\end{split}
$$

Damit gilt: Sei $\varepsilon > 0$. Wähle  
$$
N(\varepsilon) = \left\lceil \frac{9}{8\varepsilon} \right\rceil,
$$  
dann gilt für alle $n \geq N(\varepsilon)$:  
$$
|a_n - \frac{3}{2}| < \varepsilon.
$$
$\square$
