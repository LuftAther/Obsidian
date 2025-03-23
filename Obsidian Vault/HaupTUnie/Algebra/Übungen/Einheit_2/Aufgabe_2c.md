Sei $A$ eine endliche Menge. Zeigen Sie: $S \subseteq \mathfrak{P}(A)$ ist eine Unteruniversenmenge, genau dann wenn $A \in S$ und $S$ abgeschlossen ist unter Schnitten 
(d.h. wann immer $U_1$ und $U_2$ in $S$ sind, dann auch $U_1 \cap U_2$).

**Hinweis**: Finden Sie für jedes $B \in \mathfrak{B}(A) \setminus S$ eine Operation $f_B$ (mit welcher Stelligkeit?), die verhindert, dass $B$ eine (Trägermenge einer) Unteralgebra von $\mathcal{A}$ ist. 
Dabei müssen Sie darauf achten, dass alle $C \in S$ abgeschlossen bezüglich $f_B$ sind.

---

Eine Menge $S \subseteq \mathcal{P}(A)$ ist eine **Unteruniversenmenge**  $\iff A \in S$ und $S$ ist **schnittstabil**, d.h.

#### ("$\Rightarrow$") 
folgt direkt aus der $\cap$-Stabilität von Unteralgebren (siehe Prop. 2.2.1.8)

![[Prop_2.2.1.8.png]]

##### ("$\Leftarrow$") 
Sei $B \in \mathfrak{P}(A) \setminus S$ beliebig.

Wir definieren $f_B$ mit Stelligkeit $\# B$:
- Sei $B = \{b_1, \dots, b_{\#B}\}$  
- Wähle $x \in A \setminus B$ beliebig  
> Die Wahl von $x$ ist das worauf es ankommt
- Definiere $f_B(b_1, \dots, b_{\#B}) := x$  (**1**)  
- Für alle anderen $(y_1, \dots, y_{\#B}) \in A^{\#B}$
- setze $f_B(y_1, \dots, y_{\#B}) := y_1$

Sei $C \in \mathfrak{P}(A)$ mit $B \not\subseteq C$, wobei $C$ abgeschlossen ist gegenüber $f_B$.

Wir zeigen, dass ein $x$ für (**1**) esisistiert, sodass alle $D \in S$ abgeschlossen gegenüber $f_B$ sind.

**Bemerkungen:**
- $\bigcap_{C \in S,\ B \in C} C \neq B$, weil $B \notin S$ und $S$ $\cap$-stabil ist.
- Aber $B \in \bigcap_{C \in S,\ B \in C}$, weswegen...
- $B \not\subseteq {\bigcap}_{C \in S, B \in C} C = B \dot{\cup} D$ für ein $D \in A$.

---
Somit: Falls $B \subseteq C$ für ein $C \in S$, dann $D \subseteq C$.

Wählen wir $x \in D$ für (**1**), so sind nun auch $C \in S$ mit $B \subseteq C$ bzgl. $f_B$ abgeschlossen ⇒  
Alle $C \in S$ abgeschlossen gegenüber $f_B$ und $B$ nicht.

Definiert man nun ein solches $f_B$ für alle $B \in \mathfrak{P}(A) \setminus S$ auf $A$,  
so ist eine Algebra mit Universumsmenge $S$ konstruiert. □

