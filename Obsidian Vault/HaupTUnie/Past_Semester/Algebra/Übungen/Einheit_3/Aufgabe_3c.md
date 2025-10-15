1. **Geben Sie ein Beispiel einer Gruppe** $G$ **an, in der die Menge der Torsionselemente** 
   (das sind Gruppenelemente $g \in G$, die $\exists n > 0 : g^n = 1$ erfüllen) 
   **keine Untergruppe ist.**  *(Hinweis: Aufgabe 2a)*

2. **Geben Sie ein Beispiel einer nichtabelschen Gruppe** $H$ **an, in der die Menge** $T$ **der Torsionselemente eine nichttriviale Untergruppe von** $H$ **ist.**  
   (Also $\lvert T \rvert > 1$ und $T \neq H$.)

3. **Zeigen Sie (für alle Gruppen): Wenn die Menge der Torsionselemente eine Untergruppe ist, dann ist sie sogar ein Normalteiler.**

---
### (1) Geben Sie ein Beispiel einer Gruppe $G$ an, in der die Menge der Torsionselemente keine Untergruppe sind

#### Betrachte nach Hinweis 2(a):
>- $s_k(z) := k - z$ .
>- $t_{k}(z) :=  k+z$
und die verknüpfung $\circ$ 
>-  $s_k \circ s_\ell(z) = s_k(s_\ell(z)) \Leftrightarrow  k - ( \ell - z ) = (k - \ell) + z$
>-  $t_k \circ t_\ell(z) = t_k(s_\ell(z)) \Leftrightarrow  k + ( \ell+ z )$
Alleine bilden$\langle \{s\} \rangle$ und $\langle \{t\} \rangle$ mit $\circ$ keine (Unendliche)gruppe

#### Behauptung:
Die Menge der Torsionselemente ist genau 

$$
\{t_0\} \cup \{s_k : k \in \mathbb{Z}\}
$$
#### Begründung:
Denn: $s_k^2(z) = s_k \circ s_k(z) = s_k(k - z) = k - k + z = t_0(z)$

Die Translationen haben unendliche Ordnung. Das bedeutet, dass sie nie nach einer endlichen Anzahl von Anwendungen zum Einselement werden.

Allerdings haben wir schon gesehen, dass $s_1, s_0 \in \{t_0\} \cup \{s_k : k \in \mathbb{Z}\}$ die **ganze Gruppe** erzeugen.

- Die Gruppe wird durch Elemente der Form $s_k$ und $t_0$ definiert, wobei $s_k$ eine Transformation darstellt, die $z$ auf $k - z$ abbildet.
- Die Menge der Torsionselemente besteht aus $t_0$ (vermutlich die Identität) und allen $s_k$ mit $k \in \mathbb{Z}$.
- Die Berechnung zeigt, dass $s_k^2$ immer auf $t_0$ zurückführt, daher sind diese Elemente Torsionselemente.
- Translationen hingegen haben unendliche Ordnung, da sie sich nicht durch eine endliche Anzahl von Anwendungen zu $t_0$ reduzieren lassen.
- Schlussendlich wird die gesamte Gruppe durch $s_1$ und $s_0$ erzeugt, was bedeutet, dass diese beiden Elemente ausreichen, um jedes Element der Gruppe zu schreiben.

Die Aussage zeigt also, dass die Menge der Torsionselemente **keine Untergruppe** ist, da sie die gesamte Gruppe erzeugt.

---

### (2) Geben Sie ein Beispiel einer nichtabelschen Gruppe $H$ an, in der die Menge $T$der Torsionselemente eine nichttriviale Untergruppe von $H$ **ist.**  

Betrachte die Gruppe $S_3 \times \mathbb{Z}$, versehen mit der Verknüpfung $\circ \times +$, und dem neutralen Element $(id, 0)$.

#### Bestimmung der Torsionselemente
- Alle Elemente von $S_3$ haben **endliche Ordnung** (maximal 3).
- Alle Elemente von $\mathbb{Z}$ außer $0$ haben **unendliche Ordnung**.

Daher sind die **Torsionselemente** dieser Gruppe genau diejenigen, deren zweite Komponente $0$ ist. Das bedeutet:

$$
T = \{(g, 0) \mid g \in S_3\}
$$

#### Eigenschaften
- Diese Menge $T$ bildet eine Untergruppe von $S_3 \times \mathbb{Z}$.
- Sie ist **isomorph** zu $S_3$, da $\mathbb{Z}$ ignoriert wird (bzw. fixiert auf 0 ist).
- Da $S_3$ **nicht-abelsch** ist, ist auch diese Gruppe nicht abelsch.

### Erklärung

- Wir betrachten die direkte Produktgruppe $S_3 \times \mathbb{Z}$, wobei die Elemente Paare $(g, n)$ sind mit $g \in S_3$ und $n \in \mathbb{Z}$.
- Da $\mathbb{Z}$ unendliche Ordnung besitzt, kann ein Element nur dann Torsionselement sein, wenn es bezüglich der $\mathbb{Z}$-Komponente null ist.
- Somit bildet die Menge $T = \{(g, 0) \mid g \in S_3\}$ eine Untergruppe, die isomorph zu $S_3$ ist und daher ebenfalls nicht abelsch.


### (3) Zeigen Sie (für alle Gruppen): Wenn die Menge der Torsionselemente eine Untergruppe ist, dann ist sie sogar ein Normalteiler.

Sei dazu also $T$ die Menge (Untergruppe!) der Torsionselemente, $t \in T$ und $x \in G$.  
Es gilt $t^n = 1$ für ein $n \in \mathbb{N}$.  

Wir zeigen nun, dass auch $(xtx^{-1})^n = 1$.  

Eine Hilfsaussage dafür ist, dass $(xtx^{-1})^n = xt^nx^{-1}$, was man mittels vollständiger Induktion beweist:

#### Induktionsbeweis

- **Induktionsanfang:** $n = 0$ :
$$(xtx^{-1})⁰ = 1$$
- **Induktionsbehauptung:**
$$\forall n \in \mathbb{N} : (xtx^{-1})^{n}= 1 $$
- **Induktionsschritt:** ($n \to n+1$) :
$$(xtx^{-1})^{n+1} = (xtx^{-1})^{n (xtx^{-1})}\overset{IB}{\Rightarrow} 1(xtx^{-1})$$
Damit ist die aussage bewiesen da $t \in T \Rightarrow t = 1$ damit haben wir $x1x^{-1} =1$

Weil mir mein Beweis zu sus ist: 
$$(xtx^{-1})^{n+1} = (xtx^{-1})^n (xtx^{-1}) = (xt^nx^{-1})(xtx^{-1}) = (xt^n)(x^{-1}x)(tx^{-1}) = xt^{n+1}x^{-1}.$$

Damit ist bewiesen:

$$
(xtx^{-1})^n = xt^nx^{-1}
$$

Da $t^n = 1 \implies xt^nx^{-1} = x \cdot 1 \cdot x^{-1} = 1.$

Damit ist gezeigt, dass:

$$
(xtx^{-1})^n = 1
$$

### Erklärung

- Es wird bewiesen, dass wenn $T$ eine Untergruppe der Torsionselemente ist, sie auch **normal** ist.
- Der Beweis verwendet vollständige Induktion, um zu zeigen, dass Konjugation eines Torsionselements ebenfalls ein Torsionselement ergibt.
- Die Normalität folgt daraus, dass Konjugation ein Torsionselement in ein weiteres Torsionselement umwandelt.
