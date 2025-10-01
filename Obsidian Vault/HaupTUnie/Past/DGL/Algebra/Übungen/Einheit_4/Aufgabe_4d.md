### Aufgabe 4d. Gegeben eine Gruppenwirkung.

---

#### **Teil 1:**  
$f_g: X \to X, \, x \mapsto g \cdot x \)

**Zu zeigen:**  
$f_g$ist eine Bijektion und $g \mapsto f_g$ist ein $\text{Hom}(G) \).

---

## (1) Sei für $g \in G$$f_g: X \to X, \, x \mapsto g \cdot x$und $X^0$Gruppe der Permutationen von $X \).

### Zu zeigen:

1.1. $f_g$ist Bijektion.  
1.2. $g \mapsto f_g \in \text{Hom}(G, X^0) \).  

---

### **1.1.1. Injektivität**

Betrachte $f_g(x) = f_g(y) \implies g \cdot x = g \cdot y \).  
Da $G$eine Gruppe ist, gibt es zu jedem $g \in G$ein Inverses $g^{-1} \), so dass:  
$$
g^{-1} \cdot (g \cdot x) = x \quad \text{und} \quad g^{-1} \cdot (g \cdot y) = y
$$
$$
\implies x = y
$$

---

### **1.1.2. Surjektivität**

Für jedes $y \in X$existiert ein $x \in X$so dass $y = g \cdot x \).  

Wähle $x = g^{-1} \cdot y \implies y = g \cdot x \).

*Im Grunde haben wir aufgrund des Inversen in einer Gruppe eine eindeutige Inverse Funktion $\implies$Bijektiv.*

---

## **1.2.** $g \mapsto f_g$ist ein Homomorphismus von $G \to X^0: g \mapsto f_g \).

$$
f_{gh}(x) = (gh) \cdot x = g \cdot (h \cdot x) = f_g(f_h(x))
$$

$$
f_{gh} = f_g \circ f_h \implies \Psi(gh) = \Psi(g) \circ \Psi(h)
$$

$\{ g x : x \in X \} \)

**Bemerkung:** Der Beweis ist abgeschlossen.

---

## Kommentare:

- $G$ist eine Gruppe, weil $G$der erste Buchstabe von *Gruppe* ist und die Gruppenoperation als Abbildung von einer Gruppe definiert ist.  
- Wo der Faktor $y$steht, geht der Beweis genauso hypothetisch weiter.  

Für $g \in G$, definiere $f_g : X \to X$ durch $x \mapsto g \circ x$.

- **Zeige:** $f_g$ ist eine Bijektion.  

  **Beweis:**  
  - **Injektivität:** Sei $f_g(x) = f_g(y)$. Dann gilt:

    $$
    g \circ x = g \circ y \implies x = y
    $$

  - **Surjektivität:** Für jedes $y \in X$ existiert ein $x = g^{-1} \circ y \in X$, sodass

    $$
    f_g(x) = g \circ x = y
    $$

  Somit ist $f_g$ bijektiv.

- **Zeige:** Die Abbildung $g \mapsto f_g$ ist ein Homomorphismus von $G$ in die Gruppe der Permutationen von $X$.

  **Beweis:**  
  Für $g, h \in G$ und $x \in X$:

  $$
  f_{gh}(x) = (gh) \circ x = g \circ (h \circ x) = f_g(f_h(x))
  $$

  Also ist:

  $$
  f_{gh} = f_g \circ f_h
  $$

  Dies zeigt, dass $g \mapsto f_g$ ein Homomorphismus ist.

---

#### **Teil 2:**  

Zeige: Die Menge der Orbits $\{ Gx : x \in X \}$ ist eine Partition von $X$.

- **Äquivalenzrelation:** Definiere $\sim$ auf $X$ durch:

  $$
  x \sim y \iff \exists g \in G : gx = y
  $$

  - **Reflexivität:** Für jedes $x \in X$ gilt:

    $$
    e \in G, \quad ex = x \implies x \sim x
    $$

  - **Symmetrie:** Wenn $x \sim y$, dann existiert $g \in G$ mit:

    $$
    gx = y \implies g^{-1}y = x \implies y \sim x
    $$

  - **Transitivität:** Wenn $x \sim y$ und $y \sim z$, dann existieren $g, h \in G$ mit:

    $$
    gx = y, \quad hz = y \implies h^{-1}gz = x \implies x \sim z
    $$

  Die Menge der Äquivalenzklassen entspricht der Menge der Orbits $Gx$ für $x \in X$, also ist $\{Gx : x \in X\}$ eine Partition von $X$.

---

#### **Teil 3:**  

Zeige: $G_x \leq G$.

- **Definition:** Der Stabilisator $G_x$ ist:

  $$
  G_x = \{ g \in G : g \circ x = x \}
  $$

  - **Abgeschlossenheit:** Wenn $g, h \in G_x$, dann:

    $$
    (gh) \circ x = g \circ (h \circ x) = g \circ x = x
    $$

  - **Inverses:** Wenn $g \in G_x$, dann:

    $$
    g^{-1} \circ x = x
    $$

  Also ist $G_x$ eine Untergruppe von $G$.

---

#### **Teil 4:**  

Sei $x \in X$, $g \in G$, $y = g \circ x$. Zeige: $G_y = g G_x g^{-1}$.

- **Beweis:**  
  Für $h \in G_y$:

  $$
  h \circ y = y = g \circ x
  $$

  Also:

  $$
  h \circ g \circ x = g \circ x \implies g^{-1} h g \circ x = x
  $$

  Also:

  $$
  g^{-1} h g \in G_x \implies h \in g G_x g^{-1}
  $$

  Also gilt:

  $$
  G_y = g G_x g^{-1}
  $$

---

#### **Teil 5:**  

Sei $(\alpha, v) \mapsto \alpha \cdot v$ die Wirkung der multiplikativen Gruppe $G := K^{\times}$ des Körpers $K$ auf den $K$-Vektorraum $V$.

- **Bestimme $G \circ v$:**  

  Die Wirkung von $G$ auf $v \in V$ ist gegeben durch:

  $$
  G \circ v = \{ \alpha \cdot v : \alpha \in K^{\times} \}
  $$

  Das ist die Menge aller skalaren Vielfachen von $v$ in $V$, also eine Gerade durch den Nullpunkt (falls $v \neq 0$).

- **Bestimme $G_v$ für $v \in V$:**  

  $G_v = \{ \alpha \in K^{\times} : \alpha \cdot v = v \}$

  Falls $v \neq 0$:

  $$
  G_v = \{ 1 \}
  $$

  Falls $v = 0$:

  $$
  G_v = G = K^{\times}
  $$

---

Möchtest du, dass ich dir auch mit Aufgabe 4e weiterhelfe? 😊
