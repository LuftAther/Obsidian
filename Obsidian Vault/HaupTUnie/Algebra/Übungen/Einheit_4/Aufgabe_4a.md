1. Sei $G:= \mathbb{Z}_{30}$. Finden Sie alle Darstellungen von $G$ als inneres direktes Produkt $G = U_1 \odot U_2$ mit $|U_1| \leq |U_2|$.

2. Ebenso für $G = \mathbb{Z}_4 \times \mathbb{Z}_2$.

---

Setze $G = U_1 \odot U_2$  per definition ist das ein inneres direktes Produkt, genau dann wenn gilt:
- $U_1, U_2 \leq G$
- $h: U_1 \times U_2 \to G, (u_1, u_2) \mapsto u_1 u_2$ , h ist ein Isomorphismus.
![[Pasted image 20250406113419.png]]
#### 1 Finde alle Darstellungen von G ...

$$
G = \mathbb{Z}_{30} = \{[0]_{30}, [1]_{30}, \ldots, [29]_{30}\}
$$

- **Betrachte** alle möglichen Untergruppen von $\mathbb{Z_{30}}$: sei p teiler von 30 d.h $p \in \{ 1,2,3,5,6,10,15,30 \}$
$$
\begin{array}{ll}
G_1 = G = \mathbb{Z}_{30} & |G| = 30 \\
G_2 = \{[0]_{30}, [2]_{30}, [4]_{30}, \ldots, [28]_{30}\} & |G_2| = 15 \\
G_3 = \{[0]_{30}, [3]_{30}, [6]_{30}, \ldots, [27]_{30}\} & |G_3| = 10 \\
G_5 = \{[0]_{30}, [5]_{30}, [10]_{30}, \ldots, [25]_{30}\} & |G_5| = 6 \\
G_6 = \{[0]_{30}, [6]_{30}, [12]_{30}, \ldots, [24]_{30}\} & |G_6| = 5 \\
G_{10} = \{[0]_{30}, [10]_{30}, [20]_{30}\} & |G_{10}| = 3 \\
G_{15} = \{[0]_{30}, [15]_{30}\} & |G_{15}| = 2 \\
G_{30} = \{[0]_{30}\} & |G_{30}| = 1
\end{array}
$$

- **Betrachte** die Abbildung: $h: U_1 \times U_2 \to G, \quad (u_1, u_2) \mapsto u_1 +_{30} u_2$
- **Behauptung**: $h$ ist ein Isomorphismus genau dann, wenn $|G_i| \cdot |G_j| = |G|$.

Für $G_i$ und $G_j$ mit $|G_i| \cdot |G_j| = |G|$ gilt:
$$
G_i \cap G_j = \{[0]_{30}\}
$$
Daraus folgt:

$$
\forall z \in G, \, \exists! x \in G_i, \, \exists! y \in G_j: \, z = x + y = h(x, y)
$$

Mögliche Paare $(U_1, U_2)$ mit $U_1 \leq U_2$:

- $U_1 = G_{30}, U_2 = G_1$
- $U_1 = G_{15}, U_2 = G_2$
- $U_1 = G_{10}, U_2 = G_3$
- $U_1 = G_6, U_2 = G_5$

---

### 2. Sei $G = \mathbb{Z}_4 \times \mathbb{Z}_2$. Finden ...

---

Setze $G = U_1 \odot U_2$. Per Definition ist das ein **inneres direktes Produkt**, genau dann wenn gilt:
- $U_1, U_2 \leq G$
- $h: U_1 \times U_2 \to G, (u_1, u_2) \mapsto u_1 u_2$, $h$ ist ein Isomorphismus.

---

### 2.1 Bestimme alle Untergruppen von $G$

$$\begin{split}
G = \mathbb{Z}_4 \times \mathbb{Z}_2 = \\
\{([0]_4, [0]_2), ([1]_4, [0]_2), ([2]_4, [0]_2), \\
([3]_4, [0]_2), ([0]_4, [1]_2), ([1]_4, [1]_2), ([2]_4, [1]_2), \\([3]_4, [1]_2)\}
\end{split}$$


- **Betrachte** alle möglichen Untergruppen von $\mathbb{Z}_4 \times \mathbb{Z}_2$:

$$
\begin{array}{ll}
G_0 = G = \mathbb{Z}_4 \times \mathbb{Z}_2 & |G| = 8 \\
G_1 = \{([0]_4, [0]_2), ([2]_4, [0]_2)\} \times \mathbb{Z}_2 & |G_1| = 4 \\
G_2 = \{([0]_4, [0]_2), ([0]_4, [1]_2)\} & |G_2| = 2 \\
G_3 = \mathbb{Z}_4 \times \{[0]_2\} & |G_3| = 4 \\
G_4 = \{([0]_4, [0]_2), ([2]_4, [0]_2)\} & |G_4| = 2 \\
G_5 = \{([0]_4, [0]_2)\} & |G_5| = 1
\end{array}
$$

- Definiere der Abbildung $h$

$$
h: U_1 \times U_2 \to G, \quad (u_1, u_2) \mapsto u_1 + u_2
$$

 $h$ ist ein Isomorphismus genau dann, wenn

$$
|G_i| \cdot |G_j| = |G| \quad \text{und} \quad G_i \cap G_j = \{([0]_4, [0]_2)\}
$$
> Wenn der schnitt nicht nur das neutrale element beinhalten würde wäre das ein wiederspruch zur injektivität
- Damit erhalten wir die möglichen paare  $(U_1, U_2)$ mit $U_1 \leq U_2$

- $U_1 = G_5, U_2 = G_0$ 
- $U_1 = G_4, U_2 = G_1$ 
- $U_1 = G_3, U_2 = G_2$ 

---

