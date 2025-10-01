
Für Mengen $T, Tom\{T\} \subseteq X 	imes Y$ ist die Teilmenge $T^{-1}$ von $Y 	imes X$ definiert durch
$$
(a, x) \in T^{-1} \Leftrightarrow (x, a) \in T
$$
und wird als Inverse von $T$ bezeichnet.

Zeigen Sie für Vektorräume $X, Y$ (wenn nicht anders angegeben) bzw. für normierte Räume $X, Y$ oder $C^*$-Räume:

- $T$ spannt genau dann einen linearen Unterraum von $X 	imes Y$ auf, wenn $T^{-1}$ ein linearer Unterraum von $Y 	imes X$ ist.
- Für einen linearen Unterraum $T \subseteq X 	imes Y$ ist die lineare, auf $T$ genau dann eine lineare Abbildung von $x \mapsto f(x)$ darstellbar, wenn aus $(x, 0) \in T$ immer $x = 0$ folgt.
- Ist $T$ gegeben, eine beschränkte lineare Abbildung von $X 	o Y$, so ist $T = \{ (x, Tx) \}$. Dann ist auch $T^{-1}$ die eindeutig bestimmte lineare Abbildung von $Y 	o X$, die in diesem Fall $y \mapsto T^{-1} y$ erfüllt (sofern $T$ bijektiv ist).
- In dem Fall, dass $T$ eine beschränkte lineare Abbildung von $X 	o Y$ ist, ist $T^{\circ} := \{ (a,b) \mid (b,a) \in T \} = T^{-1}$ eine beschränkte lineare Abbildung von $Y 	o X$. Damit wird $T^{\circ}$ für den Abschluss von $T$ in $X 	imes Y$ stetig, wenn $X, Y$ mit der Maximumsnorm versehen sind.

---

### Beweisskizze

- $T \subseteq X 	imes Y$ linearer Unterraum $\Leftrightarrow T^{-1} \subseteq Y 	imes X$ linearer Unterraum.
- Beispiel: $(a,b), (c,d) \in T \Rightarrow (b,a), (d,c) \in T^{-1} \Rightarrow (b + d, a + c) \in T^{-1}$
- Gerade additive Rückrichtung.

---

### Graph als linearer Unterraum

- Sei $T = \{ (x, Tx) \in X 	imes Y \}$, dann ist $T \subseteq X 	imes Y$ linear.
- Dann ist $T^{-1} = \{ (Tx, x) \in Y 	imes X \}$

---

### Darstellung als Graph einer linearen Abbildung

Wenn $T$ ein linearer Unterraum ist, dann:
- Die Projektion $(T\circ X)$ ist injektiv $\Leftrightarrow \forall (x, 0) \in T \Rightarrow x=0$
- Dann existiert eine lineare Abbildung $f : X \circ Y$ mit $T = \{ (x, f(x)) \}$

---

### Normierte Räume / Beschränktheit

- $T \subseteq X 	imes Y$ linear, beschränkte Abbildung $\Rightarrow \exists c > 0 : orall (x,y) \in T : \|y\| \leq c \|x\|$
- Umkehrung: Aus solcher Schranke folgt Stetigkeit.
- Sei $(x_n, y_n) \in T$, $\|x_n\| = 1$, dann $\|y_n\| \leq c$ $\Rightarrow$ gleichmäßig beschränkt.

---

### Inverse Abbildung

- Falls $T$ ein Homöomorphismus ist, ist auch $T^{-1}$ stetig.
- Beispiel: $f : X 	o Y$, $T = \{ (x, f(x)) \} \Rightarrow f^{-1}$ stetig $\Leftrightarrow T^{-1}$ ist der Graph von $f^{-1}$

---

**Fazit**: Eigenschaften wie Linearität, Stetigkeit und Invertierbarkeit spiegeln sich zwischen einer Abbildung $T$ und ihrem Graphen sowie dessen Inversen $T^{-1}$ wider.
