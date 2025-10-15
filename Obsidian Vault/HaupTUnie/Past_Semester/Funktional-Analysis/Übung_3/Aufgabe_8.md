Sei $H = \mathbb{C}_s[t]$ die Menge aller komplexen Polynome vom Grad $\leq s$, versehen mit dem Skalarprodukt
$$
(p, q) := \int_1^{\infty} p(t) \overline{q(t)} \, dt
$$

**Zeigen Sie:** $(H, (\cdot, \cdot))$ ist ein **Hilbertraum**.

**Weiter**: Sei $w \in \mathbb{C}$ fest.  
Zeigen Sie, dass es ein $k_w \in \mathbb{C}_s[t]$ gibt, sodass
$$
p(w) = \int_1^{\infty} p(t) \overline{k_w(t)} \, dt \quad \text{für alle } p \in \mathbb{C}_s[t]
$$

---

- $(H, (\cdot,\cdot))$ ist ein Banachraum ⟺ $(H, (\cdot,\cdot))$ ist vollständig
- $\dim H = n+1$

---

**Zz:** $(p, q) := \int_1^{\infty} p(t)\overline{q(t)}\,dt$ ist ein Skalarprodukt

- (TP1): $(p, p) = \int_1^{\infty} |p(t)|^2\,dt \geq 0 \quad \forall p \in H \setminus \{0\}$

  $\Rightarrow \int_1^{\infty} |p(t)|^2\,dt > 0 \Rightarrow$ der gesamte Ausdruck ist größer $0$

- (TP2): $(\alpha x + \beta y, z) = \alpha(x, z) + \beta(y, z) \quad \forall x, y, z \in H$

  $\int_1^{\infty} (\alpha x(t) + \beta y(t)) \cdot \overline{z(t)}\,dt = \alpha \int_1^{\infty} x(t)\overline{z(t)}\,dt + \beta \int_1^{\infty} y(t)\overline{z(t)}\,dt = \alpha(x,z) + \beta(y,z)$

- (TP3): $(x, y) = \overline{(y, x)} \quad \forall x, y \in H$

  $\int_1^{\infty} x(t)\overline{y(t)}\,dt = \overline{\int_1^{\infty} y(t)\overline{x(t)}\,dt} = \overline{(y,x)}$

---

- $(x,x) = \int_1^{\infty} x(t)\overline{x(t)}\,dt = \int_1^{\infty} |x(t)|^2\,dt \geq 0$  
- Wir wissen, dass das Integral linear ist ⇒  

  $\Rightarrow \int_1^{\infty} \overline{x(t)} \cdot (\alpha y(t) + \beta z(t))\,dt = \alpha \int_1^{\infty} \overline{x(t)} y(t)\,dt + \beta \int_1^{\infty} \overline{x(t)} z(t)\,dt = \alpha(x,y) + \beta(x,z)$

- $(x, z+y) = (x,z) + (x,y)$

---

- Um zu ziegen das H vollständig ist zeigen  wir, dass **jede Cauchy-Folge in $H$ konvergiert** bzgl. der durch das Skalarprodukt induzierten Norm:
$$
\|p\| := \sqrt{(p, p)} = \left( \int_1^{\infty} |p(t)|^2 dt \right)^{1/2}
$$
Sei $(p_n)$ eine Cauchy-Folge in $H$ bzgl. $\|\cdot\|$.
Dann gilt:
$$
\forall \varepsilon > 0\ \exists N \in \mathbb{N}\ \forall n, m \geq N : \|p_n - p_m\| < \varepsilon
\quad \Leftrightarrow \quad
\int_1^{\infty} |p_n(t) - p_m(t)|^2 dt < \varepsilon
$$

Nun definieren wir eine Gewichtsfunktion:
$$
f(t) := e^{-t/2}, \quad t \in [0,1]
$$
Diese Funktion ist **stetig**, **positiv** und **beschränkt** auf dem Intervall $[0,1]$.
Nun betrachten wir die Abbildung:
$$
p \mapsto pf,\quad\text{also } pf(t) := p(t) \cdot f(t)
$$
Wir zeigen:  
$(p_n f)$ ist eine Cauchy-Folge in $L^2([0,1])$ mit dem Skalarprodukt
$$
\langle g, h \rangle_{L^2} := \int_1^{\infty} g(t)\overline{h(t)}\,dt
$$
Denn:
$$
\begin{split}
\|p_n f - p_m f\|_{L^2}^2
&= \int_1^{\infty} |p_n(t) - p_m(t)|^2 \cdot |f(t)|^2 dt\\
&= \int_1^{\infty} |p_n(t) - p_m(t)|^2 e^{-2t} dt
\leq \int_1^{\infty} |p_n(t) - p_m(t)|^2 dt < \varepsilon
\end{split}
$$
Da $L^2([0,1])$ vollständig ist, existiert ein Grenzwert $qf \in L^2([0,1])$ mit:
$$
p_n f \to qf \quad \text{in } L^2
$$

Da $f(t) \neq 0$ für alle $t$, gilt punktweise:
$$
p_n(t) \to q(t) := \frac{(p_n f)(t)}{f(t)} \in \mathbb{C}_s[t]
$$
(denn Grenzwert von Polynomen bleibt ein Polynom – endlichdimensionaler Raum!)

---

Berechne:
$$\begin{split}
\|p_n - q\|^2
= \int_1^{\infty} |p_n(t) - q(t)|^2 dt
&= \int_1^{\infty} \left| \frac{p_n(t)f(t) - q(t)f(t)}{f(t)} \right|^2 dt \\
&= \int_1^{\infty} \frac{|p_n f - q f|^2}{|f(t)|^2} dt
\end{split}$$

Da $f(t)$ beschränkt und $f(t) \geq c > 0$, folgt:
$$
\|p_n - q\| \to 0 \quad \text{in } L^2
$$

Die Folge $(p_n)$ konvergiert in $H$ bzgl. $\|\cdot\|$.  
Damit ist $H$ vollständig. Und wir haben gezeigt das

- $H = \mathbb{C}_s[t]$ mit dem $L^2$-Skalarprodukt ist ein Skalarproduktraum
- jede Cauchy-Folge $(p_n)$ in $H$ konvergiert
- also ist $H$ ein **Hilbertraum**
----
**Definition:**  
$e_w : H \to \mathbb{C},\quad p \mapsto p(w)$
$e_w$ ist ein lineares Funktional auf $H$
Da $H$ endlichdimensional ist, ist $e_w$ stetig  ⇒ $e_w \in H'$ (dem dualen Raum von $H$)
**Nach Proposition 3.2.5**  
gibt es ein $k_w \in H$  sodass:
$$
(p, k_w) = e_w(p) = p(w) \quad \text{für alle } p \in H
$$
![[Pasted image 20250410215703.png]]