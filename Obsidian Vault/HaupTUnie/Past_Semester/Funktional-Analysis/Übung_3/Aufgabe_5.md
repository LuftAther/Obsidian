Zeigen Sie für Banachräume $X, Y$, dass $f : D \to \mathcal{L}_b(X, Y)$ genau dann holomorph ist, wenn
$$
D \ni z \mapsto f(z)(x) \in Y
$$
für alle $x \in X$ holomorph ist.
**Hinweis:**  
Verwenden Sie die (nicht zu beweisende) Tatsache, dass $g : D \to Z$ (Z Banachraum) genau dann holomorph ist, wenn $g$ analytisch ist, also wenn es zu jedem $w \in D$ einen $r > 0$ und $b_n \in Z$, $n \in \mathbb{N} \cup \{0\}$, derart gibt, dass
$$
g(z) = \sum_{n=0}^\infty (z - w)^n b_n
\quad \text{für alle } z \in U_r^D(w),
$$
wobei der Konvergenzradius der Potenzreihe $\sum_{n=0}^\infty z^n b_n$ größer oder gleich $r$ ist.

Wenden Sie das vorherige Beispiel auf $Z = Y$ und $Z = \mathcal{L}_b(X, Y)$ an, wobei nachzuweisen ist, dass für $f : D \to \mathcal{L}_b(X, Y)$ die entsprechenden $b_n$ tatsächlich in $\mathcal{L}_b(X, Y)$ liegen.

Dafür könnte die **Cauchysche Integralformel** in Kombination mit dem **Satz von der gleichmäßigen Beschränktheit** dienen.

---
### Holomorph "$\Rightarrow$" $D \ni z \mapsto f(z)(x) \in Y \forall x \in X$

$f' : \mathbb{D} \to \mathcal{L}(X, Y)$ holomorph  
Beispiel: $\mathcal{L}^b(X, Y) \to Y : A \mapsto Ax$ linear und stetig

$$
\lim_{z \to z_0} \frac{f(z)x - f(z_0)x}{z - z_0}
= \left( \lim_{z \to z_0} \frac{f(z) - f(z_0)}{z - z_0} \right) x
= f'(z_0)x \quad \text{wegen Stetigkeit}
$$

---

### Holomorph "$\Leftarrow$" $D \ni z \mapsto f(z)(x) \in Y \forall x \in X$

$f_x : \mathbb{D} \to Y : z \mapsto f(z)x$ holomorph für alle $x \in X$

**Wissen:**  
Sei $w \in \mathbb{D}$ beliebig, dann gibt es $(b_n^{(x)})_{n \in \mathbb{N}} \in Y^\mathbb{N}$, $r > 0$  mit
$$
f(z)x = \sum_{n=0}^\infty (z - w)^n b_n(x) \quad \text{für alle } z \in U_r^\mathbb{C}(w)
$$

**Wir wollen zeigen,** dass $b_n \in \mathcal{L}_b(X, Y)$ für alle $x \in X, n \in \mathbb{N}$

---

- **Linearität:**

$$
b_n(\alpha x + \beta y)
= \frac{1}{n!} \left. \frac{d^n}{dz^n} \right|_{z = w} f(z)(\alpha x + \beta y)
= \frac{1}{n!} \left. \frac{d^n}{dz^n} \right|_{z = w} \left( \alpha f(z)x + \beta f(z)y \right)
$$

$$
= \alpha \cdot \frac{1}{n!} \left. \frac{d^n}{dz^n} \right|_{z = w} f(z)x 
+ \beta \cdot \frac{1}{n!} \left. \frac{d^n}{dz^n} \right|_{z = w} f(z)y
= \alpha b_n(x) + \beta b_n(y)
$$
---
- **Beschränktheit** (Verwenden der Cauchy-Formel für höhere Ableitungen)  
  (*Korollar 11.6.16, Fundamentalanalyse*)

Daher:
$$
b_n(x) = \frac{1}{n!} \left. \frac{d^n}{dz^n} \right|_{z = w} f(z)x
= \frac{1}{n!} f^{(n)}(w)x
= \frac{1}{2\pi i} \int_\gamma \frac{f(\zeta)x}{(\zeta - w)^{n+1}}\, d\zeta
$$

Sei $\|x\|_X = 1$

Dann:
$$
\|b_n(x)\|_Y \leq \frac{1}{2\pi} \int_\gamma \frac{\|f(\zeta)x\|_Y}{|\zeta - w|^{n+1}}\, |d\zeta|
\overset{\bigstar}[\leq] \frac{1}{2\pi} \int_\gamma \frac{M}{r^{n+1}}\, |d\zeta| = \frac{M}{r^{n+1}}
$$

Dabei ist:
$$
\gamma(t) = w + r \cdot \exp(it)
$$
$$
\begin{split}
&f(z)x \text{ holomorph } \\
&\Rightarrow \|f(z)x\|_Y \text{ stetig} \text{ und } \gamma([0, 2\pi]) \text{ kompakt } \\
&\Rightarrow \|f(z)x\|_Y \leq M \quad \text{auf } \gamma([0, 2\pi])\end{split} $\tag{$\bigstar$}
$$
---

Mit Aufgabe 4 folgt nun aus
$$
f(z)x = \sum_{n=0}^\infty (w - z)^n b_n(x)
\quad \text{(im Konvergenzradius $r$)} 
$$
und $b_n \in \mathcal{L}^b(X, Y)$, dass
$$
\sum_{n=0}^\infty (w - z)^n b_n
\quad \text{(z. B. im Konvergenzradius $\frac{r}{2}$)} 
$$
bezüglich Abbildungsnorm konvergiert.

Sei:
$$
R_n := \sum_{k=0}^n (w - z)^k b_k
$$

**Wir Wissen:**  
$R_n \to R \in \mathcal{L}_b(X, Y)$ bezüglich Abbildungsnorm  (da $\mathcal{L}_b(X, Y)$ abgeschlossen)

Seien $x \in X, \varepsilon > 0$ beliebig.  ⇒ $\exists N \in \mathbb{N}$ so dass für alle $n \geq N$:
$$
\|R_n x - R x\|_Y \leq \varepsilon \|x\|_X
$$

Somit auch:
$$
\lim_{n \to \infty} R_n x = R x
$$

Somit haben wir eine Potenzreihe für $f(z)$:
$$
f(z)x = \sum_{n=0}^\infty (w - z)^n b_n(x)
= \left( \sum_{n=0}^\infty (w - z)^n b_n \right)(x)
$$

gefunden, womit $f(z)$ **holomorph** ist.

----
## Wichtige Begriffe und Definitionen

---

- **Holomorphie in Banachräumen:**  
$f: D \to Z$ (Banachraum $Z$) heißt **holomorph**, wenn
$$
\lim_{z \to z_0} \frac{f(z) - f(z_0)}{z - z_0} \in Z
$$
existiert (Fréchet-Differenzierbarkeit).

- **Analytizität:**  
$f$ ist **analytisch**, wenn es für jedes $w \in D$ einen $r > 0$ und $b_n \in Z$ gibt mit
$$
f(z) = \sum_{n=0}^\infty (z - w)^n b_n \quad \text{für } z \in U_r^D(w)
$$
(normkonvergente Potenzreihe).
![[Pasted image 20250410225113.png]]

- **Satz:**  
$f$ ist holomorph $\Leftrightarrow$ $f$ ist analytisch.
![[Pasted image 20250410225346.png]]


- **Operatorauswertung:**  
Für $f: D \to \mathcal{L}_b(X, Y)$ gilt: $f(z)(x) \in Y$.
**Ziel:**  
$$
f: D \to \mathcal{L}_b(X, Y) \text{ ist holomorph } 
\Leftrightarrow f(z)(x) \text{ ist holomorph für alle } x \in X
$$



- **Cauchysche Integralformel (für Ableitungen):**
$$
f^{(n)}(w) = \frac{n!}{2\pi i} \int_\gamma \frac{f(\zeta)}{(\zeta - w)^{n+1}}\, d\zeta
$$
![[Pasted image 20250410224950.png]]



- **Satz von der gleichmäßigen Beschränktheit:**  
Aus $\sup_n \|T_n x\| < \infty$ für alle $x$ folgt $\sup_n \|T_n\| < \infty$.

**Zusammenfassung:**

| Begriff         | Bedeutung                               |
|----------------|------------------------------------------|
| $f(z)(x)$       | Operator auf Vektor                     |
| holomorph $f$   | stark differenzierbar in Operatornorm   |
| $b_n \in \mathcal{L}_b(X, Y)$ | Operator-Potenzreihen-Koeffizienten |

![[Pasted image 20250410224833.png]]