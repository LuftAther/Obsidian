Geben Sie eine Gruppe $H$ mit zwei Untergruppen $J,K$ und $J$ mit 

$$
K \subseteq J \subseteq I
$$
an, sodass 

$$
K \leq J \quad \text{und} \quad J \leq I, \quad \text{nicht aber} \quad K \leq I.
$$

*(Hinweis: Sei $G$ z.B. die alternierende Gruppe $A_4$ mit 12 Elementen, oder die 8-elementige Gruppe aller Drehungen und Spiegelungen, die ein festes Quadrat auf sich abbilden. Oder die 8-elementige Gruppe aller regulären $2 \times 2$-Matrizen, deren Einträge $0,0,1,1$ oder $0,0,1,-1$ oder $0,0,-1,1$ oder $0,0,-1,-1$ sind.)*

---
Wir betrachten folgende Matrizen:

$E = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}, \quad A = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}, \quad B = \begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}, \quad C = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix},$
$E^{-1} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}, \quad A^{-1} = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}, \quad B^{-1} = \begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}, \quad C^{-1} = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix},$
$D = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \quad F = \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}, \quad G = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}, \quad H = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$
$D^{-1} = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \quad F^{-1} = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}, \quad G^{-1} = \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}, \quad H^{-1} = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$

Und definieren daraus die Gruppe $I :=\{ E,A,B,C,D,E,F,G,H \}$
Die Gruppe ist versehen mit der **Matrixmultiplikation** und der **Einheitsmatrix** $E$ als neutralem Element.
(Damit haben wir also wirklich eine **Gruppe**)

Offensichtlich sind $J, K$ Untergrupprn wen wir sie wiefolgt definieren. 
- $J := \{E, A, B, C\}$  
- $K := \{E, A\}$  
**Behauptung:** $K$ ist Normalteiler von $J$
**Begründug:**  Wen wir alle möglichen Fälle mit allen möglichen Invertierebaren Matrizen durchgehen
**Beweis** durch ausrechnen

- $EAE^{-1} = EAE = A \in K$  
- $AAA^{-1} = AAA = A \in K$  
- $BAB^{-1} = BAB = A \in K$  
- $CAC^{-1} = CAC = A \in K$  
Da $A$ immer in $J$ bleibt, ist $J \leq U$.

**Behauptung:** $J$ ist Normalteiler von $I$
**Begründug:**  Wen wir alle möglichen Fälle mit allen möglichen Invertierebaren Matrizen durchgehen

| .                                                                 | $E = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$ | $A = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$ | $B = \begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}$ | $C = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$ |
|-------------------------------------------------------------------|---------------------------------------------------|-----------------------------------------------------|-----------------------------------------------------|-----------------------------------------------------|
| $E = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$                | $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$    | $\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$     | $\begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}$     | $\begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$    |
| $A = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$               | $\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$   | $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$      | $\begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$    | $\begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}$     |
| $B = \begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}$               | $\begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}$   | $\begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$    | $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$      | $\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$     |
| $C = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$              | $\begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$  | $\begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}$     | $\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$     | $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$      |
| $D = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$                | $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$    | $\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$     | $\begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}$     | $\begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$    |
| $F = \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}$               | $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$    | $\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$     | $\begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}$     | $\begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$    |
| $G = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$               | $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$    | $\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$     | $\begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}$     | $\begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$    |
| $H = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$              | $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$    | $\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$     | $\begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix}$     | $\begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$    |
Diese Tabelle zeigt, dass $J$ in der Gruppe $I$ invariant bleibt. und somit wirklich eine Untergruppe ist 
$J \not\leq I$

Nun zeigen wir, dass $J$ **kein Normalteiler** von $G$ ist. Wir prüfen, ob es Elemente $g \in G$ gibt, sodass

$$gAg^{-1} \notin K$$

Insbesondere betrachten wir Elemente außerhalb von $U$, z. B. $D$, $F$, $G$, $H$.

Beispielsweise:

- $DAD^{-1} = D \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} D^{-1} = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix} = B \notin K$.

Damit ist gezeigt, dass $J \not\leq I$.

---

Die Konstruktion zeigt ein konkretes Beispiel einer Gruppe mit Untergruppen $J$ und $K$, bei denen:
- $K \leq J$
- $J \leq G$
- $K \not\leq G$

Diese Struktur erfüllt genau die Anforderungen der Aufgabe.

