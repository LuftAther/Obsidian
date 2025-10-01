Sei $A = \{1, 2, 3, 4, 5, 6, 7\}$ eine 7-elementige Menge und $\sim$ die durch die Partition $\{\{1,2\}, \{3,4,5\}, \{6,7\}\}$ induzierte Äquivalenzrelation.

1. Geben Sie eine Algebra $\mathcal{A} = (A, \omega_1, \ldots, \omega_k)$ an, sodass $\sim$ die einzige nicht-triviale Kongruenzrelation (ungleich $\{(x,x) : x \in A\}$, ungleich $A \times A$) dieser Algebra ist.
   *Hinweis: Man kommt mit unären Funktionen aus.*

2. Sei $\mathcal{B}$ eine beliebige Algebra gleichen Typs, und sei $\varphi : \mathcal{A} / \sim \to \mathcal{B}$ ein beliebiger Homomorphismus. Zeigen Sie, dass $\varphi$ entweder konstant oder injektiv sein muss.

---
### Gegeben:
- Eine Menge $A = \{1,2,3,4,5,6,7\}$.
- Eine Äquivalenzrelation $\sim$ definiert durch die Partition:
  $$
  \{ \{1,2\}, \{3,4,5\}, \{6,7\} \}
  $$
  Das bedeutet:
$$
  x \sim y \quad \Leftrightarrow \quad x \text{ und } y
- \text{ sind im gleichen "Block" der Partition.}
  $$
  Also: $1 \sim 2$, $3 \sim 4 \sim 5$, $6 \sim 7$.
- definiert. Die Äquivalenzklassen sind also:
	- $A_1 = \{1,2\}$
	- $A_2 = \{3,4,5\}$
	- $A_3 = \{6,7\}$

---

### (1) Definiere eine Algebra $\mathcal{A}$ so, dass $\sim$ die einzige nicht-triviale Kongruenzrelation ist.

#### Definition der Operationen:
- $w_1(a) = \begin{cases} 1 & \text{wenn } a \in A_1 \\ 3 & \text{wenn } a \in A_2 \\ 6 & \text{wenn } a \in A_3 \end{cases}$  
- $w_2(a) = \begin{cases} 2 & \text{wenn } a \in A_1 \\ 4 & \text{wenn } a \in A_2 \\ 7 & \text{wenn } a \in A_3 \end{cases}$  
- $w_3(a) = \begin{cases} 1 & \text{wenn } a \in A_1 \\ 5 & \text{wenn } a \in A_2 \\ 6 & \text{wenn } a \in A_3 \end{cases}$  

---

### **Warum ist $\sim$ die einzige nichttriviale Kongruenzrelation?**

1. **Definition von Kongruenzrelation:**  
   Eine Kongruenzrelation $\rho$ ist eine Äquivalenzrelation auf $A$, die mit den Funktionen $w_i$ verträglich ist.  
   Das bedeutet, wenn $(a, b) \in \rho$, dann gilt:

   $$
   w_i(a) = w_i(b) \quad \text{für alle } i \in \{1,2,3\}
   $$

2. **Funktionen trennen die Klassen:**  
   Die Funktionen $w_1, w_2, w_3$ sind so konstruiert, dass sie auf jeder Klasse unterschiedliche Werte annehmen.  
   Zum Beispiel:

   - Für $A_1$: $w_1(1) = 1, w_2(1) = 2, w_3(1) = 1$  
   - Für $A_2$: $w_1(3) = 3, w_2(3) = 4, w_3(3) = 5$  
   - Für $A_3$: $w_1(6) = 6, w_2(6) = 7, w_3(6) = 6$  

   Diese Werte unterscheiden sich in **jedem Fall**.  

3. **Schlussfolgerung:**  
   Jede Kongruenzrelation $\rho$ auf $\mathcal{A}$ muss die Klassen $A_1, A_2, A_3$ **genau so trennen**.  
   Andernfalls ist $\rho$ entweder die triviale Relation $\{(x,x) \mid x \in A\}$ oder $A \times A$.  

---
----------Warning-----------

- $\omega_1: A \to A$ zum "Zusammenkleben" der Äquivalenzklassen:

  $$
  \omega_1(x) = \begin{cases} 
  1 & \mapsto 2 \\
  2 & \mapsto 1 \\
  3 & \mapsto 4 \\
  4 & \mapsto 3 \\
  5 & \mapsto 4 \\
  6 & \mapsto 7 \\
  7 & \mapsto 6 \\
  \end{cases}
  $$

- $\omega_2: A \to A$ zur Trennung der Klassen $\{1,2,3,4,5\}$, $\{1,2,6,7\}$ und $\{3,4,5,6,7\}$:

  $$
  \omega_2(x) = \begin{cases} 
  6 & \text{wenn } x \in \{1,2\}, \\
  1 & \text{wenn } x \in \{3,4,5\}, \\
  2 & \text{wenn } x \in \{6,7\}.
  \end{cases}
  $$

- $\omega_3: A \to A$ zur Trennung der Klassen $\{1,2,6,7\}$, $\{3,4,5\}$ und $\{6,7\}$:

  $$
  \omega_3(x) = \begin{cases} 
  4 & \text{wenn } x \in \{1,2\}, \\
  7 & \text{wenn } x \in \{3,4,5\}, \\
  2 & \text{wenn } x \in \{6,7\}.
  \end{cases}
  $$

Die Algebra ist also:
$$
\mathcal{A} = (A, \omega_1, \omega_2, \omega_3)
$$
#### Nachweis: $\sim$ ist die einzige nicht-triviale Kongruenzrelation

- Die definierten Operationen sind so konstruiert, dass sie genau die Äquivalenzklassen der Partition $\sim$ respektieren.
- Sei $\theta$ unsere Kongruenzrelation auf $\mathcal{A}$.

1. **Trivialität ausschließen:**  
   - $\theta$ ist nicht die Identitätsrelation $\{(x,x) : x \in A\}$.
   - $\theta$ ist auch nicht $A \times A$ (wo jedes Element mit jedem äquivalent ist).
   - Es kann keine größere Klasse geben da angenommen $\{ 1,2,3 \}$ dann ist aufgrund von $\omega_{2}(2) = 6 , \quad \omega_{2}(3) = 7$ auch $\{ 6,7 \}$ aquivalent gilt es auch für alle weiteren Erweiterungen
   d.h wir fürden ganh $\mathcal{A}$ erhalten was **Trivial** wäre

2. **Erhalten der Äquivalenzklassen:**  
   - Da $\omega_1$ alle Elemente innerhalb jeder Klasse auf ein einzelnes Element abbildet, sind diese Klassen "untrennbar". 
   - $\omega_2$ und $\omega_3$ wurden so definiert, dass sie bestimmte Blöcke trennen.  
   - Zum Beispiel: $\omega_2$ unterscheidet $\{1,2\}$ von $\{3,4,5\}$ und $\{6,7\}$.

3. **Schlussfolgerung:**  
   - Jede Kongruenzrelation, die von $\omega_1, \omega_2, \omega_3$ erhalten wird, entspricht genau $\sim$.
   - **Falls $\theta$ nicht trivial ist, muss $\theta = \sim$ sein.**
---------------Warning----------------------

---

### (2) Zeige, dass ein Homomorphismus $\varphi: \mathcal{A} / \sim \to \mathcal{B}$ entweder konstant oder injektiv ist.

Sei $\mathcal{B}$ eine Algebra gleichen Typs und $\varphi$ ein Homomorphismus. Das bedeutet:

$$
\varphi(f_i([x])) = \omega_i(\varphi([x]))
$$

#### Zu zeigen: $\varphi$ ist entweder **konstant** oder **injektiv**.

---

#### Beweis:

- **Angenomen:** $\varphi$ ist nicht injektiv.

Das bedeutet, dass mindestens zwei Äquivalenzklassen denselben Wert unter $\varphi$ haben.

- ### **Fallunterscheidung:**  
- 
1. **Fall 1:** $\varphi([1]) = \varphi([3])$
	- Da $\varphi$ ein Homomorphismus ist, gilt:  
  $$
  w_2^{\mathcal{B}}(\varphi([1])) = \varphi(w_2([1])) = \varphi(w_2([3])) = w_2^{\mathcal{B}}(\varphi([3]))
  $$
	- Das bedeutet, dass $\varphi([6]) = \varphi([3]) = \varphi([1])$.  
	- Also ist $\varphi$ **konstant** auf allen drei Klassen.

2. **Fall 2:** $\varphi([1]) = \varphi([6])$
- Da $\varphi$ ein Homomorphismus ist, gilt:  

	$$
  w_3^{\mathcal{B}}(\varphi([1])) = \varphi(w_3([1])) = \varphi(w_3([6])) = w_3^{\mathcal{B}}(\varphi([6]))
  $$

- Das bedeutet, dass $\varphi([3]) = \varphi([6]) = \varphi([1])$.  
- Also ist $\varphi$ **konstant** auf allen drei Klassen.

3. **Fall 3:** $\varphi([3]) = \varphi([6])$
- Da $\varphi$ ein Homomorphismus ist, gilt:  

  $$
  w_2^{\mathcal{B}}(\varphi([6])) = \varphi(w_2([6])) = \varphi(w_2([3])) = w_2^{\mathcal{B}}(\varphi([3]))
  $$

- Das bedeutet, dass $\varphi([1]) = \varphi([3]) = \varphi([6])$.  
- Also ist $\varphi$ **konstant** auf allen drei Klassen.

---
**Zusammengefasst:**  

Wenn $\varphi$ nicht injektiv ist, dann gilt in jedem Fall:

$$
\varphi([1]) = \varphi([3]) = \varphi([6])
$$

Das bedeutet, dass $\varphi$ **konstant** ist.

---

**Injektivität beweisen**
#### **Anngenommen:** $\varphi$ ist nicht konstant.

Das bedeutet, dass mindestens zwei Äquivalenzklassen verschieden abgebildet werden. Ohne Einschränkung sei:
$$
\varphi([3]) \neq \varphi([6])
$$

---  
Ei also 
1. Angenommen, $\varphi([3]) = \varphi([1])$.  
   - Dann gilt:

     $$
     \varphi([6]) = w_3^{\mathcal{B}}(\varphi([3])) = w_3^{\mathcal{B}}(\varphi([1])) = \varphi([1])
     $$

   - Widerspruch zur Annahme $\varphi([3]) \neq \varphi([6])$.

---

2. Angenommen, $\varphi([1]) = \varphi([6])$.  
   - Dann gilt:

     $$
     \varphi([3]) = w_2^{\mathcal{B}}(\varphi([6])) = w_2^{\mathcal{B}}(\varphi([1])) = \varphi([1])
     $$

   - Widerspruch zur Annahme $\varphi([3]) \neq \varphi([6])$.
Da jede mögliche Gleichsetzung von zwei Äquivalenzklassen zu einem Widerspruch führt, muss gelten:

$$
\varphi([1]) \neq \varphi([3]) \neq \varphi([6])
$$

Das bedeutet, dass $\varphi$ **injektiv** ist.
