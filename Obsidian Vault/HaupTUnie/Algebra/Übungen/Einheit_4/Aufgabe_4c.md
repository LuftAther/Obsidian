### Aufgabe 4c.

Sei $n = td$. Zeigen Sie, dass die zyklische Gruppe $\mathbb{Z}_n = \mathbb{Z}/n\mathbb{Z}$genau eine Untergruppe mit $t$Elementen hat, nämlich die von $d + n\mathbb{Z}$erzeugte.  
(Das folgt aus Satz 3.2.4.15. Geben Sie einen Beweis, der sich nicht einfach auf diesen Satz verlässt.)  
Finden Sie alle Untergruppen von $\mathbb{Z}_{40}$.

---

#### **Beweis:**

Wir betrachten die zyklische Gruppe $\mathbb{Z}_n = \{ 0, 1, \ldots, n-1 \}$mit Addition modulo $n$. Da $n = td$, ist $d$ein Teiler von $n$. Wir wollen zeigen, dass es genau eine Untergruppe von $\mathbb{Z}_n$mit $t$Elementen gibt.

**1. Konstruktion einer Untergruppe:**  
Die von $d$erzeugte Untergruppe ist:

$$
\langle d \rangle = \{ 0, d, 2d, \ldots, (t-1)d \}
$$

Da $d$ein Teiler von $n$, ist $td = n$, also:

$$
t = \frac{n}{d}
$$

Diese Untergruppe hat somit genau $t$Elemente. Da $\mathbb{Z}_n$zyklisch ist, ist jede Untergruppe ebenfalls zyklisch.

**2. Eindeutigkeit:**  
Nehmen wir an, es gibt eine weitere Untergruppe $H \subseteq \mathbb{Z}_n$mit $t$Elementen. Da $H$zyklisch ist, gibt es ein $k \in \mathbb{Z}_n$mit:

$$
H = \langle k \rangle
$$

Die Ordnung von $H$ist $t$, d.h. $k$ist ein Element von $\mathbb{Z}_n$mit Ordnung $t$. Die Ordnung eines Elements $k \in \mathbb{Z}_n$ist:

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

Also ist $H = \langle d \rangle$. Das zeigt, dass es genau eine Untergruppe mit $t$Elementen gibt.

---

#### **Untergruppen von $\mathbb{Z}_{40}$:**

Die Divisoren von $40$sind: $1, 2, 4, 5, 8, 10, 20, 40$.  
Für jeden dieser Divisoren $d$gibt es genau eine Untergruppe von $\mathbb{Z}_{40}$mit $\frac{40}{d}$Elementen. Diese sind:

- $d = 1$: $\langle 1 \rangle = \mathbb{Z}_{40}$mit $40$Elementen.
- $d = 2$: $\langle 2 \rangle = \{ 0, 2, 4, \ldots, 38 \}$mit $20$Elementen.
- $d = 4$: $\langle 4 \rangle = \{ 0, 4, 8, \ldots, 36 \}$mit $10$Elementen.
- $d = 5$: $\langle 5 \rangle = \{ 0, 5, 10, \ldots, 35 \}$mit $8$Elementen.
- $d = 8$: $\langle 8 \rangle = \{ 0, 8, 16, 24, 32 \}$mit $5$Elementen.
- $d = 10$: $\langle 10 \rangle = \{ 0, 10, 20, 30 \}$mit $4$Elementen.
- $d = 20$: $\langle 20 \rangle = \{ 0, 20 \}$mit $2$Elementen.
- $d = 40$: $\langle 40 \rangle = \{ 0 \}$mit $1$Element.
