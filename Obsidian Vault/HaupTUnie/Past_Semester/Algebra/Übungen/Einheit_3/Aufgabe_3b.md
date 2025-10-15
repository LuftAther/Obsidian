Wir betrachten $n \times n$ Matrizen $(n \geq 2)$ über den komplexen Zahlen. Sei $GL(n)$ die Gruppe aller invertierbaren Matrizen; $SL(n, K)$ die mit Determinante 1; $D(n)$ die regulären Diagonalmatrizen (d.h. nicht-Null Einträge nur auf der Diagonale); $U(n)$ die unitären $n \times n$-Matrizen. 

(D.h., Matrizen $U$ mit $U^H = U^{-1}$, wobei $U^H = \overline{U}^T$, transponiert und konjugiert komplex.) $SU(n) := U(n) \cap SL(n)$.

Welche der folgenden Untergruppen sind **Normalteiler**, und wie sieht im Fall eines Normalteilers der **Quotient** aus? Ist er zu einer Untergruppe von $\mathbb{C}^{\times}$ isomorph?

1. $SL(n, K) \leq GL(n, K)$
2. $D(n, K) \leq GL(n, K)$
3. $U(n) \leq GL(n, K)$
4. $D(n) \leq U(n)$
5. $SU(n) \leq U(n)$

---
### Definitonen:

- **Normalteiler:**  
   Eine Untergruppe $N$ einer Gruppe $G$ ist ein Normalteiler ($N \leq G$), wenn für jedes $g \in G$ und jedes $n \in N$ gilt:
   $$
   gng^{-1} \in N
   $$
   Das bedeutet, dass $N$ unter Konjugation durch Elemente von $G$ abgeschlossen ist.

- **Quotientengruppe:**  
   Für einen Normalteiler $N \leq G$ ist die Quotientengruppe $G/N$ definiert durch
   $$
   G/N = \{ gN \mid g \in G \}
   $$
   Die Gruppenoperation ist gegeben durch:
   $$
   (gN)(hN) = (gh)N
   $$

-  **Isomorphie zu einer Untergruppe von $\mathbb{C}^\times$:**  
   Prüfen, ob der Quotient $G/N$ zu einer Untergruppe der multiplikativen Gruppe $\mathbb{C}^\times$ isomorph ist.  
   $\mathbb{C}^\times = \mathbb{C} \setminus \{0\}$ mit der Multiplikation als Operation.

---
Wir überprüfen nun für jeden der fünf Fälle, ob die gegebene Untergruppe ein Normalteiler ist und wie der Quotient aussieht.

---

### (1)  $\operatorname{SL}(n, \mathbb{C}) \leq \operatorname{GL}(n)$

- **Definition:** $\operatorname{SL}(n, \mathbb{C}) = \{ A \in \operatorname{GL}(n) \mid \det(A) = 1 \}$.
- **Behauptung:** Ist $\operatorname{SL}(n, \mathbb{C})$ ist eine Normalteiler

#### Beweis:
Wähle ein belibige $P \in \operatorname{GL}(n)$, $P$ ist invertierbar. Betrachte weiters ein  $A \in \operatorname{SL}(n, \mathbb{C})$ nach dem Multiplikatinssatz für matritzen gilt:
$$
\det(PAP^{-1}) = \det(P) \det(A) \det(P^{-1}) = \det(P) \det(P)^{-1} \det(A) = \det(A) = 1
$$
$$
\Rightarrow PAP^{-1} \in SL(n,K)
$$

- $\operatorname{SL}(n, \mathbb{C})$ ist unter Konjugation abgeschlossen, also ein **Normalteiler**.

#### Betrachtung des Quotienten $\operatorname{GL}(n)/\operatorname{SL}(n, \mathbb{C})$

Als in anderen Worten die Menge aller Restklassen

Betrachte also:  $A \cdot \operatorname{SL}(n, \mathbb{C})$, wobei $A \in \operatorname{GL}(n, \mathbb{C})$.

> Zwei Elemente $A, B \in \operatorname{GL}(n, \mathbb{C})$ sind äquivalent, wenn  $\exists S \in \operatorname{SL}(n, \mathbb{C})$ , sodass:
$$
A \cdot B^{-1} = S
$$>
>	Das ist äquivalent zu:
$$
A \sim B \quad \Leftrightarrow \quad A = BS \quad \text{für ein } S \in \operatorname{SL}(n, \mathbb{C}).
$$>
#### Behauptung:
Die Faktorgruppe $\operatorname{GL}(n, \mathbb{C}) / \operatorname{SL}(n, \mathbb{C})$ ist *isomorph* zu $\mathbb{C}^\times$.
wobei wir behaupen dass
$$
\varphi: \operatorname{GL}(n,K / \operatorname{SL}(n, K) \to \mathbb{C}^\times, \quad \varphi(A \cdot \operatorname{SL}(n, K)) = \det(A)
$$
ein Isomorphismus ist.

#### Begründung:

-  $\varphi$ ist **wohldefiniert**, weil
  A$\det(A) = \det(B)$ für $A, B$ mit $A \cdot B^{-1} \in SL(n, K)$.

- $\varphi$ ist **Homomorphismus** 
  aufgrund des **Determinantenmultiplikationssatzes**. bzw. weil:
  $$
  \varphi(AB) = \det(AB) = \det(A) \det(B) = \varphi(A) \varphi(B)
  $$

- $\varphi$ ist **surjektiv**, da man durch Skalierung der EinheitsmatriA $I$ jede Zahl aus $\mathbb{C}^\times$ treffen kann:
  $$
  \det(\lambda I) = \lambda^n \in \mathbb{C}^\times
  $$

- $\varphi$ ist **Injektivität**, Angenommen, $\varphi(A) = \varphi(B)$ für $A, B \in \operatorname{GL}(n, \mathbb{C})$. Das bedeutet:
  $$
  \det(A) = \det(B)
  $$Betrachte nun $A \cdot B^{-1}$. Dann gilt:
  $$
  \det(A \cdot B^{-1}) = \frac{\det(A)}{\det(B)} = 1
  $$
Also ist $A \cdot B^{-1} \in \operatorname{SL}(n, \mathbb{C})$. Somit:
  $$
  A \sim B
  $$
##### Fazit:
$$
\operatorname{GL}(n, K) / \operatorname{SL}(n, K) \cong \mathbb{C}^\times
$$


---

### (2) $D(n) \leq \operatorname{GL}(n)$

- **Definition:** $D(n)$ sind die regulären Diagonalmatrizen mit $\det \neq 0$.
- **Behauptung:** $D(n)$ ein **Kein** Normalteiler von $\operatorname{GL}(n)$
#### Begrünfung:

Für eine Matrix $A \in \operatorname{GL}(n)$ und $D \in D(n)$ ist im Allgemeinen:
$$
ADA^{-1} \notin D(n)
$$
Da $A$ eine beliebige invertierbare Matrix ist, wird durch Konjugation eine Diagonalmatrix normalerweise in eine nicht-diagonale Matrix umgewandelt. Daher ist $D(n)$ **kein Normalteiler**.
#### Gegenbeispiel
Wir diagonalisisieren folgende Matrix:

$$
\begin{pmatrix} 2 & 1 \\ 0 & 3 \end{pmatrix} = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix} \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix}
$$

---

#### Überprüfung der Zugehörigkeit zu $D(n)$ und $\operatorname{GL}(n)$

- Die Matrix $\begin{pmatrix} 2 & 1 \\ 0 & 3 \end{pmatrix} \notin D(n, \mathbb{C})$ (da sie **nicht diagonal** ist).
- Die Matrix $\begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix} \in D(n, \mathbb{C})$ (da sie **diagonal** ist).
- Die Matrix $\begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \in \operatorname{GL}(n, \mathbb{C})$ (da **invertierbar**).
---

### (3) $U(n) \leq \operatorname{GL}(n)$

- **Definition:** $U(n)$ ist die Gruppe der **unitären Matrizen** mit $U^H = U^{-1}$.
- **Frage:** Ist $U(n)$ ein Normalteiler von $\operatorname{GL}(n)$?

#### Nachweis:

Für $A \in \operatorname{GL}(n)$ und $U \in U(n)$:
$$
AUA^{-1} \notin U(n)
$$
Im Allgemeinen wird die Konjugation durch $A$ eine unitäre Matrix nicht mehr unitär machen. Daher ist $U(n)$ **kein Normalteiler**.

#### Gegenbeispiel:
Betrachte die Matrix
 $$A = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \quad P = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}, \quad P^{-1} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} $$
 
 - $A \in U(n) \text{ da } A A^* = A^* A =\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$
 - Aber $P*A*P^{-1} \not\in U(n)$ da:
 $$B = P A P^{-1} = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix}$$
 und 
 $$\begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ -1 & 1 \end{pmatrix} = \begin{pmatrix} 2 & -1 \\ 0 & 1 \end{pmatrix}$$
  

---

### (4) $D(n) \leq U(n)$

- **Definition:** $D(n)$ ist die Gruppe der regulären Diagonalmatrizen.
- **Behauptung:** $D(n)$ ist kein Normalteiler von $U(n)$?

#### Begründung:

$D(n)$ erfüllt nicht die Bedinung eine Untergruppe zu sein.
- Gegenbeispiel für $n = 2$

Betrachten wir die folgende Matrix aus $D(2, \mathbb{C})$:

$$
A = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix}
$$

Berechne $A \cdot A$:

$$
A \cdot A = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 4 & 0 \\ 0 & 1 \end{pmatrix}
I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}
$$

Somit $A^H A \neq I$, ist $A \notin U(n)$. 

Das zeigt, dass $D(n)$ **nicht einmal eine Untergruppe** von $U(n)$ ist.  
Insbesondere ist es **kein Normalteiler**.

---

### (5) $\operatorname{SU}(n) \leq U(n)$

- **Definition:** $\operatorname{SU}(n)$ ist die Gruppe der **speziellen unitären Matrizen** mit $\det(U) = 1$.
- **Behauptung:** $\operatorname{SU}(n)$ ist ein **Normalteiler** von $U(n)$.

#### Begründung

1. **Untergruppe:**
   - $\operatorname{SU}(n)$ ist per Definition der Schnitt zweier Untergruppen: $U(n)$ und $\operatorname{SL}(n, \mathbb{C})$.  
   - Da der Schnitt zweier Untergruppen ebenfalls eine Untergruppe ist, ist $\operatorname{SU}(n)$ eine Untergruppe von $U(n)$.

2. **Normalität:**
   - Wir zeigen, dass für beliebige $X \in U(n)$ und $Y \in \operatorname{SU}(n)$ gilt:  $$
     \det(XYX^{-1}) = \det(Y)
     $$
Das ist analog zum Fall (1), da $X, Y \in U(n)$.
Da $X, Y \in U(n)$, gilt:
$$
X^{-1} = \overline{X}^T, \quad Y^{-1} = \overline{Y}^T
$$
   Also:$$(XYX^{-1})^{-1} = X^{-1} Y^{-1} X = \overline{X}^T \overline{Y}^T X = (\overline{X} \, \overline{Y} \, X)^T = (XYX^{-1})^T$$
   
   - Da $\det(Y) = 1$, gilt auch: $\det(XYX^{-1}) = \det(Y) = 1$
$\Rightarrow XYX^{-1} \in \operatorname{SL}(n, \mathbb{C}) \cap U(n) = \operatorname{SU}(n)$
   - Also ist $\operatorname{SU}(n) \leq U(n)$ ein **Normalteiler**.

### Isomorphie zu $S^1$

Zwei Elemente $X, Y \in U(n)$ sind äquivalent, wenn es ein $U \in U(n)$ gibt mit:
$$
X = Y \cdot U \iff X \cdot Y^{-1} = U
$$

- Wir definieren einen Homomorphismus:
$$
\varphi: U(n) / \operatorname{SU}(n) \to \mathbb{C}^\times, \quad X \mapsto \det(X)
$$

- **Homomorphismus:**  
  Wegen des **Determinantenmultiplikationssatzes** gilt:
  $$
  \varphi(XY) = \det(XY) = \det(X) \det(Y) = \varphi(X) \varphi(Y)
  $$
- **Wohldefiniertheit:** 

  Da für jedes $U \in \operatorname{SU}(n)$ gilt $\det(U) = 1$, ist:
  $$
  \varphi(XU) = \det(XU) = \det(X) \det(U) = \det(X) \cdot 1 = \det(X)
  $$

- **Surjektivität:**  
  Die Determinante jeder Matrix aus $U(n)$ liegt auf dem Einheitskreis in $\mathbb{C}$:  
  $$
  \det(X) \in S^1 = \{ z \in \mathbb{C} : |z| = 1 \}
  $$
  Durch Multiplikation mit einer komplexen Zahl vom Betrag $1$ können wir jede Zahl auf dem Einheitskreis erreichen.  

- **Injektivität**

- Angenommen, $\det(X) = \det(Y)$ für $X, Y \in U(n)$.  
- Dann gilt:
  $$
  \det(X) \det(Y^{-1}) = 1 \implies \det(XY^{-1}) = 1
  $$
  Das bedeutet, dass $XY^{-1} \in \operatorname{SU}(n)$.  
  Also sind $X$ und $Y$ äquivalent bezüglich $\operatorname{SU}(n)$.

- **Schlussfolgerung**

Damit ist gezeigt, dass der Quotient $U(n) / \operatorname{SU}(n)$ isomorph zu $S^1$ ist:
$$
U(n) / \operatorname{SU}(n) \cong S^1 \cong \mathbb{C}^\times
$$



---

### Zusammenfassung

| Gruppe                             | Normalteiler von       | Normalteiler? | Quotient / Isomorphie zu $\mathbb{C}^\times$?                   |
| ---------------------------------- | ---------------------- | ------------- | --------------------------------------------------------------- |
| $\operatorname{SL}(n, \mathbb{C})$ | $\operatorname{GL}(n)$ | Ja            | $S^1 \cong \mathbb{C}^\times$                                   |
| $D(n)$                             | $\operatorname{GL}(n)$ | Nein          | /                                                               |
| $U(n)$                             | $\operatorname{GL}(n)$ | Nein          | /                                                               |
| $D(n)$                             | $U(n)$                 | Nein          | /                                                               |
| $\operatorname{SU}(n)$             | $U(n)$                 | Ja            | $U(n) / \operatorname{SU}(n) \cong S^1 \cong \mathbb{C}^\times$ |

---