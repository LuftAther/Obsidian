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

> Die Menge aller Restklassen

$A \cdot \operatorname{SL}(n, \mathbb{C})$, wobei $A \in \operatorname{GL}(n, \mathbb{C})$.

>Zwei Elemente $A, B \in \operatorname{GL}(n, \mathbb{C})$ sind äquivalent, wenn es ein $S \in \operatorname{SL}(n, \mathbb{C})$ gibt, sodass:
$$
A \cdot B^{-1} = S
$$Das ist äquivalent zu:
>$$
A \sim B \quad \Leftrightarrow \quad A = BS \quad \text{für ein } S \in \operatorname{SL}(n, \mathbb{C}).$$>

##### Behauptung:
Die Faktorgruppe $\operatorname{GL}(n, \mathbb{C}) / \operatorname{SL}(n, \mathbb{C})$ ist *isomorph* zu $\mathbb{C}^\times$.
wobei wir behaupen dass2 
$$
\varphi: \operatorname{GL}(n,K / \operatorname{SL}(n, K) \to \mathbb{C}^\times, \quad \varphi(A \cdot \operatorname{SL}(n, K)) = \det(A)
$$
ein Isomorphismus ist.

---

#### Nachweis

- Klarerweise ist $\varphi$ wohldefiniert, weil
  $$
  \det(AB) = \det(A) \det(B)
  $$
  aufgrund des **Determinantenmultiplikationssatzes**.
- Wenn $A \sim B$, dann existiert ein $S \in \operatorname{SL}(n, \mathbb{C})$ mit:
  $$
  A = BS
  $$
  Also gilt:
  $$
  \det(A) = \det(B) \det(S) = \det(B) \cdot 1 = \det(B)
  $$

- Außerdem ist $\varphi$ ein **Homomorphismus**, weil:
  $$
  \varphi(AB) = \det(AB) = \det(A) \det(B) = \varphi(A) \varphi(B)
  $$

- $\varphi$ ist **surjektiv**, da man durch Skalierung der Einheitsmatrix $I$ jede Zahl aus $\mathbb{C}^\times$ treffen kann:
  $$
  \det(\lambda I) = \lambda^n \in \mathbb{C}^\times
  $$

---

#### Injektivität

- Angenommen, $\varphi(A) = \varphi(B)$ für $A, B \in \operatorname{GL}(n, \mathbb{C})$. Das bedeutet:
  $$
  \det(A) = \det(B)
  $$

- Betrachte nun $A \cdot B^{-1}$. Dann gilt:
  $$
  \det(A \cdot B^{-1}) = \frac{\det(A)}{\det(B)} = 1
  $$

- Also ist $A \cdot B^{-1} \in \operatorname{SL}(n, \mathbb{C})$. Somit:
  $$
  A \sim B
  $$

---

#### Fazit

Damit ist gezeigt, dass $\varphi$ ein **Isomorphismus** ist:
$$
\operatorname{GL}(n, \mathbb{C}) / \operatorname{SL}(n, \mathbb{C}) \cong \mathbb{C}^\times
$$


---

### (2) $D(n) \leq \operatorname{GL}(n)$

- **Definition:** $D(n)$ sind die regulären Diagonalmatrizen mit $\det \neq 0$.
- **Frage:** Ist $D(n)$ ein Normalteiler von $\operatorname{GL}(n)$?

#### Nachweis:

Für eine Matrix $A \in \operatorname{GL}(n)$ und $D \in D(n)$ ist im Allgemeinen:
$$
ADA^{-1} \notin D(n)
$$
Da $A$ eine beliebige invertierbare Matrix ist, wird durch Konjugation eine Diagonalmatrix normalerweise in eine nicht-diagonale Matrix umgewandelt. Daher ist $D(n)$ **kein Normalteiler**.

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

---

### (4) $D(n) \leq U(n)$

- **Definition:** $D(n)$ ist die Gruppe der regulären Diagonalmatrizen.
- **Frage:** Ist $D(n)$ ein Normalteiler von $U(n)$?

#### Nachweis:

- Diagonale Matrizen $D \in D(n)$, die unitär sind, haben **Einträge von Betrag $1$**.
- Sei $U \in U(n)$, dann gilt:
  $$
  UDU^{-1} \in D(n)
  $$
  Wenn $D$ eine unitäre Matrix ist, bleibt sie nach Konjugation mit einer unitären Matrix auch unitär und diagonal.  
  **Also: $D(n)$ ist ein Normalteiler von $U(n)$.**

#### Quotientengruppe:
$$
U(n)/D(n) \cong \operatorname{SU}(n)
$$
- Die Determinante ist der relevante Homomorphismus, und der Kern ist $D(n)$.

---

### (5) $\operatorname{SU}(n) \leq U(n)$

- **Definition:** $\operatorname{SU}(n)$ ist die Gruppe der **speziellen unitären Matrizen** mit $\det(U) = 1$.
- **Frage:** Ist $\operatorname{SU}(n)$ ein Normalteiler von $U(n)$?

#### Nachweis:

Für $U \in U(n)$ und $V \in \operatorname{SU}(n)$ gilt:
$$
\det(UVU^{-1}) = \det(U) \det(V) \det(U^{-1}) = \det(V) = 1
$$
$\operatorname{SU}(n)$ ist also unter Konjugation abgeschlossen und damit ein **Normalteiler**.

#### Quotientengruppe:
$$
U(n)/\operatorname{SU}(n) \cong S^1 \cong \mathbb{C}^\times
$$
- Dies ist, weil $U(n)/\operatorname{SU}(n)$ durch die Determinantenabbildung beschrieben wird:
  $$
  \det: U(n) \to S^1 = \{ z \in \mathbb{C} : |z| = 1 \}
  $$
  Da $\operatorname{SU}(n)$ diejenigen Matrizen mit Determinante $1$ sind, ist der Quotient isomorph zu $S^1$.

---

### Zusammenfassung

| Gruppe                 | Normalteiler von        | Normalteiler? | Quotient / Isomorphie zu $\mathbb{C}^\times$? |
|------------------------|------------------------|---------------|----------------------------------------------|
| $\operatorname{SL}(n, \mathbb{C})$ | $\operatorname{GL}(n)$ | Ja           | $\mathbb{C}^\times$                         |
| $D(n)$                 | $\operatorname{GL}(n)$  | Nein          | Nein                                         |
| $U(n)$                 | $\operatorname{GL}(n)$  | Nein          | Nein                                         |
| $D(n)$                 | $U(n)$                  | Ja            | $\operatorname{SU}(n)$                      |
| $\operatorname{SU}(n)$ | $U(n)$                  | Ja            | $S^1 \cong \mathbb{C}^\times$               |

---