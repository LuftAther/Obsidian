Sei $A$ eine endliche Menge. Zeigen Sie: $S \subseteq \mathfrak{P}(A)$ ist eine Unteruniversenmenge, genau dann wenn $A \in S$ und $S$ abgeschlossen ist unter Schnitten 
(d.h. wann immer $U_1$ und $U_2$ in $S$ sind, dann auch $U_1 \cap U_2$).

**Hinweis**: Finden Sie für jedes $B \in \mathfrak{B}(A) \setminus S$ eine Operation $f_B$ (mit welcher Stelligkeit?), die verhindert, dass $B$ eine (Trägermenge einer) Unteralgebra von $\mathcal{A}$ ist. 
Dabei müssen Sie darauf achten, dass alle $C \in S$ abgeschlossen bezüglich $f_B$ sind.

---

Eine Menge $S \subseteq \mathcal{P}(A)$ ist eine **Unteruniversenmenge**  $\iff A \in S$ und $S$ ist **schnittstabil**, d.h.

("⇒") folgt direkt aus der $\cap$-Stabilität von Unteralgebren (siehe Prop. 2.2.1.8)

![[Prop_2.2.1.8.png]]

("$\Leftarrow$")

Sei $B \in \mathfrak{P}(A) \setminus S$ beliebig.

Wir definieren $f_B$ mit Stelligkeit $\# B$:
- Sei $B = \{b_1, \dots, b_{\#B}\}$  
- Wähle $x \in A \setminus B$ beliebig  
- Definiere $f_B(b_1, \dots, b_{\#B}) := x$  (**1**)  
- Für alle anderen $(y_1, \dots, y_{\#B}) \in A^{\#B} \setminus \{(b_1, \dots, b_{\#B})\}$ setze $f_B(y_1, \dots, y_{\#B}) := y_1$

### Behauptung:
Alle $C \in S$ mit $B \not\subseteq C$ sind **abgeschlossen** bezüglich $f_B$  
und $B$ ist **nicht** abgeschlossen.

---

## Warum gilt das?

- Sei $C \in S$ mit $B \subseteq C$  
- Da $S$ schnittstabil, gilt $\bigcap_{C \in S,\ B \subseteq C} C \in S$
- Aber $x \notin B$, also auch $x \notin \bigcap C$

⇒ $f_B(b_1, \dots, b_{\#B}) = x \notin B$  
⇒ $B$ ist nicht abgeschlossen unter $f_B$

---

## Fazit:

Wählt man für jedes $B \in \mathcal{P}(A) \setminus S$ eine solche Operation $f_B$,  
so ist die resultierende Algebra (bestehend aus all diesen $f_B$) eine Algebra mit **Unteruniversenmenge genau $S$**. $\square$