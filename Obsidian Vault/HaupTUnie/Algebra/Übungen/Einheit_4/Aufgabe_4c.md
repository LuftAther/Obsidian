Sei $n = td$. Zeigen Sie, dass die zyklische Gruppe $\mathbb{Z}_n = \mathbb{Z}/n\mathbb{Z}$genau eine Untergruppe mit $t$Elementen hat, nämlich die von $d + n\mathbb{Z}$erzeugte.  
(Das folgt aus Satz 3.2.4.15. Geben Sie einen Beweis, der sich nicht einfach auf diesen Satz verlässt.)  
Finden Sie alle Untergruppen von $\mathbb{Z}_{40}$.

---

$$Z_d := \langle [d]_n \rangle =  \{[0]_n, [d]_n,[2\cdot d]_n , .., [(t-1)\cdot d]_n\}$$

#### 1) z.z. $\forall n = td\in \mathbb Z\exists ! U \leq \mathbb Z_n: |U| = t$
 Sei $n = td$ beliebig.
##### 1.1)  z.z. $Z_d \leq \mathbb Z_n \textcolor{gray}{(\Leftrightarrow \exists U\leq Z_n: |U| = t)}$
- **Behauptung** Die Opperation  $+_n|_{Z_d}$ ist abgeschlossen
- **Begründung**
 Seien $x,y \in Z_d$ beliebig. Es gilt $\exists k,l\in \mathbb Z: x = [k\cdot d]_n \wedge y = [l\cdot d]_n$. Wir beobachten 
 $$x +_n y = [k\cdot d]_n +_n [l\cdot d]_n = [k\cdot d + l \cdot d]_n = [(k+l)\cdot d]_n\in Z_d$$
 - **Behauptung**  $-_n|_{Z_d}$ ist abgeschlossen
 - **Begründung**
 Sei $x \in Z_d$ beliebig. Es gilt $\exists k\in \mathbb Z: x = [k\cdot d]$. Wir beobachten 
 $$-_nx = -_n[k\cdot d]_n = [-k\cdot d]_n = [(-k)\cdot d]_n\in Z_d$$
 Weiters haben wir dass  $[0]_n\in Z_d$, womit wir gezeigt haben, dass $Z_d \leq G$.
#### 1.2) z.z. $\forall U\in \mathfrak{P}(\mathbb Z_n): ((|U| = t \wedge U\leq \mathbb Z_n)  \Rightarrow U = Z_d)$ 
 > Beweis durch Contraposition
 
 Sei $U\in \mathfrak{P}(\mathbb Z_n)$ beliebig, sodass $|U| = t$, $U \leq \mathbb Z_n$ und $U \neq Z_d$ gilt. Nach unserer Voraussetzung ist $|U| = t$ und $U\neq Z_d$, womit $U\nsubseteq Z_d$ gilt. Wir betrachten $$u_{min} := \min_{m\in \{0,...,n\}\setminus\{k\cdot d | k\in \{0,...,t\} \}}\{m = l-m | [l]_n\neq[k]_n\in U\}$$
 $u_{min}$ existiert, wegen $U\setminus Z_d \neq \emptyset$
- Fall 1: $u_{min} < d$
Es gilt $$u_{min} < d \Rightarrow t \cdot u_{min} < t\cdot d = n$$
Wir beobachten $$[t\cdot d]_n = [0]_n \Rightarrow [t\cdot u_{min}]_n \neq [0]_n $$
Insgesamt gilt somit$$[0\cdot u_{min}]_n, \cdots, [t\cdot u_{min}] \in U\Rightarrow |U | \geq  t+1 > t 
\text{\Lightning}$$
- Fall 2: $u_{min} > d$
Es gilt $$(u_{min} > d \Rightarrow t \cdot u_{min} > t\cdot d = n)\Rightarrow (\exists k\in \{0,...,t-1\}: (k-1)\cdot u_{min} < n \leq k\cdot u_{min}) $$
Aus der Definition von $u_{min}$ und folgender Ungleichung $$((k-1)\cdot u_{min} < n \Rightarrow k\cdot u_{min} < n + u_{min} \sim_n u_{min}) \Rightarrow k\cdot u_{min} = n = t \cdot n \text{ \Lightning}$$
- Fall 3: $u_{min} = d$
Es gilt $$U\neq Z_d\Rightarrow (\exists u\in U\forall k\in \mathbb Z: ([u]_n\neq [k\cdot d]_n \Rightarrow t = |Z_d|< t+1 = |Z_d \cup \{u\}| \leq |U| \text{ \Lightning}))  $$
---
Ähnlich aber anders:
**2. Eindeutigkeit:**  
Nehmen wir an, es gibt eine weitere Untergruppe $H \subseteq \mathbb{Z}_n$mit $t$ Elementen. Da $H$ zyklisch ist, gibt es ein $k \in \mathbb{Z}_n$ mit:

$$
H = \langle k \rangle
$$

Die Ordnung von $H$ ist $t$, d.h. $k$ ist ein Element von $\mathbb{Z}_n$ mit Ordnung $t$. Die Ordnung eines Elements $k \in \mathbb{Z}_n$ist:

$$
\text{ord}(k) = \frac{n}{\text{ggT}(k, n)}
$$

Damit gilt:

$$
t = \frac{n}{\text{ggT}(k, n)}
$$

Daraus folgt:

$$
\text{ggT}(k, n) = d
$$

Also ist $H = \langle d \rangle$. Das zeigt, dass es genau eine Untergruppe mit $t$ Elementen gibt.

---

#### 2) Finden Sie alle Untergruppen von $\mathbb{Z}_{40}$.
Mit de, Satz von Lagrange und Aufgabe 1 erhalten wir 
![[Pasted image 20250407124841.png]]
 $$\begin{array}{ll}
   Z_0   = \mathbb Z_{40} & |G| = 40 \\
        Z_1 = \{[0]_{40}, [2]_{40}, [4]_{40}, ..., [28]_{40}\}, 
 &  |G_1| = 20\\
      Z_2 = \{[0]_{40}, [4]_{40}, [8]_{40}, [12]_{40}, [16]_{40}, [20]_{40}, [24]_{40}, [28]_{40}, [32]_{40}, [36]_{40}\}  &|G_2| = 10 \\
      Z_3 = \{[0]_{40}, [5]_{40}, [10]_{40}, [15]_{40}, [20]_{40}, [25]_{40}, [30]_{40}, [35]_{40}\} &|G_3| = 8\\
      Z_4 = \{[0]_{40}, [8]_{40}, [16]_{40}, [24]_{40}, [32]_{40}\} &|G_4| = 5 \\
      Z_5 = \{[0]_{40}, [10]_{40}, [20]_{40}, [30]_{40}\} &|G_5| = 4 \\
      Z_6 = \{[0]_{40}, [20]_{40}\} &|G_6| = 2 \\
       Z_7 = \{[0]_{40}\} &|G_7| = 1 \\
 \end{array}$$zusammengearbeitet mit:
Sandra Hörtnagel
12124470