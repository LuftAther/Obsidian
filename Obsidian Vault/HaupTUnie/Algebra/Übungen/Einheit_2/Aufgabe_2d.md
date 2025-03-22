# Aufgabenstellung:

Sei $(G, \cdot, 1, ^{-1})$ eine endliche Gruppe, $p \neq q$ Primzahlen, $g_1, g_2 \in G \setminus \{1\}$ und $g_1^p = g_2^q = 1$. 
Zeige, dass $|G|$ ein Vielfaches von $p \cdot q$ ist.

(Daraus folgt dann z.B. auch, dass eine Untergruppe der $S_3$, die sowohl eine „Rotation“ als auch eine „Spiegelung“ enthält, schon ganz $S_3$ sein muss; was Sie ja in Aufgabe 1d bereits gezeigt haben.)

---
# Beweis zu Aufgabe 2d: $g_1^p = g_2^q = 1$ ⇒ $|G|$ ist Vielfaches von $p \cdot q$

Gegeben: Endliche Gruppe $G$, $g_1, g_2 \in G$, $p \neq q$ Primzahlen, $g_1^p = g_2^q = 1$.

## (1) Lemma:

Falls $g^p = 1$ für eine Primzahl $p$, so ist $p$ das **minimale** $n \in \mathbb{N}$ mit $g^n = 1$

**Begründung:**  
Annahme: $n < p$ sei kleinstes $n$ mit $g^n = 1$ ⇒ $p = m \cdot n$  
Dann:

$$
g^p = (g^n)^m = 1^m = 1
$$

⇒ Widerspruch zu Minimalität von $p$, wenn $n < p$

## (2) Lemma:

Die Potenzen $(g^i g_2^j)$ für $i = 1, \dots, p$, $j = 1, \dots, q$ sind **paarweise verschieden**

Sei:

$$
g_1^i g_2^j = g_1^k g_2^\ell
$$

Dann:

$$
g_1^{i - k} = g_2^{\ell - j}
$$

Da $g_1^p = 1$ und $g_2^q = 1$, folgt:  
$p \mid (i - k)$ und $q \mid (\ell - j)$ ⇒ Nur möglich, wenn $i = k$, $j = \ell$ wegen $p \neq q$

## (3) Lemma:

Setze $H := \{ g_1^n g_2^m \mid 0 \leq n < p,\ 0 \leq m < q \} \subseteq G$  
Dann ist $H$ eine **Untergruppe**.

**Beweis:**

Für $a = g_1^n g_2^m$ und $b = g_1^{n'} g_2^{m'} \in H$ gilt:

$$
a \cdot b = g_1^n g_2^m g_1^{n'} g_2^{m'} = g_1^{n + n'} g_2^{m + m'} \in H
$$

(wenn man Modulo $p$, $q$ rechnet)

Für Inverses:

$$
a^{-1} = (g_1^n g_2^m)^{-1} = g_2^{-m} g_1^{-n} = g_1^{p - n} g_2^{q - m} \in H
$$

⇒ $H$ ist Untergruppe mit $|H| = p \cdot q$

## (4) Schlussfolgerung:

Wir haben zwei Untergruppen:

- $L := \langle g_1 \rangle$ mit $|L| \mid p$
- $H := \langle g_2 \rangle$ mit $|H| \mid q$

Nach dem **Lemma von Lagrange**:

- $p \mid |G|$
- $q \mid |G|$
- $p$ und $q$ Primzahlen ⇒ $p \cdot q \mid |G|$

$\blacksquare$
