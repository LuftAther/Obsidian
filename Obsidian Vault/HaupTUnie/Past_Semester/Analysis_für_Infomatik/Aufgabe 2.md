## Grenzwert bestimmen

### Aufgabenstellung:
Untersuchen Sie die Folge $(a_n)_{n \in \mathbb{N}}$ auf Konvergenz und bestimmen Sie gegebenenfalls den Grenzwert, indem Sie zwei geeignete Folgen $(b_n)_{n \in \mathbb{N}}, (c_n)_{n \in \mathbb{N}}$ mit $b_n \leq a_n \leq c_n$ finden.

$$
a_n = \frac{n^{3/2}}{\sqrt{2n^5 + 1}} + \frac{n^{3/2}}{\sqrt{2n^5 + 2}} + \cdots + \frac{n^{3/2}}{\sqrt{2n^5 + n}}
$$

---

### Definitionen:
- Seien $(a_n)_{n \geq 0}$ eine Folge reeller Zahlen und $n_0 < n_1 < n_2 < \dotsc$ natürliche Zahlen. Dann nennt man die Folge $(a_{n_m})_{m \in \mathbb{N}} = (a_{n_0}, a_{n_1}, a_{n_2}, \dotsc)$ eine **Teilfolge** von $(a_n)_{n \geq 0}$.
$$
\forall \varepsilon > 0 \; \exists N(\varepsilon) \in \mathbb{N} \; \forall n > N(\varepsilon) : |a_n - a| < \varepsilon
$$  
- Eine Folge $(a_n)_{n \geq 0}$ heißt **konvergent**, falls sie einen Grenzwert $a$ besitzt. In diesem Fall konvergiert die Folge gegen $a$, und man schreibt  
$$
\lim_{n \to \infty} a_n = a \quad \text{oder} \quad a_n \to a.
$$
### Sandwich Kriterium:
Seien $(a_n)_{n \geq 0}$ und $(b_n)_{n \geq 0}$ konvergente Folgen, deren Grenzwerte übereinstimmen, also  $$
\lim_{n \to \infty} a_n = \lim_{n \to \infty} b_n = a.
$$  Sei $(c_n)_{n \geq 0}$ eine Folge mit  
$$
a_n \leq c_n \leq b_n \quad \text{für fast alle } n \in \mathbb{N}.
$$
Dann folgt die Konvergenz von $(c_n)_{n \geq 0}$, und es gilt:  
$$
\lim_{n \to \infty} c_n = a.
$$
---

### Vorarbeit (Abschätzung des Grenzwerts)

Die Folge $a_n$ ist eine Summe aus $n$ Termen der Form
$$
\frac{n^{3/2}}{\sqrt{2n^5 + k}} \quad \text{für } k = 1, \dotsc, n.
$$
#### **Untere Schranke:**
Da $k \leq n$, gilt:
$$
\sqrt{2n^5 + k} \leq \sqrt{2n^5 + n} \Rightarrow \frac{n^{3/2}}{\sqrt{2n^5 + k}} \geq \frac{n^{3/2}}{\sqrt{2n^5 + n}}.
$$

Somit gilt für die Summe:
$$
a_n \geq n \cdot \frac{n^{3/2}}{\sqrt{2n^5 + n}} = \frac{n^{5/2}}{\sqrt{2n^5 + n}}.
$$

#### **Obere Schranke:**
Ebenso gilt:
$$
\sqrt{2n^5 + k} \geq \sqrt{2n^5 + 1} \Rightarrow \frac{n^{3/2}}{\sqrt{2n^5 + k}} \leq \frac{n^{3/2}}{\sqrt{2n^5 + 1}}.
$$

Daher:
$$
a_n \leq n \cdot \frac{n^{3/2}}{\sqrt{2n^5 + 1}} = \frac{n^{5/2}}{\sqrt{2n^5 + 1}}.
$$

---

### Grenzwert der Schranken

Berechne den Grenzwert der unteren Schranke:
$$
\frac{n^{5/2}}{\sqrt{2n^5 + n}} = \frac{n^{5/2}}{n^{5/2} \cdot \sqrt{2 + \frac{1}{n^4}}}
= \frac{1}{\sqrt{2 + \frac{1}{n^4}}} \underset{\lim_{ n \to \infty } }\to \frac{1}{\sqrt{2}}.
$$

Berechne den Grenzwert der oberen Schranke:
$$
\frac{n^{5/2}}{\sqrt{2n^5 + 1}} = \frac{n^{5/2}}{n^{5/2} \cdot \sqrt{2 + \frac{1}{n^5}}}
= \frac{1}{\sqrt{2 + \frac{1}{n^5}}} \underset{\lim_{ n \to \infty } }\to \frac{1}{\sqrt{2}}.
$$
Damit können wir das Sandwich-Theorem (vgl. S 164 Satz 4.22 im Buch) anwenden und es gilt:
$$
\frac{1}{\sqrt{2 + \frac{1}{n^4}}} \leq a_n \leq \frac{1}{\sqrt{2 + \frac{1}{n^5}}}
$$

beide Schranken konvergieren gegen denselben Wert damit, folgt mit dem **Sandwich-Kriterium**:

$$
\lim_{n \to \infty} a_n = \frac{1}{\sqrt{2}}.
$$
$\square$
