Sei $(\Omega, \mathcal{A}, \mu)$ ein Maßraum mit einem **endlichen Maß** $\mu$.  
Weiters sei $h : \Omega \to \mathbb{C}$ messbar.  
Sei
$$
\mathcal{D}_h := \left\{ f \in L^2(\Omega, \mathcal{A}, \mu, \mathbb{C}) : h \cdot f \in L^2(\Omega, \mathcal{A}, \mu, \mathbb{C}) \right\},
$$
und
$$
M_h : \mathcal{D}_h \to L^2(\Omega, \mathcal{A}, \mu, \mathbb{C}), \quad M_h f := h \cdot f
$$
Zeigen Sie zunächst, dass
$$
\left\{ (f, g) \in L^2(\Omega, \mathcal{A}, \mu, \mathbb{C}) \times L^2(\Omega, \mathcal{A}, \mu, \mathbb{C}) : g = h \cdot f \right\}
$$
den **Graphen** von $M_h$ angibt und dass dieser **abgeschlossen** ist in
$$
L^2(\Omega, \mathcal{A}, \mu, \mathbb{C}) \times L^2(\Omega, \mathcal{A}, \mu, \mathbb{C})
$$

**Hinweis:**  
Aus der $L^2$-Konvergenz folgt die Konvergenz einer Teilfolge **fast überall**,  
und Grenzwerte im Maß sind eindeutig **fast überall**.

**Zeigen** Sie anschließend, dass folgende Aussagen äquivalent sind:

(i) $h \in L^\infty(\Omega, \mathcal{A}, \mu, \mathbb{C})$
(ii) $\mathcal{D}_h = L^2(\Omega, \mathcal{A}, \mu, \mathbb{C})$ und $M_h$ ist **beschränkt**
(iii) $\mathcal{D}_h = L^2(\Omega, \mathcal{A}, \mu, \mathbb{C})$

---

**Hinweis:**  
Für „(¬i) ⇒ ¬(ii)“ betrachten Sie die Folge $(\mathbf{1}_{B_n})_{n \in \mathbb{N}}$,  
wobei die Mengen
$$
B_n := \{ x : |h(x)| \geq n \}
$$
aus $\mathcal{A}$ sind und positives und endliches Maß haben.


---

#### Hinweis

Sei $(f_n, g_n)$ eine Folge in $\text{graph}(M_h)$ mit
$$
f_n \to f \quad \text{in } L^2,\quad g_n \to g \quad \text{in } L^2
$$

Da nach Vorraussetzung $g_n = h f_n$, und $f,g \in L^2$ 
Wir müssen zeigen, dass $g = h\cdot f$

>Hinweis : $L^2$-Konvergenz impliziert, dass eine Teilfolge **fast überall** konvergiert und der Grenzwert **eindeutig bis auf Nullmenge** ist.

- $f_n \to f$ und $g_n \to g$ besitzen gemeinsame Teilfolgen $f_{n_k} \to f$, $g_{n_k} \to g$ fast überall
- Dann gilt auch: $g = \lim_{ n \to \infty } g_{n_k} = \lim_{ n \to \infty } h f_{n_k} \to h f$ fast überall

⇒ $g = h f \in L^2$, da Gleichheit fast überall auch Gleichheit in $L^2$ bedeutet

 Also: $(f, g) \in \operatorname{graph}(M_h)$  ⇒ $\operatorname{graph}(M_h)$ ist abgeschlossen

---

#### (ii) ⇒ (i)

Wir zeigen wie im **Hinweis** vorgschlagen durch Kontraposition ($\neg(i) \Rightarrow \neg(ii)$):  
Angenommen $h \notin L^\infty$ ⇒ $M_h$ ist unbeschränkt

$M_h$ ist **unbeschränkt**, wenn gilt:
$$
\forall C > 0\ \exists f \in \mathcal{D}_h\ :\ \frac{\|M_h f\|_{L^2}}{\|f\|_{L^2}} \geq C
$$
Äquivalent dazu:
$$
\sup_{f \in \mathcal{D}_h} \frac{\|M_h f\|_{L^2}}{\|f\|_{L^2}} = \infty
$$
Angenommen  $h \notin L^\infty$

Dann gilt:
$$
\forall n \in \mathbb{N}\ \exists A_n \in \mathcal{A} : \mu(A_n) > 0,\ \text{und}\ \forall x \in A_n : |h(x)| > n
$$
Betrachte eine konkreter ""Testfunktion""

$$
f_n := \mathbf{1}_{A_n} \in L^2(\mu)
\quad \text{(gilt, da $\mu$ endlich)}
$$

Dann ist $f_n \in \mathcal{D}_h$, da $h \cdot f_n = h$ auf $A_n$, also messbar

Berechne:
- $\|f_n\|_{L^2}^2 = \mu(A_n)$
- $\|M_h f_n\|_{L^2}^2 = \int_{A_n} |h(x)|^2 d\mu \geq n^2 \cdot \mu(A_n)$

$$\frac{\|M_h f_n\|_{L^2}^2}{\|f_n\|_{L^2}^2}
= \frac{n^2 \cdot \mu(A_n)}{\mu(A_n)} = n^2
\quad \Rightarrow \quad
\frac{\|M_h f_n\|_{L^2}}{\|f_n\|_{L^2}} = n$$
Damit haben wir ($\neg(i) \Rightarrow \neg(ii)$) ⇒ ((ii) ⇒ (i))


---
#### (i) ⇒ (ii)

Angenommen $h \in L^\infty$, dann ist $|h(x)| \leq C$ fast überall
Dann für alle $f \in L^2$:
$$
\|M_h f\|^2 = \int |h(x) f(x)|^2 d\mu \leq \|h\|_\infty^2 \cdot \|f\|^2
$$

⇒ $M_h$ ist **beschränkt**, also stetig  
⇒ $h f \in L^2$ für alle $f \in L^2$ ⇒ $\mathcal{D}_h = L^2$
Also: (i) ⇒ (ii)

---

#### (i) ⇒ (iii)

Wenn $h \in L^\infty$ dann ist $|h(x)|^2 < \infty$ fast überall ⇒ $h \in L^2$

Denn:
$$
\int |h(x)|^2 d\mu \leq \|h\|_\infty^2 \cdot \mu(\Omega) < \infty
$$

⇒ $h \in L^2$  
⇒ $h f \in L^2$ für $f \in L^2$ ⇒ $\mathcal{D}_h = L^2$
Also: (i) ⇒ (iii)

---

#### (iii) ⇒ (ii)

Wenn $\mathcal{D}_h = L^2$, zeigen wir, dass $M_h$ beschränkt ist.

Begründung:
- $L^2$ ist ein Banachraum
- $M_h$ ist linear und definiert auf ganz $L^2$
- Graph $M_h$ ist abgeschlossen (Teil 1)

⇒ Nach Satz **4.4.2**:  
Eine lineare Abbildung mit abgeschlossenem Graph und vollem Definitionsbereich im Banachraum ist stetig
Also: $M_h$ beschränkt

--- 

Die Aussagen: 
- (i) $h \in L^\infty$
- (ii) $\mathcal{D}_h = L^2$ und $M_h$ ist beschränkt
- (iii) $\mathcal{D}_h = L^2$
 sind äquivalent:
