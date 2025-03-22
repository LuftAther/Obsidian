# Aufgabe 2f

Beantworten Sie die folgenden Fragen:  
(Beweisen Sie oder finden Sie ein Gegenbeispiel.)

1. Sei $(A, +, 0, -)$ eine Gruppe (und daher auch eine Halbgruppe), und $(B, +)$ eine Unterhalbgruppe von $(A, +)$.  
   Kann $B$ durch geeignete Wahl von Operationen $0'$, $-'$ zu einer Gruppe $(B, +, 0', -')$ gemacht werden?

   *(Analog sind die folgenden Aufgaben zu verstehen, d.h., es geht immer darum, neue Operationen/Konstante hinzuzufügen, niemals neue Elemente.)*

2. Sei $(A, +, 0)$ ein Monoid (und daher auch eine Halbgruppe $(A, +)$), und $B$ eine Unterhalbgruppe von $A$, die zu einem Monoid gemacht werden kann.  
   Ist $B$ ein Untermonoid?

3. Sei $A$ eine Gruppe (und daher auch eine Halbgruppe), und $B$ eine Unterhalbgruppe von $A$, die zu einer Gruppe gemacht werden kann.  
   Ist $B$ eine Untergruppe?

4. Sei $A$ ein 1-Ring und $B$ ein Unterring, der zu einem 1-Ring gemacht werden kann.  
   Ist $B$ ein Unter-1-Ring?
---
# Aufgabe 2f – Unterstrukturen und Erweiterbarkeit

## (1) Halbgruppe $A$, $B \subseteq A$ Unterhalbgruppe  
**Frage**: Kann $B$ durch Definition von $0'$ und $-'$ zu einer Gruppe gemacht werden?

**Gegenbeispiel**:  
- $A = (\mathbb{R}^+, \cdot)$ ist eine Gruppe  
- $B = (\mathbb{N} \setminus \{0\}, \cdot)$ ist eine Unterhalbgruppe

Wähle $1$ als neutrales Element ⇒ dann müsste für jedes $n \in B$ auch $n^{-1} \in B$ gelten  
Aber z. B. $1/2 \notin \mathbb{N}$ ⇒ kein Inverses

→ $B$ kann **nicht** zu einer Gruppe gemacht werden

---

## (2) $(A, +, 0)$ Monoid, $B \subseteq A$ Unterhalbgruppe  
**Frage**: Kann $B$ mit neutralem Element $0' \in B$ zu einem Monoid gemacht werden?

**Beispiel**:  
- $A = (\mathbb{N}, \max, 0)$ ist ein Monoid  
- $B = (\mathbb{N} \setminus \{0\}, \max)$ ist Halbgruppe, **aber** $0 \notin B$ ⇒ kein neutrales Element in $B$

→ $B$ ist **kein** Untermonoid

---

## (3) $(A, +, 0, -)$ Gruppe, $B \subseteq A$ Unterhalbgruppe  
**Frage**: Kann $B$ durch Definition von $-'$ und $0'$ zu einer Gruppe gemacht werden?

**Beweis**: Zeige, dass $0' = 0$

Sei $b \in B$, dann:

$$
b + 0' = b \Rightarrow 0' = -b + b = 0 \tag{1}
$$

Außerdem:
$$
b + (-b) = 0 \Rightarrow -b = -_B b \tag{2}
$$

⇒ Da $B$ eine Unterhalbgruppe ist und $(B, +, 0, -)$ eine Gruppe ist, folgt:  
$B$ ist **Untergruppe** von $A$

---

## (4) $A$ ist 1-Ring: $(A, +, -, 0)$ abelsche Gruppe, $(A, \cdot, 1)$ kommutatives Monoid, mit distributivem Gesetz

**Frage**: Wenn $B \subseteq A$ ein Unterring ist, der zu einem 1-Ring gemacht werden kann (mit $1 \in B$), ist $B$ dann ein Unter-1-Ring?

**Gegenbeispiel**:  
- $A = (\mathbb{R}, +, -, 0, \cdot, 1)$  
- $B = 2\mathbb{Z}$ (gerade Zahlen)

⇒ $B$ ist Unterring von $\mathbb{R}$  
**aber**: $1 \notin 2\mathbb{Z}$ ⇒ $B$ ist **kein** Unter-1-Ring

---
