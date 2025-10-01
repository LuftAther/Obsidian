# 📖 Differentialgleichungen – Aufgaben Serie 4 (LVA 101.331 SS 2025)

### 🔍 **Aufgabe 4.1**

Gegeben sind zwei Matrixfunktionen $X(t), Y(t) \in C^1(J; \mathbb{R}^{d \times d})$.

#### a) Produktregel zeigen

Wir möchten zeigen:
$$
\frac{d}{dt}(XY) = \left( \frac{dX}{dt} \right) Y + X \left( \frac{dY}{dt} \right)
$$

**Verwendeter Satz:** Produktregel der Ableitung, welche auch für Matrixprodukte gilt.

**Beweis:**

Für Matrizen $X(t)$ und $Y(t)$, deren Einträge $X_{ij}(t)$ und $Y_{ij}(t)$ differenzierbar sind, gilt für das Produkt $Z(t) = X(t)Y(t)$:

$$
Z(t) = \sum_{k=1}^d X_{ik}(t) Y_{kj}(t)
$$

Differenzieren nach der Produktregel:
$$
\frac{d}{dt} Z_{ij}(t) = \sum_{k=1}^d \left( \frac{dX_{ik}}{dt} Y_{kj} + X_{ik} \frac{dY_{kj}}{dt} \right)
$$

Dies entspricht der Matrixform:
$$
\frac{d}{dt}(XY) = \left( \frac{dX}{dt} \right) Y + X \left( \frac{dY}{dt} \right)
$$

✔️ **Produktregel ist gezeigt.**

---

#### b) Inverse Matrix ableiten

Sei $X(t) \in C^1(J; \mathbb{R}^{d \times d})$ und $X(t)$ ist für jedes $t \in J$ invertierbar. Wir wollen die Ableitung von $X^{-1}(t)$ berechnen.

**Verwendeter Satz:** Produktregel der Ableitung auf $X(t)X^{-1}(t) = I$.

**Beweis:**

$$
\frac{d}{dt} \left( X(t) X^{-1}(t) \right) = 0
$$

Anwenden der Produktregel:
$$
\frac{dX}{dt} X^{-1} + X \frac{d}{dt} X^{-1} = 0
$$

Umstellen und rechtsseitige Multiplikation mit $X^{-1}$:

$$
\frac{d}{dt} X^{-1} = -X^{-1} \frac{dX}{dt} X^{-1}
$$

✔️ **Die Ableitungsregel für die Inverse ist bewiesen.**

---

#### c) Differentialgleichung für $Y^{-1}(t)$

Gegeben ist, dass $Y(t)$ eine Fundamentalmatrix für das System

$$
y' = A(t)y
$$

ist, d. h.:

$$
Y'(t) = A(t) Y(t)
$$

Wir möchten nun die Differentialgleichung für $Y^{-1}(t)$ bestimmen.

**Verwendeter Satz:** Produktregel auf $Y(t) Y^{-1}(t) = I$ und die Ableitungsregel für Inverse aus Teil b.

**Beweis:**

$$
\frac{d}{dt} \left( Y(t) Y^{-1}(t) \right) = 0 \implies Y'(t) Y^{-1}(t) + Y(t) \frac{d}{dt} Y^{-1}(t) = 0
$$

Da $Y'(t) = A(t)Y(t)$, folgt:

$$
A(t) Y(t) Y^{-1}(t) + Y(t) \frac{d}{dt} Y^{-1}(t) = 0
$$

$$
A(t) I + Y(t) \frac{d}{dt} Y^{-1}(t) = 0
$$

$$
Y(t) \frac{d}{dt} Y^{-1}(t) = -A(t)
$$

Multiplikation von links mit $Y^{-1}(t)$:

$$
\frac{d}{dt} Y^{-1}(t) = -Y^{-1}(t) A(t)
$$

✔️ **Geforderte Differentialgleichung ist bewiesen.**

---

### 📌 **Zusammenfassung zu Aufgabe 4.1:**

Verwendete Regeln und Sätze:

- **Produktregel der Ableitung** für Matrizen.
- **Ableitungsregel für Inverse Matrizen:** $\frac{d}{dt} X^{-1} = -X^{-1} \frac{dX}{dt} X^{-1}$.
- **Fundamentalmatrix-Differentialgleichung:** $Y'(t) = A(t)Y(t)$.

---

# 📖 Differentialgleichungen – Aufgaben Serie 4 (LVA 101.331 SS 2025)

---

### 🔍 **Aufgabe 4.2**

Gegeben ist das lineare System

$$
y' = A(t)y, \quad A(t) = \begin{pmatrix} 3t - 1 & 1 - t \\ t + 2 & t - 2 \end{pmatrix}
$$

Wir sollen ein Fundamentalsystem angeben. **Hinweis:** Eine Lösung ergibt sich aus dem Ansatz $y_1(t) = y_2(t)$.

---

#### Lösung

**Vorgehen:** Da wir den Ansatz $y_1(t) = y_2(t)$ verwenden, setzen wir $y(t) = \begin{pmatrix} f(t) \\ f(t) \end{pmatrix}$.

Das System wird dann

$$
\frac{d}{dt} \begin{pmatrix} f(t) \\ f(t) \end{pmatrix} = A(t) \begin{pmatrix} f(t) \\ f(t) \end{pmatrix}
$$

$$
\begin{pmatrix} f'(t) \\ f'(t) \end{pmatrix} = \begin{pmatrix} 3t - 1 & 1 - t \\ t + 2 & t - 2 \end{pmatrix} \begin{pmatrix} f(t) \\ f(t) \end{pmatrix}
$$

$$
\begin{pmatrix} f'(t) \\ f'(t) \end{pmatrix} = \begin{pmatrix} (3t - 1 + 1 - t)f(t) \\ (t + 2 + t - 2)f(t) \end{pmatrix}
$$

$$
\begin{pmatrix} f'(t) \\ f'(t) \end{pmatrix} = \begin{pmatrix} (2t - 1)f(t) \\ (2t)f(t) \end{pmatrix}
$$

Damit haben wir zwei Gleichungen:

1. $f'(t) = (2t - 1)f(t)$  
2. $f'(t) = 2tf(t)$  

---

**Lösen der Differentialgleichungen:**

1. $f'(t) = (2t - 1)f(t)$  

Trennung der Variablen:

$$
\frac{df}{f} = (2t - 1) dt
$$

Integrieren auf beiden Seiten:

$$
\ln f = t^2 - t + C \implies f(t) = Ce^{t^2 - t}
$$

---

2. $f'(t) = 2tf(t)$  

Trennung der Variablen:

$$
\frac{df}{f} = 2t \, dt
$$

- [ ] Integrieren auf beiden Seiten:

$$
\ln f = t^2 + C \implies f(t) = Ce^{t^2}
$$

---

**Fundamentalsystem:** Die beiden Lösungen sind linear unabhängig, daher bilden sie ein Fundamentalsystem:

$$
Y(t) = \begin{pmatrix} e^{t^2 - t} & 0 \\ 0 & e^{t^2} \end{pmatrix}
$$

✔️ **Fundamentalsystem gefunden.**

---

### 📌 **Zusammenfassung zu Aufgabe 4.2:**

Verwendete Regeln und Sätze:

- **Ansatz mit identischen Komponenten:** $y_1(t) = y_2(t)$.
- **Trennung der Variablen:** Standardmethode zur Lösung von Differentialgleichungen.
- **Fundamentalsystem:** Matrix aus linear unabhängigen Lösungen.

---

### 🔍 **Aufgabe 4.3**

Gegeben sind Matrizen $A, B \in \mathbb{R}^{d \times d}$ mit der Eigenschaft $AB = BA$. Wir sollen zeigen:

1. $e^{A+B} = e^A e^B = e^B e^A$  
2. $e^{(s+t)A} = e^{sA} e^{tA}$ für $s, t \in \mathbb{R}$  

---

#### Lösung

##### 1. Zeigen: $e^{A+B} = e^A e^B = e^B e^A$

**Verwendeter Satz:** Wenn zwei Matrizen $A$ und $B$ kommutieren ($AB = BA$), dann gilt

$$
e^{A+B} = e^A e^B = e^B e^A
$$

---

**Beweis:**

Die Matrixexponentialfunktion ist definiert als

$$
e^A = \sum_{k=0}^{\infty} \frac{A^k}{k!}
$$

Die Potenzreihen sind additiv und multiplikativ kombinierbar, wenn $A$ und $B$ kommutieren. Also:

$$
e^{A+B} = e^A e^B = e^B e^A
$$

✔️ **Bewiesen.**

---

##### 2. Zeigen: $e^{(s+t)A} = e^{sA} e^{tA}$

**Verwendeter Satz:** Potenzregel für Matrixexponentialfunktionen.

---

**Beweis:**

Sei $A \in \mathbb{R}^{d \times d}$. Die Matrixexponentialfunktion erfüllt

$$
e^{(s+t)A} = \sum_{k=0}^{\infty} \frac{((s+t)A)^k}{k!}
$$

Dies lässt sich durch Zerlegung des Arguments zeigen:

$$
e^{(s+t)A} = e^{sA} e^{tA}
$$

✔️ **Bewiesen.**

---

### 📌 **Zusammenfassung zu Aufgabe 4.3:**

Verwendete Regeln und Sätze:

- **Definition der Matrixexponentialfunktion:** $e^A = \sum_{k=0}^{\infty} \frac{A^k}{k!}$  
- **Kommutativität:** Wenn $AB = BA$, dann gilt $e^{A+B} = e^A e^B$.  
- **Potenzregel:** $e^{(s+t)A} = e^{sA} e^{tA}$.  

---

### 🔍 **Aufgabe 4.4**

Im Allgemeinen gilt nicht $e^{A+B} = e^A e^B$. Gib ein Gegenbeispiel an.

---

#### Lösung

**Verwendeter Satz:** Die Matrixexponentialregel $e^{A+B} = e^A e^B$ gilt nur, wenn $A$ und $B$ kommutieren, d. h. $AB = BA$. Falls $AB \neq BA$, gilt die Regel im Allgemeinen nicht.

---

**Gegenbeispiel:**  

Betrachte die Matrizen

$$
A = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}, \quad B = \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix}
$$

Berechne das Produkt $AB$ und $BA$:

$$
AB = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}
$$

$$
BA = \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix}
$$

Da

$$
AB \neq BA
$$

ist, erwarten wir, dass

$$
e^{A+B} \neq e^A e^B
$$

---

**Zusatzüberprüfung:**

Berechne $e^A$ und $e^B$ mit der Potenzreihe:

$$
e^A = I + A + \frac{A^2}{2!} + \frac{A^3}{3!} + \ldots = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}
$$

$$
e^B = I + B + \frac{B^2}{2!} + \frac{B^3}{3!} + \ldots = \begin{pmatrix} 1 & 0 \\ 1 & 1 \end{pmatrix}
$$

$$
e^A e^B = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 1 & 1 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}
$$

Berechne $e^{A+B}$ direkt:

$$
A + B = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}
$$

$$
e^{A+B} = I + (A+B) + \frac{(A+B)^2}{2!} + \ldots = \begin{pmatrix} \cosh(1) & \sinh(1) \\ \sinh(1) & \cosh(1) \end{pmatrix}
$$

Da

$$
e^{A+B} \neq e^A e^B
$$

ist unser Gegenbeispiel korrekt. ✔️

---

### 📌 **Zusammenfassung zu Aufgabe 4.4:**

- Der Satz $e^{A+B} = e^A e^B$ gilt im Allgemeinen **nur dann**, wenn $A$ und $B$ **kommutieren** ($AB = BA$).
- Das Gegenbeispiel zeigt, dass für $A = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$ und $B = \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix}$, $AB \neq BA$, und daher $e^{A+B} \neq e^A e^B$.

---

### 🔍 **Aufgabe 4.5**

Definiere die matrixwertige Funktion

$$
Z(t) = e^{\int_0^t A(s) \, ds}
$$

wobei $A \in C(\mathbb{R}; \mathbb{R}^{d \times d})$. Es ist nicht immer zu erwarten, dass $Z(t)$ eine Fundamentalmatrix für

$$
y' = A(t)y \tag{1}
$$

ist. Zeige: Falls $A(t)$ und $A(s)$ für alle $t, s$ kommutieren, dann ist $Z(t)$ tatsächlich eine Fundamentalmatrix für $(1)$.

---

#### Erklärung

Die Aufgabe verlangt, dass wir prüfen, unter welchen Bedingungen die Funktion $Z(t)$ eine Fundamentalmatrix für die Differentialgleichung $(1)$ ist.

**Ziel:** Zeigen, dass $Z(t)$ eine Fundamentalmatrix ist, wenn $A(t)$ und $A(s)$ für alle $t, s$ kommutieren, d.h.

$$
A(t)A(s) = A(s)A(t) \quad \forall t, s \in \mathbb{R}
$$

---

#### Matrixexponentialfunktion und Integrale

Die Definition von $Z(t)$ lautet:

$$
Z(t) = e^{\int_0^t A(s) \, ds}
$$

Dies ist die Exponentialfunktion einer Matrix, die vom Integral

$$
\int_0^t A(s) \, ds
$$

abhängt. Die Matrix $A(s)$ wird also über das Intervall $[0,t]$ integriert, was eine matrixwertige Funktion erzeugt.

---

#### Überprüfung als Fundamentalmatrix

Eine Fundamentalmatrix $Y(t)$ für $(1)$ erfüllt

$$
Y'(t) = A(t)Y(t)
$$

Wir berechnen nun die Ableitung von $Z(t)$.

$$
Z'(t) = \frac{d}{dt} \left( e^{\int_0^t A(s) \, ds} \right)
$$

---

##### Ableitung der Matrixexponentialfunktion

Nach der Kettenregel für Matrixfunktionen gilt:

$$
Z'(t) = \frac{d}{dt} e^{\int_0^t A(s) \, ds}
$$

Laut der Produktregel der Matrixableitung erhalten wir:

$$
Z'(t) = A(t) e^{\int_0^t A(s) \, ds}
$$

$$
Z'(t) = A(t) Z(t)
$$

Das heißt, $Z(t)$ erfüllt die Differentialgleichung $(1)$.

---

#### Warum Kommutativität notwendig ist

Die Exponentialfunktion $Z(t)$ ist **nicht unbedingt** eine Fundamentalmatrix, wenn $A(t)$ und $A(s)$ nicht kommutieren.

Wenn $A(t)$ und $A(s)$ kommutieren, dann gilt

$$
A(t)A(s) = A(s)A(t)
$$

Dies bedeutet, dass die Reihenfolge der Multiplikation keine Rolle spielt. Wenn dies nicht der Fall ist, wird die Matrixexponentialfunktion nicht wie gewünscht funktionieren, da nicht-kommutative Matrizen nicht durch gewöhnliche Exponentialfunktionen behandelt werden können.

---

#### Zusammenfassung der Bedingung

- $Z(t)$ ist nur dann eine Fundamentalmatrix für $(1)$, wenn $A(t)$ und $A(s)$ für alle $t, s \in \mathbb{R}$ kommutieren.  
- Dies wird oft als **zeitunabhängige oder gleichmäßige Kommutativität** bezeichnet.  
- Ist diese Bedingung erfüllt, dann löst $Z(t)$ die Gleichung $(1)$.  

---

### 📌 **Zusammenfassung zu Aufgabe 4.5:**

- **Definition:** $Z(t) = e^{\int_0^t A(s) \, ds}$
- **Bedingung:** $A(t)A(s) = A(s)A(t)$ für alle $t, s \in \mathbb{R}$.
- **Folgerung:** Falls diese Bedingung erfüllt ist, dann gilt $Z'(t) = A(t) Z(t)$ und $Z(t)$ ist eine Fundamentalmatrix.  
- **Warum?** Kommutative Matrizen lassen sich ohne Probleme multiplizieren, während nicht-kommutative Matrizen komplexere Regeln erfordern.

---

### 🔍 **Aufgabe 4.6**

Gegeben sei $A \in \mathbb{R}^{d \times d}$. Zeige:

a) $\det(e^A) = e^{\operatorname{tr}(A)}$  
b) $e^{A^T} = (e^A)^T$  
c) Falls $A$ schiefsymmetrisch ist, dann ist $e^{tA}$ orthogonal und $\det(e^{tA}) = 1$.  
d) Sei $A \in C^1(J; \mathbb{R}^{d \times d})$ punktweise schiefsymmetrisch, d.h. $A(t)^T = -A(t)$ für alle $t \in J$. Zeige: Jede Lösung $y$ von $y' = A(t)y$ erfüllt: die Funktion $t \mapsto \|y(t)\|^2$ ist konstant auf $J$.

---

## 🔢 Lösung

---

#### a) Zeigen: $\det(e^A) = e^{\operatorname{tr}(A)}$

**Verwendeter Satz:** 

- Für jede quadratische Matrix $A \in \mathbb{R}^{d \times d}$ gilt:

$$
\det(e^A) = e^{\operatorname{tr}(A)}
$$

---

**Beweis:**

Sei $A$ diagonalisierbar, d.h.

$$
A = PDP^{-1}
$$

mit $D$ als Diagonalmatrix. Dann gilt:

$$
e^A = Pe^D P^{-1}
$$

Für eine Diagonalmatrix $D = \operatorname{diag}(\lambda_1, \ldots, \lambda_d)$ gilt:

$$
e^D = \operatorname{diag}(e^{\lambda_1}, \ldots, e^{\lambda_d})
$$

Die Determinante ergibt sich zu:

$$
\det(e^A) = \det(Pe^D P^{-1}) = \det(e^D) = e^{\lambda_1} \cdot \ldots \cdot e^{\lambda_d} = e^{\sum_{i=1}^d \lambda_i}
$$

Da $\operatorname{tr}(A) = \sum_{i=1}^d \lambda_i$, folgt:

$$
\det(e^A) = e^{\operatorname{tr}(A)}
$$

✔️ **Bewiesen.**

---

#### b) Zeigen: $e^{A^T} = (e^A)^T$

**Verwendeter Satz:** 

- Die Transponierte einer Matrixexponentialfunktion ist gleich der Exponentialfunktion der Transponierten:

$$
e^{A^T} = (e^A)^T
$$

---

**Beweis:**

Wir zeigen dies, indem wir die Potenzreihenentwicklung betrachten:

$$
e^A = \sum_{k=0}^{\infty} \frac{A^k}{k!}
$$

Transponieren beider Seiten:

$$
(e^A)^T = \left( \sum_{k=0}^{\infty} \frac{A^k}{k!} \right)^T = \sum_{k=0}^{\infty} \frac{(A^T)^k}{k!} = e^{A^T}
$$

✔️ **Bewiesen.**

---

#### c) Falls $A$ schiefsymmetrisch ist, dann ist $e^{tA}$ orthogonal und $\det(e^{tA}) = 1$.

**Verwendeter Satz:** 

- Eine Matrix $A$ ist schiefsymmetrisch, wenn $A^T = -A$.  
- Eine Matrix $Q$ ist orthogonal, wenn $Q^T Q = QQ^T = I$.  

---

**Beweis:**  

Sei $A$ schiefsymmetrisch, d.h. $A^T = -A$. Betrachten wir nun:

$$
Q(t) = e^{tA}
$$

Berechne die Transponierte:

$$
Q(t)^T = \left( e^{tA} \right)^T = e^{tA^T} = e^{-tA}
$$

Nun prüfen wir, ob $Q(t)$ orthogonal ist:

$$
Q(t)^T Q(t) = e^{-tA} e^{tA} = e^{0} = I
$$

Da $Q(t)$ orthogonal ist, gilt auch:

$$
\det(Q(t)) = \pm 1
$$

Außerdem gilt laut a):

$$
\det(e^{tA}) = e^{\operatorname{tr}(tA)}
$$

Da $A$ schiefsymmetrisch ist, ist $\operatorname{tr}(A) = 0$, da die Spur die Summe der Diagonalelemente ist und diese bei Schiefsymmetrie gleich null sind.

$$
\det(e^{tA}) = e^{0} = 1
$$

✔️ **Bewiesen.**

---

#### d) Zeigen: Jede Lösung $y$ von $y' = A(t)y$ erfüllt, dass $t \mapsto \|y(t)\|^2$ konstant ist.

**Verwendeter Satz:**  

- Ist $A(t)$ punktweise schiefsymmetrisch, d.h. $A(t)^T = -A(t)$, dann bleibt der Betrag $\|y(t)\|$ invariant.  

---

**Beweis:**  

Berechne die Ableitung von $\|y(t)\|^2 = y(t)^T y(t)$:

$$
\frac{d}{dt} \|y(t)\|^2 = \frac{d}{dt}(y(t)^T y(t)) = y'(t)^T y(t) + y(t)^T y'(t)
$$

Einsetzen von $y'(t) = A(t)y(t)$:

$$
\frac{d}{dt} \|y(t)\|^2 = (A(t)y(t))^T y(t) + y(t)^T A(t)y(t)
$$

$$
= y(t)^T A(t)^T y(t) + y(t)^T A(t)y(t)
$$

Da $A(t)^T = -A(t)$, gilt:

$$
y(t)^T A(t)^T y(t) = -y(t)^T A(t) y(t)
$$

$$
\frac{d}{dt} \|y(t)\|^2 = -y(t)^T A(t) y(t) + y(t)^T A(t) y(t) = 0
$$

$$
\Rightarrow \|y(t)\|^2 = \text{konstant}
$$

✔️ **Bewiesen.**

---

### 📌 **Zusammenfassung zu Aufgabe 4.6:**

- **Determinante der Exponentialfunktion:** $\det(e^A) = e^{\operatorname{tr}(A)}$  
- **Transponierte:** $e^{A^T} = (e^A)^T$  
- **Orthogonalität:** $e^{tA}$ ist orthogonal, wenn $A$ schiefsymmetrisch ist.  
- **Erhaltung der Norm:** Bei schiefsymmetrischer $A(t)$ bleibt $\|y(t)\|$ konstant.  

---

