### Aufgabe 5b (ii)

Gegeben ist:
$$
A = \mathbb{Z}_3^2 \times \mathbb{Z}_9 \times \mathbb{Z}_2^3 \times \mathbb{Z}_8^2
$$

Wir bestimmen zuerst die Ordnung eines Elements mit maximaler Ordnung (hihi).  
Da
$$
\text{kgV}(9,8) = 72 = 2^3 \cdot 3^2 \quad \text{und} \quad \gcd(3|9, 2|8) = 1
$$
ist unsere maximale Ordnung also **72** und ein Element davon wäre der Erzeuger von  
$$
\{(0,0)\} \times \mathbb{Z}_9 \times \{(0,0,0)\} \times (\mathbb{Z}_8 \times \{0\}) \cong \mathbb{Z}_{72},
$$
da 8 und 9 teilerfremd sind.

---

**Betrachten wir den Rest**, also eine Untergruppe
$$
\cong \mathbb{Z}_3^2 \times \mathbb{Z}_2^3 \times \mathbb{Z}_8,
$$
so hat das Element mit maximaler Ordnung:
$$
\text{kgV}(3,8) = 24 = 3 \cdot 2^3
$$
und ein Vertreter davon wäre der Erzeuger von
$$
(\mathbb{Z}_3 \times \{0\}) \times \{(0,0,0)\} \times \mathbb{Z}_8.
$$

---

**Betrachten wir wiederum den Rest**, also eine Untergruppe
$$
\cong \mathbb{Z}_3 \times \mathbb{Z}_2^3,
$$
so ist das Element mit maximaler Ordnung der Erzeuger von
$$
\mathbb{Z}_3 \times (\mathbb{Z}_2 \times \{0\}^2)
$$
und dieser hat Ordnung **6**.

---

**Betrachten wir nun eine Untergruppe**
$$
\cong \mathbb{Z}_2^2,
$$
so hat das Element mit der größten Ordnung **2**.

---

**Betrachten wir schließlich eine Untergruppe**
$$
\cong \mathbb{Z}_2,
$$
so haben wir wieder maximale Ordnung **2**.

---

Wir erhalten also eine Darstellung:
$$
A = \mathbb{Z}_{72} \oplus \mathbb{Z}_{24} \oplus \mathbb{Z}_6 \oplus \mathbb{Z}_2 \oplus \mathbb{Z}_2,
$$
womit auch die **Teilerkettenbedingung** erfüllt ist.
