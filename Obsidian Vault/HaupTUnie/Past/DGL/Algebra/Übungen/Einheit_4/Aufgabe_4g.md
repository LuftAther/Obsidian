Sei $G$ eine endliche Gruppe der Ordnung $n$, und $p$ ein Primfaktor von $n$. Zeigen Sie: $G$ hat eine Untergruppe der Ordnung $p$.

**Hinweis:** Zeigen Sie die folgenden Aussagen.

1. Sei $X := \{ \vec{x} = (x_1, \ldots, x_p) \in G^p : x_1 \cdots x_p = 1_G \}$. Zeigen Sie $|X| = n^{p-1}$.
2. Betrachten Sie die Abbildung $f: \mathbb{Z}_p \times X \to X$ mit $f(k, \vec{x}) = (x_{k+1}, \ldots, x_p, x_1, \ldots, x_k)$.  
   - Indizes gerechnet mod $p$. 
   - Das ist eine Gruppenwirkung. 
   - Jeder Orbit $\mathbb{Z}_p \cdot \vec{x}$ hat also Größe 1 oder $p$.
1. Die Orbits partitionieren also $X$ in Klassen der Größe 1 und $p$.
2. $p$ teilt $|X|$, also ist die Anzahl der $p$-elementigen Orbits $kp$ für ein $k \in \mathbb{N}$.

3. $|\mathbb{Z}_p| = p$ und $\vec{e} = (g, \ldots, g)$ für ein $g \in G$.  
   - Das ist jedenfalls der Fall für $g = 1_G$.  
   - Daher muss es mindestens ein weiteres $g \neq 1_G$ geben mit $(g, \ldots, g) \in X$.
1. **Schließen Sie:** $\langle g \rangle \cong \mathbb{Z}_p$.
---
Vorgang nach Hinweis:

### 1. Teil
Sei $X = \left\{ \vec{x} = (x_1, \ldots, x_p) \in G^p \mid x_1 \cdots x_p = 1_G \right\}$, wobei $1_G$ das neutrale Element in $G$ ist.

- **Aus der linearen Algebra** wissen wir, dass $|G| = n$. Also ist:
  $$
  |G^p| = n^p
  $$
- Weil mir bzgl. $\circ$ abgeschlossen ist  kann $|X| \ngeq n^{p-1}$ sein.

#### Behauptung: 
Eine Basis von $X$ hat $p - 1$ Basisvektoren (Erzeugendensystem).

- Betrachte $k \in \{1, \ldots, p-1\}$, aber $p-1$ ist fest.
- Nach $\forall \, p$ gilt: 
  $$
  x_1 \cdots x_p = 1_G \implies x_p = x_1^{-1} \cdots x_{p-1}^{-1}
  $$
- **Anders ausgedrückt:**  
  $$
  |X| = n^{p-1}
  $$
- Man kann also alle $X$ mit $p-1$ Elementen erzeugen (linear unabhängig).

#### Angenommen: 
$$
|X| < p - 1
$$

- Betrachte $k < p - 1$. Es muss gelten: Alle aus $p-1$ $x_i$ erzeugen.
- Daraus folgt, dass $X$ tatsächlich $n^{p-1}$ Elemente besitzt.
---
### (ii) Betrachten Sie die Gruppenwirkung $f: \mathbb{Z}_p \times X \to X$ definiert durch  
$$
f(k, \vec{x}) = (x_{k+1}, \ldots, x_p, x_1, \ldots, x_k)
$$

#### Behauptung: $f$ ist eine Gruppenwirkung.

1. **Wirkung ist wohldefiniert:**  
   $$
   f(g_1g_2, \vec{x}) = f(g_1, f(g_2, \vec{x}))
   $$
   Das bedeutet, dass $f$ assoziativ ist.

---

2. **Beweis der Gruppenwirkungseigenschaften:**

   - $f(0, \vec{x}) = \vec{x}$ (Neutrales Element).  
   - $f(g_1g_2, \vec{x}) = f(g_1, f(g_2, \vec{x}))$ (Assoziativität).

   - Berechne:
     $$
     f(g_1, \vec{x}) = (x_{g_1+1}, \ldots, x_p, x_1, \ldots, x_{g_1})
     $$

     $$
     f(g_2, \vec{x}) = (x_{g_2+1}, \ldots, x_p, x_1, \ldots, x_{g_2})
     $$

     $$
     f(g_1g_2, \vec{x}) = (x_{(g_1 + g_2) \mod p + 1}, \ldots, x_p, x_1, \ldots, x_{(g_1 + g_2) \mod p})
     $$

     - Da $g_1g_2$ als Summenmodulo $p$ betrachtet wird:
       $$
       g_1 \mod p = \tilde{a}, \quad \text{also} \quad g_1 = np + \tilde{a}
       $$
       $$
       g_2 \mod p = \tilde{b}, \quad \text{also} \quad g_2 = kp + \tilde{b}
       $$

     - Assoziativität folgt durch:
       $$
       1 + (np \cdot \tilde{a} + kp \cdot \tilde{b}) \equiv 1 + \tilde{a} + \tilde{b} \pmod{p}
       $$

---

3. **Behauptung:** Jeder Orbit $\mathbb{Z}_p \cdot \vec{x}$ hat Größe $1$ oder $p$.  

- **Orbit der Größe $1$:**  
  Dies ist genau dann der Fall, wenn $f(k, \vec{x}) = \vec{x}$ für alle $k \in \mathbb{Z}_p$.  
  Das bedeutet, dass $\vec{x}$ konstant ist.  

- **Orbit der Größe $p$:**  
  Falls $\vec{x}$ nicht konstant ist, wird jedes zyklische Verschieben ein neues Element erzeugen.  

---

**Fazit:** $f$ ist tatsächlich eine Gruppenwirkung auf $X$, bei der jeder Orbit entweder Größe $1$ oder $p$ hat.  

---
### (iii) Die Orbits partitionieren $X$ in Klassen der Größe 1 und $p$.

- **Behauptung:** $1$ und $p$ sind die einzigen Orbitgrößen.

  - Angenommen $k$ ist auch eine Orbitgröße. Das geht nur, wenn $\vec{x}$ "konstant" ist, also $k = 1$.

- **Behauptung:** Zwei Orbits sind entweder gleich oder disjunkt.

  - Sei $i \to I$, dann:  
    $$
    i \mapsto i + p
    $$

  - Sei $j \to I$, dann:  
    $$
    i \mapsto i + 1
    $$

  - $j \to j$ falls $k, j \in I$ und $x_k = x_j$.  
    Bzw. $p$ ist ein Orbit $\vec{x} \in G$.

#### Anmerkung: 
Die Notation ist klar, aber etwas ungenau. Man könnte sie präzisieren, um den Beweis vollständiger darzustellen.

### ausführlicher: 
### (iii) Die Orbits partitionieren $X$ in Klassen der Größe 1 und $p$.

- **Behauptung:** $1$ und $p$ sind die einzigen Orbitgrößen.

  - Angenommen $k$ ist auch eine Orbitgröße. Das geht nur, wenn $\vec{x}$ "konstant" ist, also $k = 1$.

- **Behauptung:** Zwei Orbits sind entweder gleich oder disjunkt.

  - Sei $i \to I$, dann:  
    $$
    i \mapsto i + p
    $$

  - Sei $j \to I$, dann:  
    $$
    i \mapsto i + 1
    $$

  - $j \to j$ falls $k, j \in I$ und $x_k = x_j$.  
    Bzw. $p$ ist ein Orbit $\vec{x} \in G$.

#### Anmerkung: 
Die Notation ist klar, aber etwas ungenau. Man könnte sie präzisieren, um den Beweis vollständiger darzustellen.

---

### (iv) $p$ teilt $|X|$, also ist die Anzahl der $p$-elementigen Orbits $kp$ für ein $k \in \mathbb{N}$.

#### Idee:
Da wir wissen, dass die Orbits nur Größen $1$ oder $p$ haben, betrachten wir nun deren Anzahl.

- Sei $m$ die Anzahl der Orbits der Größe $1$.  
- Sei $n$ die Anzahl der Orbits der Größe $p$.  
- Da die Orbits $X$ partitionieren, gilt:
  $$
  |X| = m \cdot 1 + n \cdot p = m + np
  $$

---

#### Überlegung:
- Da $p$ ein Primfaktor von $n$, wissen wir aus Teil (i):
  $$
  |X| = n^{p-1}
  $$
  Also ist:
  $$
  p \mid |X|
  $$

- Einsetzen der Partitionierung:
  $$
  p \mid m + np
  $$

- Da $p$ ein Primfaktor ist, teilt $p$ auch den Summanden $np$, also folgt:
  $$
  p \mid m
  $$

- Das bedeutet, dass es ein $k \in \mathbb{N}$ gibt, sodass:
  $$
  m = kp
  $$

---

**Fazit:** Die Anzahl der $p$-elementigen Orbits ist $kp$ für ein $k \in \mathbb{N}$.  

---

### (v) $|\mathbb{Z}_p \cdot \vec{x}| = 1$ ⇔ $\vec{x} = (g, \ldots, g)$ für ein $g \in G$.

#### Behauptung: $|\mathbb{Z}_p \cdot \vec{x}| = 1$ genau dann, wenn $\vec{x}$ konstant ist.

---

**Hinrichtung:**  
Angenommen, $\vec{x} = (g, \ldots, g)$ für ein $g \in G$.  
- Unter der Wirkung von $\mathbb{Z}_p$ wird jeder Zyklus $\vec{x}$ auf sich selbst abgebildet.  
- Daher ist der Orbit von $\vec{x}$ genau $\{\vec{x}\}$.  
- Also gilt:
  $$
  |\mathbb{Z}_p \cdot \vec{x}| = 1
  $$

---

**Umkehrung:**  
Angenommen, $|\mathbb{Z}_p \cdot \vec{x}| = 1$.  
- Das bedeutet, dass $\vec{x}$ invariant unter jeder Verschiebung durch $\mathbb{Z}_p$ ist.  
- Insbesondere gilt:
  $$
  f(k, \vec{x}) = \vec{x} \quad \text{für alle } k \in \mathbb{Z}_p
  $$
- Das bedeutet, dass alle Einträge von $\vec{x}$ identisch sind:
  $$
  \vec{x} = (g, g, \ldots, g)
  $$
  für ein $g \in G$.

---

#### Fazit:  
Die einzigen Orbits der Größe $1$ sind die konstanten $p$-Tupel $\vec{x} = (g, \ldots, g)$.  

Da $m = kp$ ein Vielfaches von $p$ ist, muss es mindestens $p$-viele konstante $\vec{x} \in X$ geben.

---

### (vi) Schließen Sie $\langle g \rangle \cong \mathbb{Z}_p$.

#### Behauptung: Es existiert ein $g \in G$ mit $\langle g \rangle \cong \mathbb{Z}_p$.

---

**Betrachtung:**  
- Betrachte das konstante Tupel $\vec{x} = (g, g, \ldots, g) \in X$.  
- Da $\vec{x} \in X$, muss gelten:
  $$
  g \cdot g \cdot \ldots \cdot g = 1_G
  $$
  Das sind $p$-viele $g$, also:
  $$
  g^p = 1_G
  $$

---

#### Erzeugende Untergruppe $\langle g \rangle$

- Die Untergruppe $\langle g \rangle \subseteq G$ ist gegeben durch:
  $$
  \langle g \rangle = \{ 1_G, g, g^2, \ldots, g^{p-1} \}
  $$

- Da $g^p = 1_G$, ist die Ordnung von $g$ höchstens $p$.  
- Wenn $g$ die Ordnung $p$ hat, ist $\langle g \rangle \cong \mathbb{Z}_p$.  

---

#### Schlussfolgerung

- Da $p$ ein Primfaktor von $n = |G|$, existiert ein Element $g \in G$ mit $\langle g \rangle \cong \mathbb{Z}_p$.  
- Dies folgt aus dem zuvor gezeigten Argument, dass es mindestens $p$-viele konstante Tupel gibt.  
- Insbesondere ist $\langle g \rangle$ eine zyklische Untergruppe der Ordnung $p$.  

---

**Endgültige Aussage:**  
$$
\langle g \rangle \cong \mathbb{Z}_p
$$
