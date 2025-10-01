## Aufgabenstellung:

### 1.
$\mathbb{C} \setminus \{0\}$ mit der Multiplikation ist eine Gruppe. Finden Sie Untergruppen dieser Gruppen.  
   ==(1.1)==Geben Sie mindestens drei endliche, ==(1.2)== zwei abzählbar unendliche und ==(1.3)== zwei überabzählbare an.  
   (Jeweils verschiedene und nichttriviale, d.h. $\neq \{1\}$ und $\neq \mathbb{C} \setminus \{0\}$.)
### 2.
Dieselbe Aufgabe für die Gruppe der invertierbaren reellen $2 \times 2$ Matrizen  
   (mit der Matrix-Multiplikation).

#### (1.1)
Drei endliche Untergruppen von $\mathbb{C} \setminus \{ 0 \}$
##### (1.1.1) Drei endliche Zyklische Untergruppen
Die Menge der $n-$ten Einheitswurzeln. Es gibt immer ein *neurales Element*, es gibt immer ein *inverses element* die multiplikation ist *kommtutativ* und die *Assoziativität* bleibt aus $\mathbb{C}$ erhalten.

Konkretes Beispiel $n = 6$ da
![[Zyk.png]]
**Kreisteilungsgleichung:**  $z^6 = 1, \quad z \in \mathbb{C}$  

Lösungen:  $z_k = e^{i \frac{k}{6} 2\pi} = \cos \left( \frac{k}{6} 2\pi \right) + i \sin \left( \frac{k}{6} 2\pi \right), \quad k \in \{0,1,2,3,4,5\}$  

 **Zyklische Gruppe der Ordnung 6:**  
$Z_6 = \{e, g, g^2, g^3, g^4, g^5\} = \{1, z_1, z_2, z_3, z_4, z_5\} \quad \textbf{Linksdrehung}$  
$= \{1, z_5, z_4, z_3, z_2, z_1\} \quad \textbf{Rechtsdrehung}$  
 **Zyklische Untergruppen:**  
- **$Z_3$** = $\{e, g, g^2\} = \{1, z_2, z_4\} \textbf{  Linksdrehung }$
  $= \{1, z_4, z_2\} \quad \textbf{Rechtsdrehung}$ 
- **$Z_2$** = $\{e, g\} = \{1, z_3\}$  
**Verknüpfungstafel (Gruppentafel) bei Linksdrehung**  
(entsprechend Rechtsdrehung bei Fall b) (II))  

| ∘  | $z_0$ | $z_1$ | $z_2$ | $z_3$ | $z_4$ | $z_5$ |
|----|------|------|------|------|------|------|
| $z_0$ | $z_0$ | $z_1$ | $z_2$ | $z_3$ | $z_4$ | $z_5$ |
| $z_1$ | $z_1$ | $z_2$ | $z_3$ | $z_4$ | $z_5$ | $z_0$ |
| $z_2$ | $z_2$ | $z_3$ | $z_4$ | $z_5$ | $z_0$ | $z_1$ |
| $z_3$ | $z_3$ | $z_4$ | $z_5$ | $z_0$ | $z_1$ | $z_2$ |
| $z_4$ | $z_4$ | $z_5$ | $z_0$ | $z_1$ | $z_2$ | $z_3$ |
| $z_5$ | $z_5$ | $z_0$ | $z_1$ | $z_2$ | $z_3$ | $z_4$ |

##### (1.1.2)
- $\{ -1,1 \}$ 

| $\circ$ | $-1$ | $1$ |
| ------- | ---- | --- |
| $-1$    | 1    | -1  |
| $1$     | -1   | 1   |

##### (1.1.3)
- $\{ \pm i, \pm 1 \}$

| $\circ$ | $-i$ | $i$ | $-1$ | $1$ |
| ------- | ---- | --- | ---- | --- |
| $-i$    | -1   | 1   | i    | -i  |
| $i$     | 1    | -1  | -i   | i   |
| $-1$    | i    | -i  | 1    | -1  |
| $1$     | -i   | i   | -1   | 1   |

#### (1.2) Zwei abzälbar Unendliche Gruppen
##### (1.2.1)
Betrachte $\mathbb{Q} := \{ \mathbb{R} \setminus \mathbb{I}\}$ und definiere die Menge $A := \{a + b*i \in \mathbb{C} | a,b \in \mathbb{Q}\}$ 

##### (1.2.2)
Offensichtlich ist $(\mathbb{Q} + i \cdot 0) \setminus \{0\}$ eine Untergruppe, da sie isomorph zu $\mathbb{Q} \setminus \{0\}$ ist und  
demnach abgeschlossen unter der Multiplikation ist, ein neutrales Element enthält und auch die Inverse eines jeden Elements.  

##### (1.2.3)
$\{2^n \mid n \in \mathbb{Z} \} + i \cdot 0$ ist sicher eine Untergruppe.    $2^n \cdot 2^{-n} = 1$, wegen der Kommutativität hat also jedes Element eine Inverse.  
Außerdem ist $1 = 2^0 \in \{2^n \mid n \in \mathbb{Z}\}$, d.h. wir haben ein neutrales Element.  
Multipliziert man zwei Zweierpotenzen miteinander, erhält man wieder eine Zweierpotenz.
#### (1.3) Zwei Überabzählbare Untergruppen
##### (1.3.1)
Die Kreisscheibe im Koplexen mit Radius 1
$K_{1}^{\mathbb{C}}(0)\setminus{\{0\}}$
   Wenn $w, z \in K_{1}^{\mathbb{C}}(0)$, dann gilt:  $|wz| \leq 1 \Rightarrow wz \in K_{1}^{\mathbb{C}}(0)$  
   $\Rightarrow K_{1}^{\mathbb{C}}(0) \subseteq \mathbb{C}^{\times}$
