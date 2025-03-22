# Aufgabenstellung:

Sei $p$ eine Primzahl.

1. Zeige: Es gibt bis auf Isomorphie nur eine Gruppe der Ordnung $p$.
   **Hinweis**: Betrachte das Erzeugnis von $g \neq e$; zeige Isomorphismus zu $\mathbb{Z}_p$.
2. Zeige: Es gibt mehr als eine (bis auf Isomorphie) Gruppe der Ordnung $p^2$.
3. Zeige: Es gibt mehr als eine (bis auf Isomorphie) Gruppe der Ordnung $6$.
---
# Aufgabe 2e – Isomorphieklassen kleiner Gruppen

## (1) Es gibt bis auf Isomorphie nur eine Gruppe der Ordnung $p$ (Primzahl)

Sei $|G| = p$ mit $p$ prim, dann ist jede Gruppe $G = \langle g \rangle$ zyklisch.  
Nach Lagrange hat $G$ genau $p$ Untergruppen $\{1\}, \langle g \rangle, \dots$

Betrachte:
$$
G = \{ g^n \mid n \in \mathbb{N} \}
$$

Es gibt sogar:
$$
G = \{ g^n \mid n \in \{0, 1, \dots, p-1 \} \}, \quad \text{und } g^p = 1 \tag{$\alpha$}
$$

### Konstruktion eines Isomorphismus:

Definiere $\varphi: G \to \mathbb{Z}_p$ durch:

$$
\varphi(g^n) = n \mod p
$$

Für $a = g^m$, $b = g^n \in G$ gilt:

$$
\varphi(ab) = \varphi(g^{m+n}) = m+n \mod p = \varphi(a) + \varphi(b)
$$

⇒ $\varphi$ ist Homomorphismus, bijektiv, also Isomorphismus.  
Alle Gruppen der Ordnung $p$ sind also isomorph zu $(\mathbb{Z}_p, +)$ ⬛

**Beweis von $(\alpha)$:**  
Falls $g^k = 1$ für $k < p$, dann teilt $k$ die Ordnung von $g$.  
Da $p$ minimal ist, folgt: $k = p$, also $g^p = 1$

---

## (2) Es gibt mehr als eine Gruppe der Ordnung $p^2$

Beispiel:

- $(\mathbb{Z}_p \times \mathbb{Z}_p, +)$  
- $(\mathbb{Z}_{p^2}, +)$

Die Gruppe $\mathbb{Z}_p \times \mathbb{Z}_p$ hat **mehr Untergruppen** als $\mathbb{Z}_{p^2}$:

- In $\mathbb{Z}_{p^2}$ gibt es nur eine Untergruppe der Ordnung $p$
- In $\mathbb{Z}_p \times \mathbb{Z}_p$ gibt es mehrere

Daher kann kein Isomorphismus existieren, da die Gruppen unterschiedliche Untergruppenstrukturen besitzen.

---

## (3) Es gibt mehr als eine Gruppe der Ordnung $6$

Beispiel:

- $(\mathbb{Z}_6, +)$ hat 2 Untergruppen
- $S_3$ hat mehr als 2 Untergruppen (z. B. $\langle (1\,2) \rangle$, $\langle (1\,2\,3) \rangle$, ...)

Allgemein: Wenn zwei Gruppen $G$, $G'$ unterschiedlich viele Untergruppen haben,  
können sie **nicht isomorph** sein.

⇒ z. B. $\mathbb{Z}_6 \not\cong S_3$ ⬛
