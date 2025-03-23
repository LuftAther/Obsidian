# Aufgabenstellung:

Sei $p$ eine Primzahl.

1. Zeige: Es gibt bis auf Isomorphie nur eine Gruppe der Ordnung $p$.
   **Hinweis**: Betrachte das Erzeugnis von $g \neq e$; zeige Isomorphismus zu $\mathbb{Z}_p$.
2. Zeige: Es gibt mehr als eine (bis auf Isomorphie) Gruppe der Ordnung $p^2$.
3. Zeige: Es gibt mehr als eine (bis auf Isomorphie) Gruppe der Ordnung $6$.
---
#### 1) Es gibt bis auf Isomorphie nur eine Gruppe der Ordnung $p$ (Primzahl)

Sei $|G| = p$ eine Primzahl, $(G, \cdot, {}^{-1}, 1)$ eine Gruppe.
Dann gilt nach **Lagrange**: $G$ hat genau die Untergruppen $\{1\}$ und $G$ selbst.
Daher: $\langle g \rangle = G \quad \text{für } g \neq 1$
Also insbesondere:$G = \{ g^n : n \in \mathbb{N} \}$
Es gilt sogar:
$$G = \{ g^n : n \in \{1, \dots, p\} \} \quad \text{und} \quad g^p = 1 \tag{$\alpha$}$$
Wir betrachten für festes $g \in G$ die Abbildung:
$$\varphi : G \to \mathbb{Z}_{p \quad}g^{n} \mapsto \bar{n} \quad \text{für } n \in \{0, \dots, p-1\}$$

$\varphi$ ist wohldefiniert, da $g^n$ eindeutig jedes $h \in G$ trifft. Seien $a = g^n$, $b = g^m$ mit $n, m \in \{0, \dots, p-1\}$, dann gilt:

$$\varphi(a \cdot b) = \varphi(g^n \cdot g^m) = \varphi(g^{n+m}) = \varphi(g^{n+m \bmod p}) = \overline{n+m \text{ mod }p}$$
Also:
$$\varphi(a \cdot b) = \varphi(g^n) \cdot \varphi(g^m) = \varphi(a) \cdot \varphi(b)$$

 $\Rightarrow \varphi$ ist ein **Gruppenhomomorphismus** und **Bijektion**.
**Folgerung:**  
$G \cong \mathbb{Z}_p$ für alle Gruppen $ G$  mit  $|G| = p \Rightarrow$ alle zyklischen Gruppen der Ordnung  $p$  sind isomorph. $\square$

---

**Beweis von ($\alpha$):**  
Da $G = \{ g^n : n \in \mathbb{N} \}$, gibt es $m,n \in \mathbb{N}, n < m$ mit $g^n = g^m$.  
$\Rightarrow k := m - n > 0$, also $g^k = 1$ 
$\Rightarrow G = \{ g^n : n \in \{1, \dots, k\} \}$

Falls $k > p$, gibt es wieder nach derselben Konstruktion ein $p \leq \ell < k$ mit $g^\ell = 1$
$\Rightarrow G = \{ g^n : n \in \{1, \dots, \ell\} \}$ Dieser Prozess endet nach endlich vielen Schritten mit:
$$G = \{ g^n : n \in \{1, \dots, p\} \} \quad \text{und} \quad g^p = 1$$

#### 2) Es gibt mehr als eine (bis auf Isomorphie) Gruppe der Ordnung $p^2$.

$|G| = p^2$, $p$ Primzahl, $(G, \cdot, {}^{-1}, 1)$

**Beispiel:** $(\mathbb{Z}_{p^2}, +)$ und $(\mathbb{Z}_p^2, +)$

- $\mathbb{Z}_{p^2}$ hat als Untergruppe $\{ \overline{0}, \overline{p}, \dots, \overline{(p-1)p} \}$ der Ordnung $p$
- $\mathbb{Z}_p^2$ hat keine nicht-trivialen Untergruppen der Ordnung $p$, also keine

Daher wäre mit Bijektion $\varphi : \mathbb{Z}_{p^2} \to \mathbb{Z}_p^2$  
⇒ $\varphi(H)$ keine Untergruppe, also $\varphi$ **kein Isomorphismus**

---

#### 3) Es gibt mehr als eine (bis auf Isomorphie) Gruppe der Ordnung $6$.
$|\mathbb{Z}_6| = 6$ und $|S_3| = 6$, aber $S_3$ hat **mehr Untergruppen** als $\mathbb{Z}_6$ (nachprüfen!)


Haben zwei endliche Gruppen $G$, $G'$ unterschiedliche Anzahl an Untergruppen,  
dann gilt:

Seien $(H_i)_{i \in \{1, \dots, n\}}$ und $(H_i')_{i \in \{1, \dots, m\}}$ die jeweiligen Untergruppen mit jeweils $|H_i| = |H_j'| = k$ für alle $i, j$,  
so kann (o.B.d.A. $n > m$) kein Isomorphismus $\varphi$ existieren mit  
$$ \varphi(H_i) \cong H_i' \text{ paarweise verschieden} $$

⇒ keine Bijektion ⇒ **kein Isomorphismus**. $\square$
