Sei $K$ die Menge aller reellen Polynome mit Grad $\leq n$ (für festes $n$), für die $p'' \geq 0$ auf einem gegebenen Intervall $[a, b]$ gilt.
Man zeige, dass es zu einem $f \in L^2([a, b], \lambda)$ **genau ein** $p_0 \in K$ gibt, sodass
$$
\int_{[a, b]} |f - p_0|^2 \, d\lambda \leq \int_{[a, b]} |f - p|^2 \, d\lambda
$$
für alle $p \in K$.

**Hinweis:**  
Die Menge aller komplexen Polynome vom Grad $\leq n$ ist ein endlichdimensionaler Unterraum.  
Für $t \in [a, b]$ sind $p \mapsto p(t)$ sowie $p \mapsto p''(t)$ lineare Funktionale auf diesem Unterraum und daher stetig.

---
**Gegeben**:
- $K \subset L^2([a,b], \lambda)$ ist die Menge aller **reellen Polynome vom Grad $\leq n$**, für die $p''(t) \geq 0$ auf $[a, b]$ gilt
- $f \in L^2([a,b], \lambda)$ gegeben

**Ziel:** Zeige, dass es genau ein $p_0 \in K$ gibt mit
$$
\int_a^b |f(x) - p_0(x)|^2 \, d\lambda(x) \leq \int_a^b |f(x) - p(x)|^2 \, d\lambda(x) \quad \text{für alle } p \in K
$$

---
 Zunächst **betrachten** wir die Mänge K

- **Konvexität:**
Seien $p, q \in K$, also $p'', q'' \geq 0$.  
Für $\lambda \in [0,1]$ gilt:
$$
(\lambda p + (1 - \lambda) q)'' = \lambda p'' + (1 - \lambda) q'' \geq 0
$$
⇒ Konvexe Kombination liegt wieder in $K$ ⇒ $K$ ist **konvex**

- **Abgeschlossenheit:**
Die Menge der reellen Polynome vom Grad $\leq n$ ist endlichdimensional ⇒ **abgeschlossen** im Banachraum $L^2$  
Außerdem ist $p \mapsto p''$ stetig als lineares Funktional ⇒ $\{p : p'' \geq 0\}$ ist abgeschlossen ⇒ $K$ ist abgeschlossen

- **Nichtleere Menge:**
Beispielsweise ist $p(x) = x^2$ (für $n \geq 2$) in $K$ ⇒ $K \neq \emptyset$

![[Pasted image 20250410153207.png]]
Angewendet auf diese **Situtation**:
- $L^2([a,b], \lambda)$ ist Hilbertraum
- $K$ ist nichtleer, konvex und abgeschlossen

⇒ Es existiert **genau ein** $p_0 \in K$, sodass
$$
\|f - p_0\|_{L^2} = \inf_{p \in K} \|f - p\|_{L^2}
$$
Weiters erhalten wir über die Äquivalenz zur Integraldarstellung

Aus:
$$
\|f - p_0\|_{L^2}^2 = \sqrt{ \int_a^b |f(x) - p_0(x)|^2\, d\lambda(x)}
$$

⇒ Diese Größe ist **minimal**, also
$$
\int_a^b |f - p_0|^2 \, d\lambda \leq \int_a^b |f - p|^2 \, d\lambda \quad \text{für alle } p \in K
$$

Es existiert genau ein $p_0 \in K$, das $f$ im Sinne der $L^2$-Norm **am besten approximiert**, also die Abweichung $\|f - p_0\|_{L^2}$ minimiert. Dieses Minimum existiert wegen **Konvexität, Abgeschlossenheit und Nichtleerheit** von $K$ im Hilbertraum $L^2$.
