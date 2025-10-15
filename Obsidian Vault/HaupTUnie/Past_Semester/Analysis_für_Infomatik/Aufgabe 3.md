
### a) Stetigkeit einer Funktion $f : \mathbb{R} \to \mathbb{R}$ an der Stelle $a \in \mathbb{R}$

Eine Funktion $f : \mathbb{R} \to \mathbb{R}$ heißt **stetig an der Stelle $a \in \mathbb{R}$**, wenn für jede Folge $(x_n)_{n \in \mathbb{N}}$ mit $\lim_{n \to \infty} x_n = a$ gilt:  
$$
\lim_{n \to \infty} f(x_n) = f(a).
$$  
Alternativ (und äquivalent) lässt sich die Stetigkeit auch so definieren:  
Die Funktion $f$ ist stetig an der Stelle $a$, wenn gilt:  
$$
\forall \varepsilon > 0 \; \exists \delta > 0 \; \forall x \in \mathbb{R} : |x - a| < \delta \Rightarrow |f(x) - f(a)| < \varepsilon.
$$

---

### b) Ableitung einer Funktion $f : \mathbb{R} \to \mathbb{R}$ an der Stelle $a$

Eine Funktion $f : \mathbb{R} \to \mathbb{R}$ heißt **an der Stelle $a$ differenzierbar**, wenn der folgende Grenzwert existiert:  
$$
\lim_{x \to a} \frac{f(x) - f(a)}{x - a}.
$$  
Existiert dieser Grenzwert, so nennt man ihn die **Ableitung von $f$ an der Stelle $a$** und schreibt:  
$$
f'(a) = \lim_{x \to a} \frac{f(x) - f(a)}{x - a}.
$$
