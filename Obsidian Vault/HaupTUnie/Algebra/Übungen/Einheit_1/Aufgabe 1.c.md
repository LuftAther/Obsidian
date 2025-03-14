## Aufgabenstellung:

 Sei $(V, \leq)$ Verbandsordnung. Wir definieren 
 $$a \lor b := \sup\{a,b\}$$$$a \land b := \inf\{a,b\}$$ für alle $a, b \in V$. Weiters sei für alle $a, b, c \in V$

$$ m^-(a, b, c) := (a \lor b) \land (a \lor c) \lor (b \land c) $$
$$ m^+(a, b, c) := (a \lor b) \land (a \lor c) \land (b \lor c) $$

==(1)==Zeigen Sie $m^-(a, b, c) \leq m^+(a, b, c)$ für alle $a, b, c$. Hinweis: Vergleichen Sie z.B. $a \land b$ mit $a \lor b$, $a \lor c$, $b \lor c$. ==(2)==Finden Sie einen Verband, wo Gleichheit nicht immer gilt.  
(Hinweis: Z.B. Unterräume eines zwei-dimensionalen Vektorraums.) ==(3)==Wenn $(V, \leq)$ eine lineare Ordnung ist, finden Sie eine konzise Beschreibung von $m^+(a, b, c)$ und $m^-(a, b, c)$.

**Anmerkung:** Wenn z.B. $a = b$ gilt, dann ist $m^+(a, b, c) = m^-(a, b, c) = a$; daher ist die Beschreibung von $m(a, b, c)$ vor allem für paarweise verschiedene $a, b, c$ interessant.

#### (1)
$a \land b = \inf \{a, b\} : a \land b \leq a \vee b, a \land b \leq a \vee c, a \land b \leq b \vee c$   
$a \land c = \inf \{a, c\} : a \land c \leq a \vee c, a \land c \leq a \vee b, a \land c \leq c \vee b$   
$b \land c = \inf \{b, c\} : b \land c \leq b \vee c, b \land c \leq b \vee a, b \land c \leq c \vee a$   
$\Rightarrow m^-$ ist unterrre Schranke von $a \vee b, a \vee c, b \vee c$ und damit natürlich auch von $m⁺$

---

#### (2)
Betrachte $(V(\mathbb{R²}),\subseteq) \dots$ die Menge aller Teilmängen von $\mathbb{R}²$ mit der teilmängen Realation 
Dann betrachte die vektorren $v_{1} = \left(\left[\begin{array}{c} 0 \\1\end{array}\right]\right) =:a$, $v_{2} = \left(\left[\begin{array}{c} 1 \\1\end{array}\right]\right) =:b$, $v_{3} = \left(\left[\begin{array}{c} -1 \\-1\end{array}\right]\right)=: c$
Wo sind $\left(\{0\} < \{0\}\right) \cdot \left(\{0\}\right) \{1\}$  

Dann haben wir
$$ m^-(a,b,c) = (a \cap b) + (a \cap c) + (b \cap c) = \{0\} + \{0\} + \{0\} = \{0\} $$  
$$ m^+(a,b,c) = (a + b) \cap (a + c) \cap (b + c) = \mathbb{R}^2 \cap \mathbb{R}^2 \cap \mathbb{R}^2 = \mathbb{R}^2 $$  

---

#### (3)
**Für lineare Ordnung:**  

$$ m^- := \sup \{\inf \{a, b\}, \inf \{b, c\}, \inf \{a, c\}\} $$  Für $m⁻:$
- $c \leq b \leq a$: $m^- = \sup \{c, b\} = b$  
- $c \leq a \leq b$: $m^- = \sup \{c, a\} = a$  
- $a \leq b \leq c$: $m^- = \sup \{a, b\} = b$  
- $b \leq a \leq c$: $m^- = \sup \{b, a\} = a$  
- $b \leq c \leq a$: $m^- = \sup \{b, c\} = c$  
- $a \leq c \leq b$: $m^- = \sup \{a, c\} = c$  
Für $m⁺:$
 - $c \geq b \geq a$: $m^+ = \inf \{c, b\} = b$  
- $c \geq a \geq b$: $m^+ = \inf \{c, a\} = a$  
- $a \geq b \geq c$: $m^+ = \inf \{a, b\} = b$  
- $b \geq a \geq c$: $m^+ = \inf \{b, a\} = a$  
- $b \geq c \geq a$: $m^+ = \inf \{b, c\} = c$  
- $a \geq c \geq b$: $m^+ = \inf \{a, c\} = c$ 
d.h.:  
$b \in \{x, y, z\} \exists a , c \in \{x, y, z\}:a \leq b \leq c \Rightarrow b = m^-(x, y, z) = m^+(x, y, z)$
