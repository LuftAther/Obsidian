# Die Induktion (Die natürlichen Zahlen)
**Datum:** 07.03.2025

- **Definiere eine Menge:**  
  $M : \{n \in \mathbb{N}\}$  
  $U \in M$  
  Wenn $(n \in M) \implies (n+1 \in M)$  

  Dann $M = \mathbb{N}$

---

### Supremum
- $A \subseteq B$, $|A| = n \implies |A| = 0 \implies B = \emptyset$, $B \in A$  
- $|A| = n+1 \implies k, j \in \mathbb{N}$, $j \leq n \implies B$ aufsteigend sortiert $(a_0, a_1, \ldots, a_n)$  
- $|A| = 0$  
  - $\emptyset \in U$  
- $|A| = 1$  
  - $|A'| = 0$  
- $|A| = 2$  
  - $|A'| = 1$  

---

### Goldstroms Lieblingsturmel

1. $x^2 = 1 \implies x = \pm 1 \implies (x - 1)(x + 1) = 0$
2. In $\mathbb{Z}$:
   - $a, b \implies a \cdot b = 0 \implies a = 0 \lor b = 0$
   - $x = -1 \lor x = 1 \lor x = 0$
3. In $\mathbb{Z} / 24$:
   - $[a] \cdot [b] = 0 \implies 241 \cdot 0$
   - $[ab] = 0 \implies 241 \cdot 0$

---

### Aussagenlogik

- $(A \implies B) \iff (\lnot A \lor B)$, $A \implies B$
# Relationen

- $R \subseteq A \times B = \{(a, b) \mid a \in A, b \in B\}$  

- Beispiel für Relationen:  
  - $x \leq y \implies T = \{(x, y) \in \mathbb{Z} \times \mathbb{Z} \mid x \leq y\}$  
  - $x < y \implies S = \{(x, y) \in \mathbb{R} \times \mathbb{R} \mid x < y\}$  

- **Relation $V$:**  
  $V = \{(x, y) \in \mathbb{Z} \times \mathbb{Z} \mid x \leq y\}$  

---

### Funktion

- $\implies f: A \to B$ ist eine Funktion von $A \to B$  
  - $f \subseteq A \times B$  
  - $\forall a \in A \, \exists! \, b \in B: (a, b) \in f$  

- Wenn $f: A \to B$, dann $f^{-1}: B \to A = \{(y, x) \mid (x, y) \in f\}$ ist dann $g$ eine Funktion.  
  - $f$ dann **wenn** $f$ injektiv ist.  
  - Funktion $\implies$ Relation, aber Relation $\centernot\implies$ Funktion.  

---

### Abbildung

- $\implies f: A \to A$  
  - **Scherung:** $f: \mathbb{Z} \to \mathbb{Z}, \, v \mapsto \mathbb{Z} - vc$  

---

### Partition

- $P = \{A_1, \ldots, A_i, \ldots\}$  
  - $A_i \neq \emptyset$  
  - $\bigcup_{i \in I} A_i = A$  
  - $A_i \cap A_j = \emptyset \, \forall \, i \neq j$  

---

### Partielle Ordnung

- $(\mathbb{N}, R)$, Lineare Ordnung (Totalordnung)  
- $R$ ist:
  - Reflexiv  
  - Transitiv  
  - Antisymmetrisch  
  - $\forall x, y \in X, \, x R y \land y R x \implies x = y$  
- Partielle Halbordnung

---

### Strukturelle Halbordnung

- **Eigenschaften:**
  - Transitiver  
  - Asymmetrisch  
  - $\forall x, y \in X, \, x R y \implies \lnot (y R x)$  

---

### Beispiel

- Menge: $\{(a, b), (b, a), (a, c), (b, d), (c, d), (a, d)\}$  
- Nur für zeitliche partielle Bindungen.  
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
# Ordnungrelationen

**Datum:** 18.03.2025

### Definition: Ordnungsrelation

Sei $M$ eine Menge. Eine Ordnungsrelation ist:  
- **Reflexiv:** $\forall x \in M, \, x R x$  
- **Transitiv:** $\forall x, y, z \in M, \, (x R y \land y R z) \implies x R z$  
- **Antisymmetrisch:** $\forall x, y \in M, \, (x R y \land y R x) \implies x = y$  

---

### Hinweis zu Asymmetrie

Wenn $\forall x, y \in M, \, x R y \implies \lnot (y R x)$, dann ist $R$ **asymmetrisch**.  

---

### Kette und Antikette

- **Kette:** Linear geordnete Menge = total geordnete Menge.  
- **Antikette:** Je zwei Elemente sind unvergleichbar.  

---

### Lineare Ordnung

Eine lineare Ordnung $(L, \leq)$ heißt **Noethersch**, wenn:  

$$\forall (x_i) \in L: \, \exists n \in \mathbb{N}: \, x_n \leq x_{n+1}$$  

**Beispiel:** $(-\infty, 0] \subseteq \mathbb{Z}$  

---

### Arthinsche Ordnung

$$\{y_1, y_2, \ldots, y_n\} \subseteq \mathbb{L}^{\mathbb{N}} \, \text{mit} \, x_i < x_j$$  

**Beispiel:** $\mathbb{N}$  

---

### Satz

Wenn $L$ Noethersch und Arthinsch, dann ist $L$ endlich.  

---

## 2.1.3 Operationen

Betrachte **n-stellige Operationen** auf $A$:  
$$f: A \to B$$  
$$A \to B$$  

Dann heißt $f$ **invertierbar**, wenn:  
$$f \circ g = id_A \quad \text{und} \quad g \circ f = id_A$$  

---

### Eigenschaften

- **Kommutativ:**  
  $$\forall x, y \in A, \, f(x, y) = f(y, x)$$  
  Beispiel: $x + y = y + x$  

- **Assoziativ:**  
  $$\forall x, y, z \in A, \, f(f(x, y), z) = f(x, f(y, z))$$  
  Vorteil: Man kann Klammern weglassen.  
  Beispiel: $f(x, y, z) = x + y + z$  

---

### Notation

- **Infixnotation:** $x + y$  
- **Präfixnotation (Polnische Notation):** $+xy$  
- **Postfixnotation (Umgekehrte Polnische Notation):** $xy+$  

---

### Wichtige Definition

$$A^n = \{f \mid f: A^n \to A\}$$  
- Beispiel:  
  - Linksinverses $g$: $g \circ f = id_A$  
  - Rechtsinverses $g$: $f \circ g = id_A$  
  - Linksinverses $\implies$ injektiv  
  - Rechtsinverses $\implies$ surjektiv  
# UE: Assoziativität

$$* : M \times M \to M \quad \text{assoziativ}$$  
$$\forall x_1, x_2, \ldots, x_n \in M: \, (x_1 * x_2) * \ldots * x_n = x_1 * (x_2 * \ldots * x_n)$$  
$$ = x_1 * x_2 * \ldots * x_n$$

**Klammersetzung bei Möglichkeit:** Beweis durch Induktion.

---

## 2.1.4 Relationale Strukturen

- **Äquivalenzrelationen**
- **Partielle Ordnung (HO)**
- **Verband**
  - **Vollständiger Verband**
  - **Lineare Ordnung**

---

### Verträglichkeitsaxiome

**Angeordneter Körper:**  

1. Körper $K = (\mathbb{R}, +, \cdot, 0, 1)$  
2. Lineare Ordnung $\leq$  
3. $a \leq b \implies a + x \leq b + x$  
4. $a \leq b, \, 0 \leq x \implies ax \leq bx$  

---

### Satz

**Satz:** Auf $\mathbb{C}$ gibt es keine verträgliche Ordnung.  

---

## 2.1.8 Terme

### Variablen

$$ X = \{ x_1, x_2, x_3, \ldots \} $$  

---

### Sprache

Wir interessieren uns für **Algebren** (Menge mit Operationen) der Form $(M, f, g)$ vom Typ $(2, 1)$.  

---

### Terme

- **Terme:** $x_i \in T_0$  
- $\omega_2(x_1, x_3) \in T_1$  
- $\omega_1(\omega_2(x_1, x_3)) \in T_2$  

---

### Definition: Term

- **Term:** Jede Variable ist Term **0-ter Stufe**.  
- $T_0 = X$  
- $T_{n+1} = T_n \cup \{ \omega(s, t) \mid s, t \in T_n \}$  

Insbesondere, wenn $\omega$ **0-stellig**, dann $w \in T$.  

- Term mit Stufe höchstens $n+1$  
- $$ T = \bigcup_{n \in \mathbb{N}} T_n $$  

---

### Beispielbaum

```plaintext
               ω1
             /    \
           ω2      x1
         /    \
        x1     x3
```


# Termalgebra

**Datum:** 13.03.2025  

---

## Definition

Eine Termalgebra wird definiert durch:  

- $I$: Indexmenge  
- $\omega_i \in I$: Operationen mit Typ $\text{Typ} = (\nu_i, \epsilon_i)$  

---

## Sprache

Sei $\mathcal{A} = (A, (\omega_i)_{i \in I})$ eine **Algebra dieses Typs**.  

- $\omega_i^n : A^n \to A$  
  - $n_i$-stellige Operation  

---

### Variablenmenge

$$ T = X \, (\text{Variablen}) = \{x_1, x_2, \ldots\} $$

$$ T_{n+1} = T_n \cup \bigcup_{i \in I} \omega_i(t_1, \ldots, t_n) \quad \text{mit} \quad t_1, \ldots, t_n \in T_n $$

$$ T = \bigcup_{n} T_n $$

---

### Beispiel

- $x + y \in T$  
- $(x + y), (z + t) \in T_2$  
- Beispielterm:  
  $$ (((x - y) + (y - z)) + (x - t)) + (y - z) $$  
  - **Stufe:** $5$  

---

## 2.1.8.4 Beweis skizzieren

Wir haben Sprache $L$ und $T = $ Termalgebra zur Sprache $L$ aufgebaut auf $X$ (Variablenmenge).  

$$ \mathcal{A} = (A, (\omega_i)_{i \in I}) \quad \text{Algebra} $$  

Sei $f: X \to A$, dann gibt es genau einen Homomorphismus $h: T \to A$, sodass:

$$ \forall x \in X: \, h(x) = f(x) $$  

---

### Definition für $i \in I$

Für $i \in I$ ist $\omega_i: T^n \to T$ definiert durch:

$$ \omega_i(t_1, \ldots, t_n) = \omega_i(t_1, \ldots, t_n) $$  

- Links: Tatsächliche Funktion  
- Rechts: Symbolische Darstellung  

# Beweis: $f = \alpha$

### Gegeben

- $f: X \to A$  
- $\alpha_0: T_0 \to A$  
- $\alpha_n: T_n \to A$  
- $T = \bigcup_{n \in \mathbb{N}} T_n$  

---

### Definition

$$\alpha(t) = \alpha_n(t) \quad \text{wenn} \quad t \in T_n$$  

---

### Konstruktion

- Sei $t = \omega_i(t_1, \ldots, t_n)$  
- $$\alpha_{n+1}(t) = \omega_i^A(\alpha_n(t_1), \ldots, \alpha_n(t_n))$$  

- $\alpha_{n+1}: T_{n+1} \to A$  

---

### Rekursive Definition

$$ \alpha = \bigcup_{n \in \mathbb{N}} \alpha_n $$  

---

### Erweiterung

$$ \alpha(t) = \alpha_n(t) \quad \text{wenn} \quad t \in T_n $$  
$$ \alpha_{n+1}(t) = \omega_i^A(\alpha_n(t_1), \ldots, \alpha_n(t_n)) $$  

---

### Beweis, dass $\alpha$ ein Homomorphismus ist

1. Nach Konstruktion ist $\alpha$ ein Homomorphismus.  
2. $\alpha$ setzt $f$ fort.  

---

### Wohldefiniertheit

- Beispiel: $f: \mathbb{R}^+ \to \mathbb{R}$  
- $$ f(x_1) = x_1, \, f(x_2) = x_2 $$  
- $$ f(x_1 + x_2) = x_1 + x_2 $$  
- $$ f(x_1 + x_2) = x_1 + x_2 = x_2 + x_1 $$  

- **Wohldefiniertheit bedeutet:** Die Definition ist unabhängig davon, wie der Term erzeugt wurde.  

---

### Wichtig!

Nicht $g(x_i) = g(x_j)$ statt $|x_i| = |x_j|$, weil wir noch nicht wissen, ob $\alpha$ wohl definiert gültig ist.  

---

### Notiz

**Termalgebra praktisch um Gesetze aufzuschreiben:**  

- $I = \{1, 2, 3\}$  
- $\nu_i = (2, 1)$  
- $\omega_i$: $+$, $\cdot$  
- Auf **Zeichen paar 3 wird auf $\mathbb{N}$ abgebildet**.  
# 2.1.8.6 Gesetze

---

## Gesetze

Ein **Gesetz** ist ein Tupel:  
$$(t_1, t_2) \in T \times T$$  

Beispiel (Kommutativgesetz):  
$$(x \cdot y, y \cdot x)$$  

- **Nicht so aufzuschreiben:**  
  $$ x \cdot y = y \cdot x $$  
- **So aufzuschreiben (effizient):**  
  $$ \alpha = (A, \omega_i, \ldots) \implies x \cdot y = y \cdot x $$  

---

### Kette: $a \cdot b \cdot a$

---

## Erklärung

Für jede Abbildung $\alpha: \{x_i, y_j\} \to A$ gilt:  

- $T(t_1, t_2)$ (Termalgebra auf $\{x_i, y_j\}$) ist erfüllt durch $\alpha$, wenn:  
  $$ \alpha(t_1) = \alpha(t_2) $$  

- Anderer Ausdruck:  
  $$ T(t_1, t_2) \implies \forall \alpha: \alpha(t_1) = \alpha(t_2) $$  

---

### Gruppengesetze

- **Gruppen Gesetze:**  
  - $(\mathbb{Z}, +)$ erfüllt Gruppenaxiome.  
  - **Achtung:** Gruppenaxiome führen nicht automatisch zu einer Algebra.  
  - Algebra + Operationen $\nRightarrow$ Algebra.  

---

## Modelle

Sei $\Sigma$ eine Menge von Gesetzen.  

- **Modelle:**  
  $$\text{Modelle}(\Sigma) = \{ A \mid A \text{ ist Algebra vom Typ } (n_i)_{i \in I} \land \forall \kappa \in \Sigma, A \models \kappa \}$$  

- Alternativ:  
  - **Gleichungsdefinierte Masse** genannt **Varietät**.  
  - Klasse der Gruppe ist Varietät.  
  - Klasse der Ringe ist Varietät.  
  - Klasse der Körper ist nicht Varietät.  

---

### Beispiel: $\mathbb{Z}_5$ als VR

- $\mathbb{Z}_5 = \{0, 1, 2, 3, 4\}$  
- Operationen:  
  - $m_0, m_1, m_2, m_3, m_4$  
  - $m_0(x + y) \approx m_0(x) \approx m_0(y)$  
  - $m_3(m_3(x)) \approx m_1(x) \approx X$  

---

### Notiz

- **Körper kann man nicht durch Gesetze beschreiben**, weil **Produkt von Körpern kein Körper** ist.  
- **$\mathbb{Z}, (+, -)$** ist eine reine richtige Gruppen-Definition für uns, nur **$ (\mathbb{Z}, +, -) $** ist zulässig.  
# 2.1.2.1 Unteralgebren

---

## Definition: Unteralgebra

Sei $\mathcal{A} = (A, f_i)_{i \in I}$ eine Algebra.  
$U \subseteq A$ heißt **Unteralgebra**, wenn:  

1. $\forall i \in I, \, U \subseteq A \implies f_i(U) \subseteq U$.  
2. $U = \{U_1, U_2, \ldots\}$, wobei $U_i \subseteq A$.  

---

### Untergruppen von $\mathbb{Z}$

- $\mathbb{Z} \subseteq \mathbb{Z}$  
- $2\mathbb{Z} \subseteq \mathbb{Z}$  
- $3\mathbb{Z} \subseteq \mathbb{Z}$  
- $7\mathbb{Z} \subseteq \mathbb{Z}$  

---

### Definition: Unteralgebra

Sei $\mathcal{A}$ Algebra, $U \subseteq A$.  
Dann ist $(U, (f_i)_{i \in I})$ eine **Unteralgebra**.  

---

## Satz 1: Eigenschaften

Sei $\mathcal{A} = (A, f_i)_{i \in I}$ und $U \subseteq A$. Dann gilt:  

- $\mathcal{U} = (U, (f_i)_{i \in I})$ ist eine Unteralgebra.  
- Jede Varietät ist unter Unteralgebren abgeschlossen.  

---

### Hülle

Sei $\mathcal{A}$ Algebra, $S \subseteq A$.  
Die **Hülle** von $S$ ist definiert durch:  

$$ \langle S \rangle = \bigcap \{ U \subseteq A \mid S \subseteq U \, \text{und} \, U \, \text{ist Unteralgebra} \} $$  

- **Notation:** $\langle S \rangle$ ist die kleinste Unteralgebra, die $S$ umfasst.  

---

## Lemma

Der Durchschnitt von beliebig vielen Unteralgebren ist wieder eine Unteralgebra.  

$$ f \subseteq \bigcup S(t) $$  
$$ \forall n \in \mathbb{N}, \, \forall j \in J, \, \forall f_j: f \in U_j $$  
$$ \{ U_i \mid U_i \subseteq A, \, f_i(U_i) \subseteq U_i \} $$  

---

## Beispiel

- $V = \{x, y \in V \mid x + y \in V\}$  
- Beispiel anhand Spezialfall: $+ A \times A \to A$  
- Sei $U \subseteq A$, $x, y \in U \implies x + y \in U$  

---

## Alternative Charakterisierung

**Betrachte alle möglichen Terme.**  

- Beispiel: $2x + y = m_2(m_1x, y)$  

---

### Termalgebra

Betrachte $t \in T$ mit verwendeten Variablen $x_1, x_2, x_3$.  

$$ \alpha': \{x_1, x_2, x_3\} \to A $$  
$$ \alpha(t) \to A $$  

$$ \alpha'(t) = \alpha(t) \in A $$  
# Umgekehrt

Sei $t$ ein fester Term, dann definiert $t^A: A^n \to A$ eine Operation.  

$$ t = \omega_i(x_1, \ldots, x_n) $$  
$$ t^A(a_1, \ldots, a_n) = \omega_i^A(a_1, \ldots, a_n) $$  

---

## Definition

Sei $S \subseteq A$.  

### Satz: Direkte Erzeugung

$$ \langle S \rangle = \bigcup_{n \in \mathbb{N}} \{t^A(s_1, \ldots, s_n) \mid t \, \text{Term verwendet} \, \{x_1, \ldots, x_n\}, \, s_i \in S\} $$  

- Mit Induktion kann man beweisen, dass diese Menge endlich ist.  

---

## Erzeugendensystem

Sei $E \subseteq A$, dann erzeugt $A \leftrightarrow \langle E \rangle = A$  

---

### Beispiel

- $E = T_0 = X$  
- Für $E = \{1\}$ gilt:  
  $$ \langle E \rangle = (\mathbb{Z}, +, 0, 1, -) $$  
  $$ \langle E \rangle = \mathbb{Z} $$  
- Gruppe $(G, \cdot, 1, \ldots)$  

---

## UE: Satz

Seien $\mathcal{A}, \mathcal{B}$ Algebren vom gleichen Typ, $h_1, h_2: A \to B$ Homomorphismen, $E \subseteq A$.  

Wenn:  
- $h_1|_E = h_2|_E$ (Einschränkung auf $E$)  

Dann:  
$$ h_1\langle E \rangle = h_2\langle E \rangle $$  

**Ergibt Eindeutigkeit**  

---

## Beweis Skizze

- Betrachte:  
  $$ U = \{a \in A \mid h_1(a) = h_2(a)\} \supseteq E $$  
  (Menge auf der wir übereinstimmen)  

- **Behauptung:**  
  $$ U \subseteq A, \, \text{sei} \, i \in I, \, a_1, \ldots, a_n \in U \implies \omega_i^A(a_1, \ldots, a_n) \in U $$  
# HOM UE Anmerkung

**Datum:** 19.03.2025

---

## Bedingungen

Wenn $(P, \leq)$ HO, $U \subseteq P$, dann:  

1. $\forall A \subseteq P, \, \exists n \in \mathbb{N}, \, A \subseteq P \implies A \subseteq \bigcup_{i=1}^n U_i$  
2. $U \subseteq P$ ist eine Algebra $(A, (f_i)_{i \in I})$  

---

### Definition: Unteralgebra

$$ \text{Sub}(A) = \{U \subseteq A \mid U \, \text{ist unter allen Operationen abgeschlossen} \} $$  

- Subalgebren sind **partiell geordnet** und für alle Funktionen $f: S \to S$ gilt:  
  $$ f(S) \subseteq S $$  

---

### Supremum und Infimum

$$ S = \bigcap \{ V \in \text{Sub}(A) \mid V \supseteq U \} = \bigcup \{ V \subseteq A \mid V \subseteq U \} $$  

---

## Permutationen

### Definition

$$ \text{Sym}(M) = \{ \text{Permutation von } M \mid M \to M \text{ bijektiv} \} $$  

- **Bijektive Funktion:** Keine Verdopplung, keine Einermengen.  
- $(\text{Sym}(M), \text{id}_M, \circ)$ ist eine **Gruppe**.  

---

### Beispiel

- Sei $M = \{1, 2, 3, 4, 5, 6\}$  
- $\text{Sym}(M) = S_6$  

---

### Zyklenschreibweise

| Zykel | $\pi(x)$ |
|-------|----------|
| 1     | 3        |
| 2     | 4        |
| 3     | 5        |
| 4     | 6        |
| 5     | 2        |
| 6     | 1        |

---

### Produkt zur Darstellung

**Beispiel:** $(123)(12) = (23)$ (Permutation Produkt)  

---

### Schreibweisen

1. **Schreibweise:** $(1 \, 2 \, 3 \, 4 \, 5 \, 6)$  
2. **Schreibweise:** $(135624)$  
3. **Schreibweise:**  
   $$(1)(352)(4)(6) \, \circ \, (225)(46) \, \circ \, (234561) \, \circ \, (136)$$  

---

### Produkt

- **Notiz:** Produkt ist meist endlich, auch wenn explizit dazu geneigt.  

---

### Schreibweise für $ \circ $ (Komposition)

- $y \to f(x)$  
- $g(f(x))$  
- $(g \circ f)(x)$  

- $y = x$  
- $(x + f) = x + f \neq 0$  

# Multiplikative & Additive Gruppen

---

## Notizen

### Multiplikative Gruppe
Sei $(G, \cdot, 1, ^{-1})$:

- Neutrales Element: $1$
- Inverses Element: $a^{-1}$
- Assoziativität: $(a \cdot b) \cdot c = a \cdot (b \cdot c)$

### Additive Gruppe
Sei $(G, +, 0, -)$:

- Neutrales Element: $0$
- Inverses Element: $-a$
- Assoziativität: $(a + b) + c = a + (b + c)$

---

### Notiz

Oft betrachtet man **Ringe mit 1**: $(R, +, \cdot, 0, 1, -)$  
- **Multiplikation:** $x \cdot x \cdot x \cdot x$  
- **Addition:** $x + x + x + x$

---

## Wichtige Rolle

Spielen auch **nullteilerfreie Ringe**:  

$$ \forall x, y \in R: x \cdot y = 0 \implies (x = 0 \, \text{oder} \, y = 0) $$  

**Beispiel:** $\mathbb{R}$, $\mathbb{Z}$ sind nullteilerfrei.  

---

## WDH Ring

$$(R, +, 0, -, \cdot)$$  

- **Additiv:** Von Gruppe  
- **Multiplikativ:** Von Halbring  

---

## 2.1.3.7 Halbgruppe & Monoid

### Definition: Halbgruppe

$(H, \cdot)$ ist eine Halbgruppe, wenn:  

- Assoziativität: $(x \cdot y) \cdot z = x \cdot (y \cdot z)$  

---

### Definition: Monoid

$(H, \cdot, 1)$ ist ein Monoid, wenn:  

- Assoziativität gilt.  
- Es gibt ein neutrales Element $1$: $x \cdot 1 = x = 1 \cdot x$  

**Hinweis:** Es gibt partielle Algebren, in denen wir totale Funktionen betrachten.  

---

## Beispiel: Gruppen & Monoid

Sei $G$ Gruppe $(G, \cdot, 1, ^{-1})$. Sei $U \subseteq G$ eine **Unteralgebra**.  

- $U = \{u \in G \mid \text{Untergruppe}\}$  
- Eingeschränkt auf $U$:  
  - $U \subseteq G$: Untergruppe  
  - $U \neq G$: Monoid  

---

### Beispiel: Monoid

Betrachte $\{0, 1\}, \cdot$ Monoid:

- **Unteralgebra:**  
  - $\{3\}, \cdot$ ist rein, weil $1$ fehlt.  
  - $\{0, 1\}, \cdot$ ist Unteralgebra.  

- **Monoid für sich:** $\{0, \cdot\}$  
# Gesetze

---

### Multiplikativgesetz

$$ x \cdot y = y \cdot x $$  

---

## Beispiel: $\mathbb{Q}$ als VR

$$(V, +, 0)$$ ist ein Vektorraum.  

- **Beispielmenge:** $\{m, c \mid m, c \in \mathbb{Q}\}$  
- **Definition:**  
  $$ m(a) = \min(a, c) \quad \text{und} \quad M(a) = \max(a, c) $$  

---

## Gesetze auf Unteralgebren

Sei:  

$$ G_1 = (G_1, \cdot, 1, ^{-1}) $$  
$$ G_2 = (G_2, \cdot, 1, ^{-1}) $$  

- $G_1 \times G_2 = (G_1 \times G_2, \cdot, 1, ^{-1})$  
- **Definition:**  
  $$ (x_1, x_2) \cdot (y_1, y_2) = (x_1 \cdot y_1, x_2 \cdot y_2) $$  

---

## Bemerkung

Das Produkt einer Gruppe ist eine Gruppe.  

---

### Beispiel

$$(x_1, x_2), (x_1', x_2') \in G_1 \times G_2$$  
$$ 0 = (0, 0) \quad \text{und} \quad x_1 = x_1' \implies (x_1, x_2) = (x_1', x_2') $$  

---

## Satz

Allgemein gilt: Wenn $A, B$ Algebren des gleichen Typs sind und wir beide ein Gesetz $L$ teilen, dann erfüllt auch $A \times B$ (mit komponentenweiser Operation) dieses Gesetz.  

---

### Beweis

**Komponentenweise nachrechnen:**  

---

## Gruppen und Untergruppen

Sei $(G, \cdot, 1, ^{-1})$ eine Gruppe, $U \subseteq G$ eine **Untergruppe**.  

---

### Definition

Für $g \in G$ sei:  
$$ g \cdot U = \{g \cdot u \mid u \in U\} \quad \text{(Nebenklasse)} $$  

---

### Eigenschaften

1. Wenn $g \in U$, dann:  
   $$ g \cdot U = U $$  
2. Wenn $g \notin U$, dann:  
   $$ g \cdot U \neq U $$  
3. **Gliedert man $U$ in disjunkte Mengen auf:**  
   $$ G = \bigcup_{g \in G} g \cdot U $$  
4. **Zusammenhang mit Nebenklassen:**  
   $$ g \cdot g^{-1} = 1 \in U \implies g^{-1} \in U \implies g^{-1} \cdot g \in U $$  
   $$ g \cdot g^{-1} = 1 \in U \implies g^{-1} \cdot U = U $$  

---

### Fazit

Haben jetzt **diese Gliedheit gezeigt**.  
# Untergruppen und Nebenklassen

---

## Beweis

Wenn $g \cdot g^{-1} \in U$, dann sei $u = g \cdot g^{-1}$, dann ist:  

$$ g \cdot g^{-1} = g \cdot u \in g \cdot U $$  

---

## Lemma 1

Wenn $x \in g \cdot U \cap g' \cdot U$, dann gibt es $u, u' \in U$ mit:  

$$ x = g \cdot u = g' \cdot u' $$  
$$ g^{-1} \cdot x = u \in U \implies g \cdot u = g' \cdot u' $$  

---

## Lemma 2

Sei $U \leq G$.  

- Sei $x \in G$, dann ist die Abbildung:  
  $$ \overline{U} \to x \cdot U $$  
  $$ y \mapsto x \cdot y $$  

  **Bijektivität:**  

  - $x \cdot y \in U$  
  - $x^{-1} \cdot y \in U$  

---

## Satz

Wenn $G$ eine **endliche Gruppe** ist und $U \leq G$, dann sind alle $g \cdot U$ gleich groß.  

- **Index von $U$:**  
  $$ [G : U] = | \{ gU \mid g \in G \} | $$  

  Sagt uns, wie viele Nebenklassen es gibt.  

- $$ |G| = |U| \cdot \text{Index} $$  

---

### Beispiel 1

Betrachte $\mathbb{Z} \geq 10 \, \mathbb{Z}$:  

- $0 + U = U$  
- $1 + U = \{ \ldots, -9, -8, \ldots \}$  
- $8 + U = \ldots$  
- $9 + U = \ldots$  

---

### Beispiel 2

$S_3 = \{ \text{id}, (12), (123), (132), (23), (13) \}$  

- **Untergruppe $U_G$:**  
  - $\{\text{id}, (123), (132)\}$  
  - Nebenklassen:  
    - $\{\text{id}, (123), (132)\}$  
    - $\{(12), (23), (13)\}$  

- **Unnormalteiler:**  
  $$ U \text{ ist normalteiler} \iff \forall g \in G: g \cdot U = U \cdot g $$  

---

### Lagranges Satz

**Lagrange:** Muss Teiler von $|S_3| = 6$ sein.  
# WDH: Termfunktion

**Datum:** 20.03.2025  

---

## Definition

Gegeben:  
- Variablen: $x_1, x_2, x_3, \ldots$  
- Belegung:  
  $$
  \begin{aligned}  
  x_1 &\mapsto a \\  
  x_2 &\mapsto a \\  
  x_3 &\mapsto a \\  
  \vdots &\mapsto \vdots  
  \end{aligned}
  $$
- $\mathcal{A}$ Algebra mit $f_i: A^n \to A$  

---

### Termfunktion

- Termfunktion sind Funktionen.  
- Bsp.: $\mathcal{A} = (A, f_1, f_2, \ldots)$  
- Produkt von mehr als zwei (unendlich vielen) Mengen.  

---

## Produkte

### Definition

Sei $(A_i)_{i \in I}$ eine Familie von Mengen.  

$$ A = \prod_{i \in I} A_i = \{f \mid f: I \to \bigcup_{i \in I} A_i, \, \forall i \in I: f(i) \in A_i\} $$  

- Beispiel:  
  - $I = \{1, 2\}$  
  - $A_1 = \{x\}$, $A_2 = \{y\}$  
  - $A = A_1 \times A_2 = \{(x, y)\}$  

---

## Satz

Sei $(A_i, i \in I)$ der Form vom Typ $(2, 1, \lambda)$.  
$\mathcal{A} = (A_i; +, 0, -)$  

**Satz:** Wenn $t_1 \approx t_2$ Gesetze $\forall i \in I: A_i \models t_1 \approx t_2$, dann:  

$$ \prod_{i \in I} A_i \models t_1 \approx t_2 $$  

---

### Beweis

Komponentenweise nachrechnen.  

---

### Produktbildung

Jede **Varietät** ist unter Produktbildung abgeschlossen.  

$$ \prod_{i \in I} A_i \cong A^{-1} = A $$  

---

## Beispiel

$$ \prod_{i \in I} A_i = (T A_i, +, 0, -) $$  

- $x = (x_i)_{i \in I} \in T A_i$  
- $y = (y_i)_{i \in I} \in T A_i$  
- $x + y = (z_i)$, wobei $z_i = x_i + y_i$  
- $0 = (0)_{i \in I}$  

---

## Notiz

**Homomorphismen sind strukturerhaltende Abbildungen.**  
# 2.1.9 Homomorphismen

---

## Definition

Seien $\mathcal{A}, \mathcal{B}$ Algebren des gleichen Typs.  
Ein **Homomorphismus** ist eine Abbildung:  

$$ f: A \to B $$  

sodass für jede Operation $\omega_i$ gilt:  

$$ f(\omega_i^{\mathcal{A}}(a_1, a_2, \ldots, a_n)) = \omega_i^{\mathcal{B}}(f(a_1), f(a_2), \ldots, f(a_n)) $$  

---

### Beispiel

$$ f(a \ast a') = f(a) \ast f(a') $$  
$$ f(0) = 0, \quad f(1) = 1 $$  

---

## Arten von Homomorphismen

- **Epimorphismus:** Surjektiv  
- **Endomorphismus:** $A = B$  
- **Isomorphismus:** Bijektiv (ein Homomorphismus, der eine Bijektion ist)  
- **Automorphismus:** Isomorphismus $A \to A$  

---

### Beispiel

- $\mathbb{Z}$, $+ , 0$  
- $\mathbb{Z}_5$, $+ , 0$  
- Beispiel: $\mathbb{Z}_2 \times \mathbb{Z}_2$ ist **nicht isomorph** zu $\mathbb{Z}_4$.  

---

## Satz

Sei $f: A \to B$, dann gilt:  

$$ f(A) = \{ f(a) \mid a \in A \} $$  

---

### Beweis

Durch **Induktion** oder den allgemeinen Fall gezeigt, dass:  

- $f$ ist unten und abgeschlossen.  
- Für $x, y \in A$:  
  $$ f(x + y) = f(x) + f(y) $$  
  $$ f(x) = y_1 + y_2 \implies f(x) = y_1 + y_2 $$  

---

## Definition: Kern

Eine Funktion $f: A \to B$ hat als **Kern**:

$$ \text{Kern}(f) = \{(a_1, a_2) \mid f(a_1) = f(a_2)\} $$  

---

### Satz: Äquivalenz

Der **Kern** ist äquivalent zu:  

1. $[a] \subseteq A$  
2. $b \in [a] \implies f(a) = f(b)$  
3. $b \in [a] \implies f(a) = f(b)$  

---

### Diagramm

Eine Illustration, die zeigt, dass Äquivalenzklassen in Schichten oder Blöcke zerlegt werden.  

---

### Notiz

- $f(a) = f(a_1) = 0$  
- $f(a - a_2) = 0$  
# Satz: Kern eines Homomorphismus

---

### Satz

Wenn $f: A \to B$ ein Homomorphismus ist, dann ist $\text{Kern}(f) \subseteq A \times A$ eine **Kongruenzrelation** auf $A$.  

---

### Beweis

Für Sprache $\Sigma$:  

- Seien $(a_1, a_2), (b_1, b_2) \in \text{Kern}(f)$  
- $\omega_i^{\mathcal{A}}(a_1, b_1) = \omega_i^{\mathcal{A}}(a_2, b_2)$, da $f(a_1) = f(a_2)$ und $f(b_1) = f(b_2)$.  
- Gültigkeit:  
  $$
  f(a) = f(b) \implies (a, b) \in \text{Kern}(f)
  $$  
  $$
  \text{Kern}(f) = \{(a, b) \mid f(a) = f(b)\}
  $$  

---

## Definition / Vorarbeit: Algebra

Eine Relation $\theta \subseteq A \times A$ heißt **Kongruenzrelation** auf $A$, wenn:

1. $\theta$ ist **Äquivalenzrelation** auf $A$.  
2. $\theta$ ist **Autohomomorphismus** von $A \times A$.  

Für alle Operationen $\omega_i$ auf $A$:  

$$ \forall a_1, \ldots, a_n, b_1, \ldots, b_n \in A $$  

Wenn $(a_i, b_i) \in \theta$ für $i = 1, \ldots, n$, dann:  

$$ \omega_i(a_1, \ldots, a_n) \, \theta \, \omega_i(b_1, \ldots, b_n) $$  

---

### Wohldefiniertheit

- Wenn $a \sim b$, dann:  
  $$ f(a) = f(b) $$  
- Ist $f: A \to B$ ein Homomorphismus, dann ist:  
  $$ \text{Kern}(f) \subseteq A \times A \implies \text{Kern}(f) \text{ ist } \theta $$  

---

## Satz: Homomorphie

1. Sei $f: A \to B$ ein Homomorphismus, dann ist $\text{Kern}(f)$ **kongruent**.  
2. Wenn $\theta \subseteq A \times A$ kongruent, dann gibt es ein $f: A \to A / \theta$ mit folgender Eigenschaft:  
   $$
   f: A \to A / \theta, \quad a \mapsto [a]_{\theta}
   $$  
   $$
   f(\omega(a_1, \ldots, a_n)) = \omega(f(a_1), \ldots, f(a_n))
   $$  
3. $\theta$ ist wohldefiniert.  
4. $\theta$ ist ein Homomorphismus.  

---

## Beispiel: Algebra

$$ \Delta_A = \{(x, x) \mid x \in A\} \text{ ist kongruent.} $$  

---

## Beispiel: Beweis

Sei $B$ eine beliebige einelementige Menge.  
$B - \text{leere}$  
Dann ist:  
$$ f: A \to B \text{ surjektiv.} $$  

---

## Schlussfolgerung

- Wenn $A = B \cup \{x\}$, dann ist:  
  $$
  f(x) = f(y) \implies x = y
  $$  

---

## Diagramm

Eine visuelle Darstellung eines geordneten Sets mit Pfeilen, die zeigen, wie die Elemente durch den Homomorphismus abgebildet werden.  

# WDH: Kongruenzrelationen

**Datum:** 26.03.2025  

---

## Definition: Algebra

Eine Algebra $\mathcal{A} = (A, (\omega_i)_{i \in I})$ mit $(n_i)_{i \in I}$ als ihre Typen und $\omega_i$ als Operationen.  

---

## Definition: Kongruenzrelation

Eine **Kongruenzrelation** $E \subseteq A \times A$ ist:  

1. **Äquivalenzrelation**:  
   $$ \forall x \in A: \, x \sim x $$  
   $$ \forall x, y \in A: \, (x \sim y \implies y \sim x) $$  
   $$ \forall x, y, z \in A: \, (x \sim y \land y \sim z \implies x \sim z) $$  

2. $E$ ist **invariant** bzw. abgeschlossen unter Operationen:  
   $$ \forall i \in I, \, \forall (a_1, \ldots, a_{n_i}), (b_1, \ldots, b_{n_i}) \in A: $$
   $$
   (a_j, b_j) \in E \implies (\omega_i(a_1, \ldots, a_{n_i}), \omega_i(b_1, \ldots, b_{n_i})) \in E
   $$  

---

### Bemerkung

- $E$ ist unter $\mathcal{A} \times \mathcal{A}$ abgeschlossen, also Unteralgebra von $\mathcal{A} \times \mathcal{A}$.  

---

## Lemma 1

Wenn $f: A \to B$ ein **Homomorphismus** ist, dann ist:  
$$ \text{Kern}(f) = \{(a_1, a_2) \mid f(a_1) = f(a_2)\} \subseteq A \times A $$  
eine **Kongruenzrelation**.  

---

## Lemma 2

Wenn $E \subseteq A \times A$ eine Kongruenzrelation ist, dann kann man auf der Menge $A / E$ eine Algebra $\overline{A}$ definieren (gleichen Typs).  

---

### Beweisidee

- Sei $X = \{X_i\}_{i \in I}$ eine Partition.  
- Abbildung:  
  $$
  A \to A / E, \, x \mapsto [x]
  $$
  ist **surjektiv** und ein **Homomorphismus**.  

---

### Diagramm

Eine Illustration zeigt:  

- **Faktorbildung** durch Äquivalenzrelation.  
- Jede Äquivalenzklasse wird durch ein Element repräsentiert.  
- Diese Klassen bilden eine **Partition**.  

---

### Notizen

1. **Wenn Äquivalenzrelation vorhanden:**  
   - Schaue auf die Partition an, diese ist übersichtlich.  

2. **Reelle Zahlen:**  
   - Reelle Zahlen nach Faktorisierung immer noch Algebra.  

3. **Isomorphie:**  
   - Isomorph zu $G$ ist nicht unbedingt isomorph zu Zellmenge.  

---

### Definition: Faktoralgebra

Eine Faktoralgebra ist auch als **Quotientenalgebra** bekannt.  
# Gruppenfamilien und Faktoralgebra

---

## Definition

Sei $(G_n)_{n \in \mathbb{N}}$ eine Familie von Gruppen.  

$$ G = \bigcup_{n \in \mathbb{N}} G_n $$  

---

## Satz 1

Es gibt genau eine Gruppe $G_\infty$ auf der Menge $G$ derart, dass:  

$$ G_n \subseteq G_\infty \quad \text{für alle } n \in \mathbb{N} $$  

---

### Beweis (Skizze)

Für $x, y \in G_\infty$ gibt es $n, k \in \mathbb{N}$, sodass:  

- $x \in G_n$, $y \in G_k$  
- Definiere: $x \cdot y = g_n \cdot g_k$  

---

### Notiz

Man muss alle Gruppenaxiome für den Beweis nachrechnen.  

---

## Satz 2 (2.2.9)

Wenn $(A_n)_{n \in \mathbb{N}}$ eine Folge von (nicht leeren) Algebren ist (gleichen Typs), und $f$ eine Folge von Gesetzen ist, dann gibt es eine Algebra auf der Menge:  

$$ A = \bigcup_{n \in \mathbb{N}} A_n $$  

Diese Algebra ist analog definiert wie für Gruppen.  

---

## Beispiel

- $G_n = \{ e^{2\pi i k/n} \mid k = 0, 1, \ldots, n - 1 \}$  
- $G = \bigcup_{n=1}^\infty G_n$  
- **Bild:** Kreis mit Punkten, die Einheitswurzeln auf dem Einheitskreis darstellen.  

---

### Duales Kachanal

- Man nennt $2\pi i k/n$ eine $n$-te Einheitswurzel.  

---

## Beweis (Skizze)

Betrachte:  

$$ \beta \leq \beta \times \Pi A_n \quad \text{mit} \quad A = \beta / \theta \quad \text{ist isomorph} $$  

1. $\theta \in \beta \times \Pi A_n$ kongruent.  
2. $\theta$ bedeutet konstante oder gleiche Punkte.  

---

### Schlussfolgerung

Wenn:  

$$ a = (a_0, a_1, \ldots) \in \Pi A_n $$  
$$ \theta \in \beta \quad \Rightarrow \quad (a_0, a_1, \ldots) \sim (a_0', a_1', \ldots) $$  

---

### Nebensatz

Ein analoger Satz gilt auch für Körper.  
- Braucht neuen Satz, weil Körper keine Varietät bilden.  

---

### Notizen

1. **Total erfüllt:** Bedeutet, dass ein Gesetz überall gilt.  
2. **Körper:** Nicht als Varietät darstellbar.  

---

## Diagramm

Eine Illustration zeigt, wie $G_n$ auf $G$ abgebildet wird und wie eine Kongruenzrelation zur Bildung einer Faktoralgebra führt.  

# 2.2.2 Normalteiler

---

## Definition: Normalteiler

Seien $G, H$ Gruppen und $f: G \to H$ ein Homomorphismus.  

- Sei $N = f^{-1}(\{1_H\}) = \{x \in G \mid f(x) = 1_H\}$  

---

### Bemerkungen

1. Wenn $g \in G$ und $x \in f^{-1}(\{1\})$, dann ist:  
   $$ f(g \cdot x \cdot g^{-1}) = 1 $$  

2. $N$ ist **unter Konjugation abgeschlossen**, d.h.:  
   $$ gNg^{-1} \subseteq N $$  

---

## Satz

Sei $G$ eine Gruppe, $N \leq G$, $x \in G$. Dann gilt:  

1. $xN = Nx$  
2. Auf der Menge $G/N = \{xN \mid x \in G\}$ wird durch:  
   $$ (xN) \cdot (yN) = (xy)N $$  
   eine Gruppenstruktur definiert. Diese Gruppe nennt man **Quotientengruppe** oder **Faktorgruppe** $G/N$.  

---

### Abbildung

$$ \varphi: G \to G/N, \quad \varphi(x) = xN $$  

- Die Abbildung ist **surjektiv**, ein **Homomorphismus**, und der Kern ist $N = f^{-1}(1)$.  

---

## Beweis

1. Für $x \in G$:  
   $$ xN = Nx $$  

2. Sei $x \in G$, $y = x^{-1}$, dann:  
   $$ yNy^{-1} \subseteq N $$  
   $$ xN = Nx $$  

---

## Beweis (Fortsetzung)

Sei $N \triangleleft G$ und $x \in G$.  

- Für alle $n \in N$:  
  $$ xnx^{-1} \in N $$  
  $$ xN = Nx $$  

---

## Aussage

$$ xN = Nx \iff xN x^{-1} = N $$

Dies gilt, weil:  

1. Für alle $n \in N$:  
   $$ xnx^{-1} \in N $$  

2. Für alle $n' \in N$:  
   $$ x^{-1} n' x \in N $$  

3. Folgt aus Voraussetzung.  

# Definition: Gruppenstruktur und Wohldefiniertheit

---

## Definition

Eine Gruppenstruktur ist nur wohldefiniert, wenn:  

$$ (xN)(yN) = (xy)N $$  

---

## Notiz

Diese Bedingung wird oft im Skript hervorgehoben.  

---

## Überprüfung: Wohldefiniertheit

Wir müssen zeigen:  

1. Wenn $xN = x'N$ und $yN = y'N$, dann:  
   $$ (xy)N = (x'y')N $$  

2. Sei $x \in G$, $x'N = xN$, $y'N = yN$.  

3. Da $N$ ein Normalteiler ist:  
   $$ x' \in xN \implies x' = xn \quad \text{für } n \in N $$  
   $$ y' \in yN \implies y' = ym \quad \text{für } m \in N $$  

---

### Wunsch

Zeigen, dass:  

$$ (xy)N = (x'y')N $$  

---

### Beweis

$$ (xy)N = (x'y')N \implies (xy)^{-1} (x'y') \in N $$  
$$ (x^{-1} y^{-1}) (x'y') \in N $$  
$$ N \text{ ist normal } \implies \text{wohldefiniert} $$  

---

## Was ist Kern $N$?

$$ N = \ker f = \{ x \in G \mid f(x) = 1 \} $$  

---

## Homomorphismus

Sei $f: G \to H$ ein surjektiver Homomorphismus mit $N = \ker f$.  

- $G_x \xrightarrow{f} G_y$  
- $G/N \xrightarrow{\tilde{f}} H$  

---

### Diagramm

Eine Zeichnung zeigt, wie $f$ von $G$ auf $H$ abgebildet wird.  
Auch die Abbildung $G/N \to H$ wird dargestellt.  

---

## Bedingung für Homomorphismus

Wenn $f$ ein Homomorphismus ist, dann ist:  

$$ f(x^{-1}y^{-1}) = 1 \implies f(x)^{-1}f(y)^{-1} = 1 $$  

---

## Fazit

Der Homomorphismus ist wohldefiniert, wenn:  

$$ f(x) \cdot f(y) = f(xy) $$  
# WDH: Normalteiler

**Datum:** 27.03.2025  

---

## Definition

Sei $\varphi: G \to K$ ein Gruppenhomomorphismus.  
Der Kern von $\varphi$ ist:  

$$ N = \ker(\varphi) = \{x \in G \mid \varphi(x) = 1_K\} $$  

---

### Bedingung für Normalteiler

$$ N \triangleleft G \iff \forall x \in G, \, xNx^{-1} \subseteq N $$  

---

### Eigenschaften

1. $N \triangleleft G \implies N$ ist abgeschlossen unter Konjugation.  
2. $N = \ker(\varphi)$ ist immer ein Normalteiler von $G$.  
3. Wenn $\varphi: G \to K$ ein Gruppenhomomorphismus ist, dann ist:  
   $$ \varphi(x^{-1}y^{-1}) = \varphi(x)^{-1} \varphi(y)^{-1} = 1_K $$  

---

## Lemma

Sei $\varphi: G \to K$ ein Homomorphismus, dann ist:  

$$ \ker(\varphi) = \{x \in G \mid \varphi(x) = 1_K\} $$  
$$ \varphi(x^{-1} y x) = \varphi(y) \implies x^{-1} y x \in \ker(\varphi) $$  

---

## Bemerkung

Wenn $G, K$ Gruppen sind und $\varphi: G \to K$ ein Homomorphismus ist, dann gilt:  

$$ \varphi \text{ ist ein Homomorphismus} \implies \forall x, y \in G: \varphi(xy) = \varphi(x) \varphi(y) $$  

---

## Beweis

1. In jeder Gruppe $G$ hat $x \cdot x^{-1} = 1_G$ genau eine Lösung, nämlich $x^{-1}$.  
2. Wenn $e$ neutral in $G$, dann:  
   $$ \varphi(e) = \varphi(e) \cdot \varphi(e) = e_K $$  
3. Für alle $g \in G$ hat $g \cdot g^{-1} = e$ genau eine Lösung, nämlich $g^{-1}$.  
4. Daraus folgt:  
   $$ \varphi(g^{-1}) = (\varphi(g))^{-1} $$  

---

## Beispiel: Normalteiler

Betrachte $S_3 = \{\text{id}, (12), (13), (23), (123), (132)\}$ (Zyklenschreibweise).  

- Untergruppe $U = \{\text{id}, (123), (132)\}$  

- Ist $U$ ein Normalteiler?  

  - $(13)U(13) = \{\text{id}, (13)(123)(13), (13)(132)(13)\}$  
  - $U \neq (13)U(13)$  

  - **Ergebnis:** $U$ ist **kein** Normalteiler, weil es unter Konjugation **nicht abgeschlossen** ist.  

---

## Lineare Algebra: Signum

- Signumabbildung $\text{sign}: S_n \to \{-1, 1\}$  
- Definiert durch:  
  $$
  \text{sign}(\sigma) = \begin{cases} 
  1 & \text{wenn } \sigma \text{ gerade ist}, \\
  -1 & \text{wenn } \sigma \text{ ungerade ist}.
  \end{cases}
  $$  

- $\text{sign}: S_n \to \{-1, 1\}$ ist ein Gruppenhomomorphismus.  
# Signum und Zykeltypen

---

## Signumabbildung

Sei $\sigma \in S_n$.  
Die Signumabbildung ist definiert als:  

$$ \text{Sign}(\sigma) = 1 \iff \sigma \in A_n \subseteq S_n $$  

---

## Permutationen

Sei $\sigma \in S_n$, eine Permutation.  

### Beispiel: Einfacher Fall

$$ \sigma' = (1 \, 2) \quad \text{(Transposition)} $$  
$$ \sigma'(1) = 2, \quad \sigma'(2) = 1, \quad \sigma'(k) = k \, \text{für } k \neq 1, 2 $$  

---

### Anwendung auf Permutation $\pi$

$$ \sigma'(\pi(1)) = \pi(2), \quad \sigma'(\pi(2)) = \pi(1), \quad \ldots $$  
$$ \sigma'(\pi(i)) = \pi(i) \quad \text{für } i \neq 1, 2 $$  

---

### Analogie

$$ \sigma = (\alpha_1 \, \alpha_2 \, \ldots \, \alpha_k) $$  
$$ \pi \circ \sigma \circ \pi^{-1} = (\pi(\alpha_1) \, \pi(\alpha_2) \, \ldots \, \pi(\alpha_k)) $$  

---

### Beispiel

$$ \pi = (12)(457)(3896) \quad \sigma = (1 \, 2) $$  

$$ \pi \circ \sigma = \pi(\pi(1)) \, \pi(\pi(2)) \, \ldots \, \pi(\pi(6)) $$  

---

### Zykeltypen

- **(12), (13):** Zykeltyp = 2  
- **(123):** Zykeltyp = 3  

---

---

## Satz

Sei $U \subseteq S_n$. Dann gilt: $U$ ist ein Normalteiler in $S_n$ genau dann, wenn:

1. $U$ ist unter Konjugation abgeschlossen.  
2. Für alle $\sigma, \tau \in S_n$:  
   $$ \tau \sigma \tau^{-1} \in U \implies \sigma \in U $$  

---

### Beweis

1. Wenn $U \subseteq S_n$, $U \subseteq G$, $G$ ist gleich zykeltypisch:  
   $$ \pi \in S_n, \, \sigma \in U \implies \pi \sigma \pi^{-1} \in U $$  

2. Wenn $U$ unter gleichen Zykeltypen abgeschlossen ist:  
   $$ \forall \pi \in S_n, \, \pi \sigma \pi^{-1} \in U \implies \sigma \in U $$  

---

### Beispiel: Alle Normalteiler von $S_4$

| $E$   | $\sigma$                 | Zykeltypen von $\sigma$           |
|-------|--------------------------|----------------------------------|
| 4     | $id$                     | $1,1,1,1$ oder (nichts hinreichend) |
| 6     | $(12)(34)$               | 2, 2                            |
| 8     | $(1234), (1324)$         | 4                                |
| 6     | $(123), (124)$           | 3                                |
| 24    | $A_4$ (alle geraden)     | -                                |
| 24    | $S_4$                    | -                                |

---

### Hinweis

- $S_4$ hat insgesamt $24$ Elemente.  
- Normalteiler von $S_4$:  
  - $E = \{\text{id}\}$  
  - $A_4$ (alle geraden Permutationen)  
  - $S_4$ (selbst)  

# Untergruppen und Normalteiler

---

## Bemerkungen

1. Wenn $A, B \leq G$:  
   $$ A \cap B = \{a \in A \mid a \in B\} $$  

2. Wenn $A \leq G$:  
   $$ A \subseteq G, \, x \in G \implies (A : B) $$  

---

## Beispiel

Seien $a, b \in A \cap B$.  
- $(ab)^{-1} = b^{-1} a^{-1}$  

---

## Lemma (3.2.2.13)

Sei $G$ eine Gruppe, $U \leq G$, $N \triangleleft G$.  
Dann gilt:  

$$ UN = NU \leq G $$  

---

### Beweis

$$ UN = \{ux \mid u \in U, \, x \in N\} $$  
$$ NU = \{xu \mid x \in N, \, u \in U\} $$  

$$ UN = \bigcup_{u \in U} uN \quad \text{und} \quad NU = \bigcup_{u \in U} Nu $$  

---

### Wenn

1. $a \in UN, b \in UN$  
2. $a, b \in U$ und $x, y \in N$  

Dann:  
$$ ab = uxvy \in UN \implies ab \in UN $$  
$$ ab \in NU $$  

---

### Schlussfolgerung

$$ N \triangleleft UN \leq G $$  

---

### Beweis

1. $x \in UN$:  
   $$ x^{-1} Nx = N \implies \text{Also } \forall x \in G $$  

---

### Hinweis

Wenn wir einen **Normalteiler (NT)** sehen, bilde einen **Faktor**.  

---

## Notiz

**Jede Gruppe ist ein Normalteiler in sich selbst (trivial, also uninteressant).**  
# Satz 2: Isomorphiesatz (3.2.2.14)

---

## Satz

Wenn $UN = NU$, dann ist $U / (U \cap N) \cong UN / N$.  

---

### Bedingungen

1. $U \subseteq G$, $N \triangleleft G$.  
2. $UN = NU \leq G$.  

---

### Zu Zeigen

- Wohldefiniertheit  
- Homomorphismus  
- Bijektivität  

---

## Wohldefiniertheit

$$ uN \mapsto u(UN) = (UN)u \subseteq UN $$  

$$ x \in U, N \triangleleft G \implies x^{-1}Nx = N \implies xN = Nx $$  

---

## Homomorphismus

- Sei $U \cap N \leq U$, $UN = NU \leq G$.  
- Homomorphismus:  
  $$ h: U \to UN, \quad h(u) = uN $$  

---

## Bijektivität

- Injektiv: $U \cap N \leq N \implies h(UN) = UN$  
- Surjektiv: $UN = NU \implies \text{bijektiv}$  

---

---

## Produktgruppen

Sei $G$ eine Gruppe, $U_1, U_2 \leq G$.  
Wir betrachten die Gruppe $U_1 \times U_2$ als äußeres Produkt:  

$$ h(a_1, a_2) = a_1 a_2 $$  

---

### Definition

$G$ heißt **inneres Produkt** von $U_1, U_2$, wenn es einen **Homomorphismus** von $U_1 \times U_2$ nach $G$ gibt.  

---

### Darstellung

- **Inneres Produkt:** Überlappung von $U_1$ und $U_2$ in $G$.  
- **Äußeres Produkt:** Keine Überlappung.  

---

### Bemerkung

- Wenn der Schnitt dieser Mengen trivial ist, dann gelten spezielle Eigenschaften.  

---

---

## Schlussfolgerung

Wenn $G = U_1 \cdot U_2$, dann müssen gelten:  

1. $(p_x, p_y): G \to U_1 \times U_2$ ist surjektiv.  
2. Für jedes $g \in G$ existiert genau ein Paar $(p_x, p_y)$, sodass $g = p_x p_y$.  

---

### Homomorphismus

Wenn $G$ eine Gruppe ist, dann ist die Abbildung:  

$$ \varphi: G \to G / G_1, \quad \varphi(g) = xgx^{-1} $$  

Ein Homomorphismus.  

---

### Hinweis

Wenn $G$ **abelsch** ist, dann gibt es nur **Auto**.  
