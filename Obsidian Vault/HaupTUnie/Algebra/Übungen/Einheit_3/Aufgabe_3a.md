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

---

### (1) Definiere eine Algebra $\mathcal{A}$ so, dass $\sim$ die einzige nicht-triviale Kongruenzrelation ist.

#### Definition der Operationen:

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


---

### (2) Zeige, dass ein Homomorphismus $\varphi: \mathcal{A} / \sim \to \mathcal{B}$ entweder konstant oder injektiv ist.

Sei $\mathcal{B}$ eine Algebra gleichen Typs und $\varphi$ ein Homomorphismus. Das bedeutet:

$$
\varphi(f_i([x])) = \omega_i(\varphi([x]))
$$

#### Zu zeigen: $\varphi$ ist entweder **konstant** oder **injektiv**.

---

#### Beweis:

- Es gibt genau **drei Äquivalenzklassen** von $\sim$:
  $$
  C_1 = \{1,2\}, \quad C_2 = \{3,4,5\}, \quad C_3 = \{6,7\}
  $$

- Ein Homomorphismus $\varphi$ kann also drei mögliche Werte haben, $\varphi(C_1), \varphi(C_2), \varphi(C_3)$.

- Da $\varphi$ ein Homomorphismus ist, muss er die Struktur von $\mathcal{A}$ respektieren. Insbesondere wird die Partition $\sim$ **entweder vollständig zusammengezogen** (d.h., alle Klassen werden auf einen Punkt abgebildet) oder jede Klasse wird auf ein **unterschiedliches Element** abgebildet.

- Wenn $\varphi$ auf alle Klassen den gleichen Wert abbildet, dann ist $\varphi$ **konstant**.

- Wenn $\varphi$ auf jede Klasse einen **unterschiedlichen Wert** abbildet, dann ist $\varphi$ **injektiv**.

- Es gibt keine Möglichkeit, dass $\varphi$ teilweise injektiv ist, da ein Homomorphismus zwischen Äquivalenzklassen immer entweder vollständig kollabiert oder vollständig differenziert ist.

$$
\boldsymbol{\therefore} \quad \varphi \text{ ist entweder konstant oder injektiv.}
$$

---

### (2) Zeige, dass ein Homomorphismus $\varphi: \mathcal{A} / \sim \to \mathcal{B}$ entweder konstant oder injektiv ist.

Im Folgenden betrachten wir also die Restklassen von $A$, $[1]$, $[3]$, $[6]$ und einen beliebigen Homomorphismus $\varphi$ auf dieser Menge.

#### Angenommen, $\varphi$ wäre nicht injektiv.

- Falls $\varphi([1]) = \varphi([3])$, so folgt daraus  
  $$
  \omega_2^B(\varphi([1])) = \varphi(\omega_2([1])) = \varphi([6]) = \varphi(\omega_2([3])) = \omega_2^B(\varphi([3])).
  $$
  
- Falls $\varphi([1]) = \varphi([6])$, so folgt daraus  
  $$
  \omega_3^{\mathcal{B}}(\varphi([1])) = \varphi(\omega_3([1])) = \varphi([3]) = \varphi(\omega_3([6])) = \omega_3^{\mathcal{B}}(\varphi([6])).
  $$

- Falls $\varphi([6]) = \varphi([3])$, so folgt daraus  
  $$
  \omega_2^\mathcal{B}(\varphi([6])) = \varphi(\omega_2([6])) = \varphi([1]) = \varphi(\omega_2([3])) = \omega_2^\mathcal{B}(\varphi([3])).
  $$

In jedem Fall wäre $\varphi$ konstant.

---

#### Angenommen, $\varphi$ wäre nicht konstant.

Wir betrachten den Fall $\varphi([3]) \neq \varphi([6])$, der Rest geht analog.

- Angenommen $\varphi([3]) = \varphi([1])$, dann gilt auch  
  $$
  \varphi([6]) = \omega_3^\mathcal{B}(\varphi([3])) = \omega_3^\mathcal{B}(\varphi([1])) = \varphi([1]) = \varphi([3]).
  $$  
  Widerspruch.

- Angenommen $\varphi([1]) = \varphi([6])$, dann wäre auch  
  $$
  \varphi([6]) = \omega_2^\mathcal{B}(\varphi([1])) = \omega_2^\mathcal{B}(\varphi([6])) = \varphi([3]).
  $$
  Widerspruch.

Also ist $\varphi$ injektiv.
