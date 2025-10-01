Finden Sie alle Normalteiler von 
$$
G := \mathbb{Z}_3 \times \mathbb{Z}_3
$$
(Dabei meinen wir mit $\mathbb{Z}_3$ natürlich die Gruppe $(\mathbb{Z}_3, +, \bar{0}, -)$.)  
*(Hinweis: Lineare Algebra kann hier hilfreich sein.)* Finden Sie für jeden solchen Normalteiler $N$ eine (möglichst einfach beschriebene) Gruppe $H$ und einen Homomorphismus 

$$
\varphi : G \to H
$$
sodass $N$ das $\varphi$-Urbild des neutralen Elements von $H$ ist.

---

- Ein **Normalteiler** $N$ einer Gruppe $G$ ist eine Untergruppe von $G$, die unter Konjugation mit jedem Element von $G$ invariant bleibt. Das bedeutet:

$$\forall g \in G, \, \forall n \in N: \, gng^{-1} \in N$$

Alternativ kann man sagen, dass $N$ ein Normalteiler von $G$ ist, wenn gilt:

$$g \quad \text{für alle } g \in GgN=N$$

- Ein **Gruppenhomomorphismus** ist eine Abbildung $\varphi: G \to H$ zwischen zwei Gruppen $G$ und $H$, die die Gruppenoperation erhält, also:

$$\varphi(g_1g_2) = \varphi(g_1)\varphi(g_2)$$
für alle $g_1, g_2 \in G$.

- Der **Kern** eines Gruppenhomomorphismus $\varphi: G \to H$ ist die Menge aller Elemente von $G$, die auf das neutrale Element von $H$ abgebildet werden:

$$\ker(\varphi) = \{g \in G \mid \varphi(g) = e_H\}$$

Ein wichtiger Satz ist: **Der Kern eines Homomorphismus ist immer ein Normalteiler von $G$.**

- Direktes Produkt von Gruppen eir betrachten hier:
$$G := \mathbb{Z}_3 \times \mathbb{Z}_3$$
Das bedeutet, dass die Gruppe $G$ aus geordneten Paaren $(x,y)$ besteht, wobei $x, y \in \mathbb{Z}_3$. Die Gruppenoperation wird komponentenweise definiert, also:
$$(x_1, y_1) + (x_2, y_2) = (x_1 + x_2, y_1 + y_2)$$

---
#### Betrachte die Untergruppen von $G = \mathbb{Z}_3 \times \mathbb{Z}_3$
Wir zählen alle Untergruppen von $G$ auf. Diese sind automatisch Normalteiler, da $G$ abelsch ist:

1. $\{(0,0)\}$
2. $\{(x,0) : x = 0,1,2\} \cong \mathbb{Z}_3$
3. $\{(0,x) : x = 0,1,2\} \cong \mathbb{Z}_3$
4. $\{(x,x) : x = 0,1,2\} \cong \mathbb{Z}_3$
5. $\{(x,-x) : x = 0,1,2\} \cong \mathbb{Z}_3$
6. $\mathbb{Z}_3 \times \mathbb{Z}_3$

Das sind alle.
- Wenn angenommen wird, dass es noch eine weitere Untergruppe gibt, dann enthält diese ein Element $(x,y) \neq (0,0)$.  
- Dieses Element erzeugt aber mindestens eine der eindimensionalen Untergruppen, da jedes nicht-null Element des $\mathbb{Z}_3$ bereits den ganzen $\mathbb{Z}_3$ erzeugt.  
- Also müsste $U$ größer sein als die eindimensionalen Untergruppen. Dann hätten wir aber bereits $\mathbb{Z}_3 \times \mathbb{Z}_3$.  
### Konstruktion der Homomorphismen

Nun finden wir besagte Homomorphismen:

- $\{(0,0)\}$: $H = G, \varphi_1 = id.$
- $\{(x,0): x = 0,1,2\}$: $H = \mathbb{Z}_3, \varphi_2(x,y) = y$
- $\{(0,x): x = 0,1,2\}$: $H = \mathbb{Z}_3, \varphi_3(x,y) = x$
- $\{(x,x): x = 0,1,2\}$: $H = \mathbb{Z}_3, \varphi_4(x,y) = x - y$
- $\{(x,-x): x = 0,1,2\}$: $H = \mathbb{Z}_3, \varphi_5(x,y) = x + y$
- $\mathbb{Z}_3 \times \mathbb{Z}_3$: $H = \{0\}, \varphi_6(x,y) = 0$

$\varphi_1, \varphi_2, \varphi_3$ und $\varphi_6$ sind offensichtlich Homomorphismen, deren Kern genau die Normalteiler sind.  

---

### Überprüfung der Homomorphieeigenschaft der restlichen $\varphi_{n}$

Seien $(x_1, y_1), (x_2, y_2) \in \mathbb{Z}_3 \times \mathbb{Z}_3$. Dann gilt:

1. Für $\varphi_4$:
$$
\varphi_4((x_1,y_1) + (x_2,y_2)) = \varphi_4(x_1 + x_2, y_1 + y_2) = (x_1 + x_2) - (y_1 + y_2)
$$

$$
= (x_1 - y_1) + (x_2 - y_2) = \varphi_4(x_1,y_1) + \varphi_4(x_2,y_2)
$$

2. Für $\varphi_5$:

$$
\varphi_5((x_1,y_1) + (x_2,y_2)) = \varphi_5(x_1 + x_2, y_1 + y_2) = (x_1 + x_2) + (y_1 + y_2)
$$

$$
= (x_1 + y_1) + (x_2 + y_2) = \varphi_5(x_1,y_1) + \varphi_5(x_2,y_2)
$$
