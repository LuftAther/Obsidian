Seien $X$ ein normierter Raum, $M, N$ lineare Teilräume von $X$ derart, dass $X = M \oplus N$ (direkte Summe), und $P : X \to X$ die Projektion ($P^2 = P$), welche $M$ als Bild und $N$ als Kern hat. Weiters sei $M \times N$ mit der Maximumsnorm versehen.

**(1)** Zeigen Sie, dass aus $P \in \mathcal{L}_b(X)$ die Abgeschlossenheit von $M$ und $N$ folgt.

**(2)** Zeigen Sie, dass $J : M \times N \to X$ mit $J((x, y)) = x + y$ linear, bijektiv sowie beschränkt ist, und dass $J^{-1} : X \to M \times N$ genau dann beschränkt ist, wenn $P$ beschränkt ist.

**(3)** Zeigen Sie, dass im Fall eines Banachraumes $X$ die Beschränktheit von $P$ zur Abgeschlossenheit von $M$ und $N$ äquivalent ist.

----
### (1) Zeigen Sie, dass aus $P \in \mathcal{L}_b(X)$ die Abgeschlossenheit von $M$ und $N$ folgt.

Da $P \in \mathcal{L}_b(X)$ (also stetig), folgt:

- $\ker P = N$ ist abgeschlossen. 
- $\operatorname{ran} P = M = \ker(I - P)$

Nach Gleichung (3.2.2) gilt:
$$(I - P) \in \mathcal{L}_b(X) \Rightarrow M \text{ ist abgeschlossen}$$
Also  $P$ und $I - P$  sind stetig, und die Kerne stetiger Operatoren abgeschlossen sind, folgt, dass sowohl $M$ als auch $N$ abgeschlossen sind.

![[Pasted image 20250409194456.png]]

---

### (2) Zeigen Sie, dass $J : M \times N \to X$ mit $J((x, y)) = x + y$ linear, bijektiv sowie beschränkt ist, und dass $J^{-1} : X \to M \times N$ genau dann beschränkt ist, wenn $P$ beschränkt ist.

- #### Linearität:
Die Linearität von $J:M\times N \to X$ mit $J((x,y)) = x+y$ folgt direkt aus der linearität der addition.
- Betrachte $(x,y), (a,b) \in M \times N, \quad \lambda \in \mathbb{K}$ dann ist 
- $$ J((x,y)) + J((a,b)) = (x+y)+(a+b)  \overset{Ass}=  x+a+ y+b = J((a x+a,a y+ b))$$
- $$ \lambda J((x,y)) = \lambda (x+y) = (\lambda x + \lambda y) = J((\lambda x,\lambda y))$$
- #### Bijektivität

- **Injektiv:** Angenommen:
$$
J(x_1, y_1) = J(x_2, y_2)
\quad \Rightarrow \quad x_1 + y_1 = x_2 + y_2
$$

Dann:
$$
x_1 - x_2 = y_2 - y_1
$$

- Linke Seite ist in $M$, rechte in $N$
- Also liegt $x_1 - x_2 \in M \cap N$

Da $M \cap N = \{0\}$ folgt:
$$
x_1 - x_2 = 0 \quad \text{und} \quad y_2 - y_1 = 0
$$
also:
$$
x_1 = x_2,\quad y_1 = y_2
\Rightarrow (x_1, y_1) = (x_2, y_2)
$$
- **Surjektiv:**
- Sei $z \in X$ beliebig. Da $X = M \oplus N$, existieren **eindeutig** $x \in M$, $y \in N$ mit:
$$
z = x + y = J(x, y)
$$

Die Abbildung $J : M \times N \to X,\quad J(x, y) = x + y$ ist **bijektiv**, da:
- Jeder Vektor in $X$ eindeutig als Summe aus einem Vektor aus $M$ und einem aus $N$ geschrieben werden kann.
- Und weil $M \cap N = \{0\}$, ist diese Darstellung eindeutig.
- Da jeder Vektor $z \in X$ sich eindeutig als $z = x + y$ mit $x \in M$, $y \in N$ schreiben lässt, ist $J$ bijektiv.

- #### Beschränktheit

Die Maximumsnorm auf $M \times N$ ist definiert durch:
$$
\|(x, y)\| := \max\{\|x\|, \|y\|\}
$$

Dann gilt:
$$
\|x + y\| \leq \|x\| + \|y\| \leq 2 \cdot \max\{\|x\|, \|y\|\}
$$

Daher:
$$
\sup_{(x,y) \in M \times N} \frac{\|x + y\|}{\max\{\|x\|, \|y\|\}} \leq 2
$$

Also ist $J$ beschränkt.

---

#### $J^{-1}$ beschränkt $\Leftrightarrow$ $P$ beschränkt

Wir zeigen:
$$
J^{-1}(z) = (Pz, z - Pz) \quad \text{(also $J^{-1} = (P, I - P)$)}
$$

**Bemerkung:**
- Bild von $P$ ist $M$
- Bild von $I - P$ ist $N$
- Für $x + y \in X$, mit $x \in M$, $y \in N$:
  $$(P(x+y), (x+y) - P(x+y)) = (x, y)$$

**Folgerung:** Die Aussage folgt sofort, da $J^{-1}$ genau dann beschränkt ist, wenn $P$ beschränkt ist.
-   **$P$ beschränkt $\Rightarrow J^{-1}$ beschränkt**
	- $P$ ist beschränkt ⇒ auch $I - P$ ist beschränkt
	- $J^{-1}(z) = (Pz,\ (I - P)z)$ besteht aus zwei beschränkten linearen Abbildungen
	- Also ist $J^{-1}$ eine beschränkte lineare Abbildung von $X$ nach $M \times N$

-  **$J^{-1}$ beschränkt $\Rightarrow P$ beschränkt**
	- Angenommen $J^{-1}$ ist beschränkt.
	- Dann ist insbesondere die Abbildung $X \to M,\ z \mapsto Pz$ (erste Komponente von $J^{-1}$) beschränkt, da $Pz$ nur eine Projektion ist:

$$
Pz = \pi_1(J^{-1}(z))
$$
	- Dabei ist $\pi_1$ die Projektion auf die erste Komponente:

$$
\pi_1 : M \times N \to M,\quad \pi_1(x, y) = x
$$
	- $\pi_1$ ist beschränkt (sogar Lipschitz mit Konstante $1$ unter Maximumsnorm)
	- Zusammensetzung $\pi_1 \circ J^{-1} = P$ ⇒ beschränkt

---

### (3) Falls $X$ ein Banachraum ist

**Behauptung:** $P$ beschränkt $\Leftrightarrow M$ und $N$ abgeschlossen

- "$\Rightarrow$": Schon gezeigt in (1)

- "$\Leftarrow$": 
  - $X$ Banach, $M$, $N$ abgeschlossen $\Rightarrow$ $M \times N$ mit Maximumsnorm ist Banachraum
  - $J$ ist linear und bijektiv
  - Nach Satz 4.3.4 (offene Abbildung), ist $J^{-1}$ stetig
  - $J^{-1}$ stetig $\Rightarrow$ $P$ beschränkt

**Fazit:** Im Banachraum ist $P \in \mathcal{L}_b(X)$ genau dann, wenn $M$ und $N$ abgeschlossen sind.

![[Pasted image 20250409215719.png]]