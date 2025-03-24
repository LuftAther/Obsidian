# Aufgabenstellung:

Betrachten Sie die Algebren $(\mathbb{Z}, \cdot)$ und $(\mathbb{Z}, +)$ mit den üblichen Operationen.  
Bestimmen Sie alle Homomorphismen (siehe Definition 1.1.29):

1. von $(\mathbb{Z}, \cdot)$ nach $(\mathbb{Z}, +)$,
2. von $(\mathbb{Z}, \cdot)$ nach $(\mathbb{Z}, +)$,
3. von $(\mathbb{Z}, +)$ nach $(\mathbb{Z}, \cdot)$.

Zu welchen Klassen von Algebren (Gruppen, Monoide, Körper etc.) 
gehören $(\mathbb{Z}, +)$ bzw. $(\mathbb{Z}, \cdot)$,  
gegebenenfalls nach Ergänzung mit geeigneten Operationen (wie in Aufgabe 2f)?

---

### 1) $f: \mathbb{Z} \to \mathbb{Z}$ mit $f(x + y) = f(x) + f(y)$

Gesucht: Homomorphismen von $(\mathbb{Z}, +)$ nach $(\mathbb{Z}, +)$

- $(\mathbb{Z}, +, 0)$ ist eine Gruppe  
- Daher gilt für Homomorphismen:
  - $f(-x) = -f(x)$
  - $f(0) = 0$

⇒ Jeder Homomorphismus $f$ ist von der Form $f(x) = kx$ mit $k \in \mathbb{Z}$  
⇒ **Alle** Homomorphismen: $f(x) = kx$, $k \in \mathbb{Z}$

---

### 2) $f: \mathbb{Z} \to \mathbb{Z}$ mit $f(x \cdot y) = f(x) + f(y)$

Homomorphismus von $(\mathbb{Z}, \cdot)$ nach $(\mathbb{Z}, +)$

- $(\mathbb{Z}, \cdot, 1)$ ist ein Monoid  
- Sei $f(1)$ gegeben, dann:

$$f(x \cdot 1) = f(x) + f(1) \Rightarrow f(x) = f(x) + f(1) \Rightarrow f(1) = 0$$
- Weiter: $f(0) = f(0 \cdot 1) = f(0) + f(1) = f(0) \Rightarrow f(1) = 0$
- Auch: $f(x \cdot (-1)) = f(-x) = f(x) + f(-1) \Rightarrow f(-x) = f(x) + f(-1)$

Vergleiche mit $f(-x) = -f(x)$ aus Gruppeneigenschaft ⇒ $f(x) = 0$
**$\Rightarrow$Null-Homomorphismus**.

---

### 3) $f: (\mathbb{Z}, +) \to (\mathbb{Z}, \cdot)$

Homomorphismus von $(\mathbb{Z}, +)$ nach $(\mathbb{Z}, \cdot)$

Gesucht ist eine Abbildung $f$ so dass: $$f(x + y) = f(x) \cdot f(y)$$
Betrachte:
- $f(0) = f(0 + 0) = f(0)^2 \Rightarrow f(0) = 0$ oder $f(0) = 1$
- Ist $f(0) = 0 \Rightarrow \forall x$: $f(x) = f(x + 0) = f(x) \cdot f(0) = f(x) \cdot 0 = 0$
	$\Rightarrow$ Entweder $f \equiv 0$ oder $f(0) \equiv 1$

- Sei also  $f(0) = 1$, dann:
  $f(a + (-a)) = f(0) = 1$, aber auch $f(a) \cdot f(-a) = 1$ ⇒ $f(-a) = f(a)^{-1}$
	- Wähle z. B. $x = y = 2 \Rightarrow f(4) = f(2 + 2) = f(2)^2 = f(2 \cdot 2)$ 
		$\Rightarrow$ Es muss sein: $f(x + y) = f(x \cdot y)$ für alle $x,y$

Das erhällt man  **nur** im fall $f \equiv 1$ oder $f \equiv 0$  $\Rightarrow$ **konstante Homomorphismen**.

---

## Zusammenfassung:

- Homomorphismen $(\mathbb{Z}, +) \to (\mathbb{Z}, +)$: $f(x) = kx$
- Homomorphismen $(\mathbb{Z}, \cdot) \to (\mathbb{Z}, +)$: nur $f(x) = 0$
- Homomorphismen $(\mathbb{Z}, +) \to (\mathbb{Z}, \cdot)$: $f(x) = 1$ oder $f(x) = 0$
