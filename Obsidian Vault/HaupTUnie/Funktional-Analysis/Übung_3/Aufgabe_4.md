Seien $X, Y$ Banachräume über $\mathbb{C}$ und $R \in (0, +\infty)$.  
Weiters seien $A_n \in \mathcal{L}_b(X, Y)$, $n \in \mathbb{N}$, derart, dass die $Y$-wertige Potenzreihe $\sum_{n=0}^{\infty} z^n A_n(x)$ für alle $x \in X$ Konvergenzradius $\geq R$ hat.

**Zeigen Sie**, dass dann die $\mathcal{L}_b(X, Y)$-wertige Potenzreihe $\sum_{n=0}^{\infty} z^n A_n$ auch Konvergenzradius $\geq R$ hat.

**Hinweis:** Überlegen Sie zunächst, dass der Konvergenzradius von $\sum_{n=0}^{\infty} z^n b_n$ mit $b_n \in Z$, $n \in \mathbb{N} \cup \{0\}$, für einen beliebigen Banachraum $Z$ über $\mathbb{C}$ mit
$$
\sup\{s \in [0, +\infty) : \{s^n b_n : n \in \mathbb{N} \cup \{0\}\} \text{ ist beschränkt in } Z\}
$$
übereinstimmt. Satz von der gleichmäßigen Beschränktheit

---
 
Beweise von dem Hinweis:
Angenommen $|z| < R$ ⇒ $\sum z^n b_n$ ist **summierbar** ⇒ $\{ z^n b_n : n \in \mathbb{N} \}$ ist **beschränkt**  
⇒ also $|z| < R'$, d.h. $R \leq R'$

Umgekehrt: Sei $|z| < s < R'$, also $\left| \frac{z}{s} \right| < 1$, und  
angenommen $|s^n b_n| \leq C$ für alle $n \in \mathbb{N}$

Dann gilt:
$$
\sum_{n=0}^{\infty} z^n b_n
= \sum_{n=0}^{\infty} \left( \frac{z}{s} \right)^n s^n b_n
$$
Da $\left| \frac{z}{s} \right| < 1$ und $\{ s^n b_n \}$ beschränkt, ist die Reihe absolut konvergent:
$$
\sum_{n=0}^{\infty} \left| \frac{z}{s} \right|^n \cdot \|s^n b_n\| \leq \sum_{n=0}^{\infty} \left( \frac{|z|}{s} \right)^n C < \infty
$$

⇒ $\sum z^n b_n$ konvergiert ⇒ $|z| < R \Rightarrow R' \leq R$

Daher: $R = R'$

Der **Konvergenzradius** einer Potenzreihe in einem Banachraum $Z$ entspricht genau dem Supremum der $s > 0$, für die die Folge $\{s^n b_n\}$ beschränkt ist **Satz von der gleichmäßigen Beschränktheit.**

---
 Anwendung des Hinweises 

Sei $R$ wie in der Angabe oben, und Angenommen $|z| < R$.  
Setze $\tilde{R}$ als den Konvergenzradius der $\mathcal{L}_b(X, Y)$-wertigen Reihe $\sum_{n=0}^{\infty} z^n A_n$.

Nach Voraussetzung konvergiert
$$
\sum_{n=0}^{\infty} z^n A_n(x) \in Y \quad \text{für alle } x \in X
$$

⇒ Für alle $x$:  
$$
\{ z^n A_n(x) : n \in \mathbb{N} \} \subset Y \text{ ist beschränkt}
$$

Das heißt:  
Die Familie $\{ z^n A_n \}$ ist **punktweise beschränkt** auf $X$, also:
$$
\sup_n \|z^n A_n(x)\| < \infty \quad \text{für alle } x \in X
$$
Anwendung von Korollar 4.2.2

Da $X$ ein Banachraum ist, und $\{z^n A_n\}$ punktweise beschränkt ist, folgt aus **Korollar 4.2.2**:
![[Pasted image 20250410154459.png]]  

Die Familie $\{ z^n A_n \}$ ist **gleichmäßig beschränkt**, also
 $$
\sup_n \|z^n A_n\| < \infty
 $$

Dann gilt für die Konvergenz in der Operatornorm

Da $z^n A_n \in \mathcal{L}_b(X, Y)$ gleichmäßig beschränkt ist,  
und für jedes $x$ die Reihe $\sum z^n A_n(x)$ konvergiert ⇒  
konvergiert auch die Reihe $\sum z^n A_n$ **in Operatornorm** (normierte Konvergenz in $\mathcal{L}_b(X, Y)$)

Damit 

Die Potenzreihe $\sum_{n=0}^{\infty} z^n A_n$ konvergiert **in Operatornorm** für $|z| < R$,  
also ist ihr **Konvergenzradius** in $\mathcal{L}_b(X, Y)$ mindestens $R$:

$$
\tilde{R} \geq R
$$


Dies folgt durch Kombination von:
- Punktweiser Konvergenz
- Korollar 4.2.2 (gleichmäßige Beschränktheit)
- Anwendung des allgemeinen Potenzreihen-Kriteriums im Banachraum
