# UE: 14.1-7n, $|B| = k$, $|A| = n$

**Datum:** 06.03.2025  

- $f: A \to B$ (Sehr unscheinbar)  
- Reflexion: **Partielle (Reflexive) Ordnung** $(M, \leq)$  

- $\forall x, y, z \in M$
  - $x \leq x$
  - $x \leq y \land y \leq z \implies x \leq z$
  - $x \leq y \land y \leq x \implies x = y$

---

### Menge $X$ und VR

- $X$ Menge  
- $V$ VR  
- $P(X), \subseteq$  
- $V = (U \cup V, \subseteq)$  
- $\{U \, | \, U \subseteq V\}$  

---

### Hasse-Diagramm Beispiel

- $X = \{1,2,3,4,6,12\}$  
```plaintext
          12
       /  |  \
      6   4   3
       \ / \ / 
        2   1
# UE: Satz
```


**Satz:** Wenn $(P, \leq)$ jede Teilmenge ein Inf hat, dann ist $(P, \leq)$ vollständig.  
**Beispiel:** Sei $X$ Menge, $P = P(X)$, $\leq = \subseteq$.  
- $(P, \leq)$ ist vollständig $\implies$ HD $\subseteq P(X)$

---

### Beweis

- Sei $V = VR / \leq$  
- $U = \{ U \mid U \subseteq V \}$  
- $\sup A = \bigcup_{U \in A} U$  
- $U = \{ U_1, U_2, \ldots \} \implies \bigcup_{i \in I} U_i$  

- $\sup \{ a, b \} = a \cup b$  
- $\inf \{ a, b \} = a \cap b$  
- $\inf \{ a, b, c \} = a \cap b \cap c$  

---

### Definition: Verbandsordnung / Verbände

- $(P, \leq)$ HO heißt **Verbandsordnung**, wenn $\forall x, y \in P$:  
  - $\inf \{ x, y \}$ existiert.  
  - $\sup \{ x, y \}$ existiert.  

- **Beispiel:** $X = \{ 1, 2, 3, 4, 6, 12 \}$  

```plaintext
        12
       /  \
      6    4
     / \  / \
    3   2    1
```

    sup(x, y, z)
       /     |     \
      x      y      z

$t \geq x, \, t \geq y, \, t \geq z$
$\implies t \geq \sup(x, y)$
$\implies t \geq \sup(x, y, z) = s$
# Algebra

Eine **Algebra** ist eine Menge, die mit einer Familie aus Operationen ausgestattet ist.

---

## Definition: Algebra

Sei $A$ eine Menge, $n \in \mathbb{N}_0$.  
Eine **n-stellige Operation** auf $A$ ist eine Abbildung:

$$f: A^n \to A$$

---

### Beispiele

- $+$ ist eine $2$-stellige Operation auf $\mathbb{R}$  
- $-$ ist eine $2$-stellige Operation auf $\mathbb{R}$  
- $-$ ist eine $1$-stellige Operation auf $\mathbb{R}$  
- $x \mapsto x$ ist eine $1$-stellige Operation auf $\mathbb{R}$  
- $x, y \mapsto (x, y)$ ist eine $2$-stellige Operation auf $\mathbb{R}$  

---

### Weiteres Beispiel

- **2-stellige Operation** auf $\mathcal{P}(X)$:  
  $$(x, y) \mapsto x \cup y$$

- **1-stellige Operation** auf $\mathcal{P}(X)$:  
  $$x \mapsto A \setminus x$$

---

## Projektionen

Sei $X$ Menge: $(X_i)_{i \in I} = X$.  

$$\pi^3: X \to A^3 \implies \text{Projektion auf die 3. Koordinate}$$  

- Identitäten verketten sich.  
- Beispiel: $f(1) = a, f(2) = b$  
- Ist isomorph zu $A$.  

---

### Nullstellen

$$A^0 = \{ f | f: \emptyset \to A \} = A$$  

$$A^1 = \{ f | f: A \to A \}$$  

---

## Gruppen

Eine **Gruppe** $G = (G, *)$ besteht aus:

- **Gruppenaxiome:**  
  - $0$-stellige Operation.  
  - $0$-stellig $\implies$ Neutrales Element $e$.  
  - $1$-stellige Operation $\implies$ Inverses Element $a^{-1}$.  

---

### Beispiel: Zyklische Gruppe

$$\mathbb{Z} / \text{mod } 12$$ - Zyklische Gruppe  
- $S_5 = \{1, 2, \ldots, 120\}, -1 \implies \mathbb{Z} / 120 \text{ weil kommutativ}$  

---

### Darstellung als Kartesisches Produkt

$$\mathbb{Z} / 12 \times \mathbb{Z} / 12 = \{(0,0), (1,1), (0,1), (1,0)\}$$  

$$\mathbb{Z} / 12 \times \mathbb{Z} / 32 \cong \mathbb{Z}_6$$  

# Algebra

---

## Körper

Ein **Körper** $(K, +, 0, -, \cdot, 1, ^{-1})$ erfüllt:

- $(K, +, 0, -)$ ist eine **kommutative Gruppe**  
- $(K \setminus \{0\}, \cdot, 1, ^{-1})$ ist eine **Gruppe**  
- Distributivgesetz:  
  $$ x \cdot (y + z) = x \cdot y + x \cdot z $$

---

### Beispiele

- $(\mathbb{R}, +, 0, -, \cdot, 1, ^{-1})$ ist ein **kommutativer Körper**.  
- $(\mathbb{Z}, +, 0, -, \cdot)$ ist ein **Ring**, aber kein Körper.  
- $(\mathbb{Q}, +, 0, -, \cdot, 1, ^{-1})$ ist ein **Körper**.  

---

## Ring

Ein **Ring** ist eine Menge $R$ mit zwei Operationen $(+, \cdot)$, die folgende Eigenschaften erfüllen:

- $(R, +)$ ist eine **abelsche Gruppe**.  
- **Assoziativgesetz:** $(x \cdot y) \cdot z = x \cdot (y \cdot z)$  
- **Distributivgesetz:**  
  $$ x \cdot (y + z) = x \cdot y + x \cdot z $$

---

### Kommutativer Ring

Ein **kommutativer Ring** ist ein Ring, bei dem zusätzlich gilt:  
$$x \cdot y = y \cdot x$$  

---

### Zusammenfassung

| Eigenschaft | Beschreibung |
|-------------|--------------|
| Ring        | Ohne neutrales Element. |
| Ring+       | Ring mit neutralem Element. |
| Ring*       | Ring mit Inversen. |
| Ring        | Normaler Ring. |

---

## Verbandsgeordnete Menge

Sei $(P, \leq)$ eine **verbandsgeordnete Menge**:

- $x \land y = \inf(x, y)$  
- $x \lor y = \sup(x, y)$  

### Eigenschaften

- $x \land y = y \land x$ (Kommutativ)  
- Assoziativität:  
  $$ (x \land y) \land z = x \land (y \land z) $$  
- **Idempotenz:**  
  $$ x \land x = x $$  
  $$ x \lor x = x $$  
- **Inversenelemente:**  
  $$ x \land (x \lor y) = x $$  
  $$ x \lor (x \land y) = y $$  

---

### Verband: Wenn 2 Operationen existieren

- $x \leq y \iff x \land y = x$ (Infimum)  
- $x \lor y = y$ (Supremum)  