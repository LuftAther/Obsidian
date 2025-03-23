# Aufgabenstellung:

Sei $(G, \cdot, 1, ^{-1})$ eine endliche Gruppe, $p \neq q$ Primzahlen, $g_1, g_2 \in G \setminus \{1\}$ und $g_1^p = g_2^q = 1$. 
Zeige, dass $|G|$ ein Vielfaches von $p \cdot q$ ist.

(Daraus folgt dann z.B. auch, dass eine Untergruppe der $S_3$, die sowohl eine „Rotation“ als auch eine „Spiegelung“ enthält, schon ganz $S_3$ sein muss; was Sie ja in Aufgabe 1d bereits gezeigt haben.)

---
#### 1) Lemma:

Falls $g^p = 1$ mit einer Primzahl $p$, so ist $p$ auch  
$$ \min \{ n \in \mathbb{N} \mid g^n = 1 \} $$

**Annahme:** $n \neq p$ sei Minimum ⇒  
$1$-Stellen sind genau, wenn $(g^n)^m = g^{nm} = 1$, aber dann $p = n \cdot m \Rightarrow$ $\lightning$

---

#### 2) Lemma:

Die Menge $\left(g^n\right)_{n \in \{1, \dots, p\}}$ ist paarweise verschieden.

Sei $g^i = g^j$ mit $i, j \in \{1, \dots, p\}$, so gilt:  
$$ g^{j - i} = 1 $$  
und da $j - i < p$, steht das im Widerspruch zu (1).  
⇒ $j = i$

#### 3) Lemma:

$$H := \{ g^n : n \in \{1, \dots, p\} \} \subseteq G \text{ ist Untergruppe}$$

Seien $a, b \in H$, dann $a = g^n$, $b = g^m$ für bestimmte $n, m \in \{1, \dots, p\}$

⇒  $a \cdot b = g^{n+m}$ 
Falls $n + m > p$ gilt:  $a \cdot b = g^{n+m-p} \quad (\text{da} g^p = 1)$$\Rightarrow g^{n+m-p} \in H$

Außerdem:  
Zu $a = g^n$ existiert $a^{-1} = g^{-n}$, sodass:  
$$a \cdot a^{-1} = 1 \Rightarrow 1 \in H$$

#### 4)
Wir haben nun wegen (2) und (3) zwei Untergruppen $L$ und $H$ mit:

- $|L| = p$
- $|H| = q$

und nach **Lagrange** gilt:  
- $p \mid |G|$  
- $q \mid |G|$  

Da $p, q$ Primzahlen sind, gilt:
$$ p \cdot q \mid |G| \quad \square $$
$\blacksquare$
