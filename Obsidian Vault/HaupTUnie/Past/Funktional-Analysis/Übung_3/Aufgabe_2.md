-Seien $X, Y$ Banachräume und $T \in \mathcal{L}_b(X, Y)$ derart, dass
$$
Y = T(X) + Z
$$
für einen gewissen abgeschlossenen Unterraum $Z \subseteq Y$.

**Zeigen Sie:** Dann ist auch $T(X)$ abgeschlossen.
**Hinweis:** Betrachte $R : X \times Z \to Y$ definiert durch
$$
R(x, z) := T(x) + z
$$
und das Komplement von $R(X \times (Z \setminus \{0\}))$ in $Y$. Dabei ist $X \times Z$ mit der Maximumsnorm versehen.

---

Wir definieren:
$$
R(x, z) := T(x) + z
$$
- $R$ ist eine **surjektive** abbildung
Wir wissen:  
$Y = T(X) + Z$, d.h. **jeder Vektor $y \in Y$ lässt sich als Summe $y = T(x) + z$** schreiben mit $x \in X$ und $z \in Z$.

Das bedeutet:
$$
\forall y \in Y\ \exists (x, z) \in X \times Z\ :\ R(x, z) = T(x) + z = y
$$

Also:
$$
R(X \times Z) = T(X) + Z = Y
$$

Also ist $R$ **surjektiv**.

- **Linearität**

$R$ ist die Summe zweier linearer Abbildungen:
- $x \mapsto T(x)$ (linear)
- $z \mapsto z$ (lineare Einbettung in $Y$)
⇒ $R(x, z) = T(x) + z$ ist **linear**.

-  **Norm und Beschränktheit**

Betrachte  $X \times Z$ versehen mit der **Maximumsnorm**:
$$
\|(x, z)\| := \max(\|x\|_X,\ \|z\|_Z)
$$
Dann gilt für $R(x, z)$:

$$
\begin{aligned}
\|R(x, z)\|_Y &= \|T(x) + z\|_Y \\
&\leq \|T(x)\|_Y + \|z\|_Y \\
&\leq \|T\| \cdot \|x\|_X + \|z\|_Z \\
&\leq \|T\| \cdot \max(\|x\|_X,\ \|z\|_Z) + \max(\|x\|_X,\ \|z\|_Z) \\
&= (\|T\| + 1) \cdot \|(x, z)\|_{\max}
\end{aligned}
$$
Also:
$$
\|R(x, z)\|_Y \leq C \cdot \|(x, z)\|_{X \times Z}
\quad\text{mit}\quad C = \|T\| + 1
$$

⇒ $R$ ist **beschränkt** (also stetig).



Da $T$ und die Addition stetig sind, ist $R$  **beschränkt** (d.h. stetig linear).
Damit sind die Voraussetzungen für den Satz von der offenen Abbildung:
- $Y$ ist Banachraum
- $Z \leq Y$ abgeschlossen ⇒ $Z$ ist Banachraum
- $X$ ist Banachraum (gegeben)
- $\Rightarrow X \times Z$ ist ebenfalls Banachraum (mit Maximumsnorm)
erfüllt

Daher gilt:
$$
R : X \times Z \to Y \quad \text{linear, stetig, surjektiv}
$$
 Nach dem **Satz von der offenen Abbildung** (Satz 4.3.1) ist $R$ eine **offene Abbildung**.
 
![[Pasted image 20250409225136.png]]

---


Sei $U := X \times (Z \setminus \{0\})$.
- $X$ offen in $X$
- $Z \setminus \{0\}$ ist offen in $Z$ ⇒ $U$ offen in $X \times Z$

Da $R$ offen ist, ist auch
$$
R(U) = R(X \times (Z \setminus \{0\}))
$$
offen in $Y$.

Dann ist das **Komplement** in $Y$ abgeschlossen:
$$
T(X) = R(X \times \{0\}) = Y \setminus R(X \times (Z \setminus \{0\}))
$$

Also ist $T(X)$ **abgeschlossen** als Komplement einer offenen Menge.

   Y (gesamter Zielraum)
   ┌──────────────────────────────┐
   │                              │
   │     R(X × (Z \ {0}))         │  ← offen in Y (Bild einer offenen Menge)
   │       (offene Menge)         │
   │                              │
   │        •••••••••••••••       │
   │        •             •       │
   │        •   Störung    •      │
   │        • durch Z≠0    •      │
   │        •             •       │
   │        •••••••••••••••       │
   │                              │
   │         ⎯⎯⎯⎯⎯⎯⎯⎯⎯          │
   │         T(X) = R(X × {0})    │  ← abgeschlossen (Komplement der offenen Menge)
   │                              │
   └──────────────────────────────┘
