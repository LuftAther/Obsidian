# Aufgabenstellung:

Sei $S \subseteq \mathcal{P}(A)$. Eine Menge $S$ heißt **Unteruniversen-Menge**, wenn es eine Algebra $\mathcal{A}$ gibt (mit Universum $A$), sodass gilt: $B \in S \iff \text{es gibt eine Unteralgebra } \mathcal{B} \leq \mathcal{A} \text{ (mit Universum } B \text{)}$
Zum Beispiel ist  $\{ \{0\}, \{0,2\}, \{0,1,2,3\} \}$ eine Unteruniversen-Menge, bezogen auf
$(\mathbb{Z}_4, +, 0, -)$.

- 1. Zeige: $S = \{ \{0\}, \{0,1\}, \{0,2\}, \{0,2,3\}, \{0,1,2,3\} \}$ ist eine Unteruniversen-Menge.
- 2. Zeige: Für jedes $A$ (endlich oder unendlich) mit $\lvert A \rvert \geq 3$ gibt es eine Menge $S \subseteq \mathfrak{B}(A)$ mit $A \in S$, die keine Unteruniversen-Menge ist.
---

## Definitionen
- Unteralgebra:
![[Unteralgebra.png]]

### Aufgabe(1) 
Um zu zeigen das $S$ eine *Unteruniversen-Menge* ist müssen wir eine Algebra finden, die als unteralgebra $S$ beinhaltet.

- Zuerst Konstruieren wir eine (**kommutative**)Operation $\circ$:
	- $\omega(0,2) \mapsto 0 \circ 2 = 0$
	- $\omega(0,3) \mapsto 0 \circ 3 = 2$
	- $\omega(1,2) \mapsto 1 \circ 2 = 3$
	- $\omega(1,2) \mapsto 1 \circ 3  = 3$
	und für alle anderen ellemente gilt
	- $\omega(x,y) \mapsto x \circ y = 0$ 

Damit können wir genau die menge S erzeugen:
$$\begin{aligned}
\langle \{ 0 \} \rangle &= \{ 0 \}\\
\langle \{0,1\} \rangle &= \{0,1\} \\
\langle \{0,1,2\} \rangle &= \{0,1,2,3\} \\
\langle \{0,3\} \rangle &= \{0,2,3\}\\
\langle \{0,2\} \rangle &= \{0,2\}
\end{aligned}$$
- Als zweites vevolllständigen wir die *Untermengen* zu einer *Unteralgebra*
→ Betrachte nun:
$\mathcal{B}$ := Unteralgebren  

Wir brauchen:
- $0$ muss immer enthalten sein.
- S muss **alle Unteralgebren** enthalten.
- **Alles**, was man aus einem Erzeuger erzeugen kann, ist enthalten. 

---

### Aufgabe(2) 
Zeige: Für $|A| \geq 3$ gibt es eine Menge S,  $S \subseteq \mathfrak{B}(A)$ mit $A \in S$, sodass $S$ **keine Unteruniversen-Menge** ist

Die Mengen der Unteralgebren muss **schnittstabil** sein (nach Prop. 2.2.1.8).  
Also: $S$ muss $\cap$-stabil sein.
- Betrachte also für $|A| = 3$,$$A = \{\{ 0,2 \}, \{ 2,3 \} \{ 0,1,2 \}\},$$

→ Diese Menge ist **nicht** $\cap$-stabil.
	zb. $\{ 0,2 \} \cap \{ 2,3 \} = \{ 2 \} \not\subseteq A$

Also gibt es für $|A| \geq 3$ immer solche Mengen $S$, die **keine Unteruniversen-Mengen** sind.

![[Prop_2.2.1.8.png]]