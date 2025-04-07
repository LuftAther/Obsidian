Seien $A$ und $B$ Gruppen, und sei $\varphi : B \to \text{Aut}(A)$ ein Homomorphismus. Wir schreiben $\varphi_b$ statt $\varphi(b)$.

Auf der Menge $G := A \times B$ definieren wir eine Operation

$$
(a, b) \triangleright (a', b') := (a \ast \varphi_b(a'), b \ast b')
$$

1. Zeigen Sie, dass $(G, \triangleright, ?, ?)$ mit dieser Operation eine Gruppe ist. (Was muss man für die Fragezeichen einsetzen?)  
2. Zeigen Sie, dass $A \times \{1_B\} \triangleleft G$ und $\{1_A\} \times B \leq G$ gilt.  
3. Sei $A := \mathbb{Z}_4$, $B := \mathbb{Z}_2$, $\varphi : B \to \text{Aut}(A)$ nicht trivial. (Und zwar?) Zeigen Sie, dass $\{0_A\} \times B$ kein Normalteiler von $G$ ist.
---

#### Behauptung:
Sei $e_G := (1_A, 1_B), \text{ wobei } 1_A, 1_B \text{ die neutralen Elemente der Gruppen } A \text{ und } B \text{ sind.}$
Weiters definiere die Abbildung: 
$$
\star : G \to G, \quad (a,b) \mapsto \star(a,b) := (\varphi_{b^{-1}}(a^{-1}), b^{-1})
$$

Dann ist : $(G, \rtimes, e_G, \star)$ ist eine Gruppe, d.h., zu zeigen:

(a) $\rtimes$ ist wohldefiniert und assoziativ  
(b) $e_G$ ist das neutrale Element  
(c) $\star$ definiert ein inverses Element  

---
### (a) Wohldefiniertheit

![[Pasted image 20250407055155.png]]
Also zu zeigen ist, dass für alle $(a,b), (a',b')\in G$  $\exists! y \in G$, sodass $y = (a,b) \rtimes (a',b')$

Da $\varphi$ ein Homomorphismus ist und $\varphi_b$ ein Automorphismus, ist $\varphi_b(a') \in A$ wohldefiniert.  

$\Rightarrow$:

$$
(a\ast \varphi_b(a'), b\ast b')\in G
$$

---

### (b) Assoziativität

Zu zeigen ist:

$$
(a_1,b_1) \rtimes ((a_2,b_2) \rtimes (a_3,b_3)) = ((a_1,b_1) \rtimes (a_2,b_2)) \rtimes (a_3,b_3)
$$

Durch Berechnungen (siehe LaTeX-Datei) ergibt sich:

$$
(a_1,b_1) \rtimes ((a_2,b_2) \rtimes (a_3,b_3)) = ((a_1,b_1) \rtimes (a_2,b_2)) \rtimes (a_3,b_3)
$$

---

### (c) Neutrales Element

Zu zeigen ist:

$$
(a,b) \rtimes e_G = e_G \rtimes (a,b) = (a,b)
$$

Berechnung:

$$
(a,b) \rtimes (1_A,1_B) = (a\ast \varphi_b(1_A), b\ast 1_B) = (a\ast 1_A, b) = (a,b)
$$

---

### (d) Inverses Element

Zu zeigen ist:

$$
(a,b) \rtimes \star(a,b) = \star(a,b) \rtimes (a,b) = e_G
$$

Berechnung:

$$
(a,b) \rtimes \star(a,b) = (a\ast \varphi_b(\varphi_{b^{-1}}(a^{-1})), b\ast b^{-1}) = (1_A, 1_B)
$$

---

### (2) Normalteiler und Untergruppen

#### (a) $A \times \{1_B\} \vartriangleleft G$

Es gilt:

$$
(a,1_B) \rtimes (a',1_B) = (a \ast a', 1_B)
$$

Unter Konjugation:

$$
(g_1, g_2) \rtimes (a,1_B) \rtimes (\varphi_{g_2^{-1}}(g_1^{-1}), g_2^{-1}) = (g_1 \ast \varphi_{g_2}(a) \ast g_1^{-1}, 1_B)
$$

---

#### (b) $\{1_A\} \times B \leq G$

Abgeschlossenheit:

$$
(1_A, b) \rtimes (1_A, b') = (1_A, b \ast b') \in \{1_A\} \times B
$$

---

### (3) Gegenbeispiel

Wir betrachten:

$$
A = \mathbb{Z}_4, \quad B = \mathbb{Z}_2, \quad \varphi: \mathbb{Z}_2 \to \text{Aut}(\mathbb{Z}_4)
$$

$$
\varphi(0) = \text{id}, \quad \varphi(1) = \text{Negation}
$$

Berechnung:

$$
(3_A, 1_B) \rtimes (0_A, 1_B) \rtimes \star(3_A,1_B) = (2_A, 1_B) \notin \{0_A\} \times B
$$

Also ist $\{0_A\} \times B$ kein Normalteiler.
