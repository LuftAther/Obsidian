
---
![[Pasted image 20250612063943.png]]
- **1. Summen-Metrik ($d = d_1$)**

$$
d_1(\vec{x}, \vec{y}) = |x_1 - y_1| + |x_2 - y_2|
$$

Einheitskugel:
$$
|x| + |y| \leq 1
$$

**Geometrie**: Eine **Raute** (Rhombus), deren Eckpunkte auf der $x$- und $y$-Achse bei $\pm1$ liegen.

- **2. Euklidische Metrik ($d = d_2$)**

$$
d_2(\vec{x}, \vec{y}) = \sqrt{(x_1 - y_1)^2 + (x_2 - y_2)^2}
$$

Einheitskugel:
$$
x^2 + y^2 \leq 1
$$

**Geometrie**: Ein **Kreis** mit Radius $1$ um den Ursprung.

-  **3. Maximums-Metrik ($d = d_\infty$)**

$$
d_\infty(\vec{x}, \vec{y}) = \max\left\{ |x_1 - y_1|, |x_2 - y_2| \right\}
$$

Einheitskugel:
$$
\max\{|x|, |y|\} \leq 1
$$

**Geometrie**: Ein **Quadrat**, dessen Seiten parallel zu den Koordinatenachsen verlaufen. Die Ecken liegen bei $(\pm1, \pm1)$.

- **4. Hamming-Metrik ($d = d_H$)**

$$
d_H(\vec{x}, \vec{y}) = \#\{i \mid x_i \neq y_i\}
$$

Für $\vec{y} = \vec{0}$ ergibt sich:
- $d_H(\vec{x}, \vec{0}) = 0$ nur für $\vec{x} = \vec{0}$
- $d_H(\vec{x}, \vec{0}) = 1$ für $\vec{x}$ mit genau einer von zwei Koordinaten $\neq 0$

Einheitskugel:
$$
\overline{K}_{d_H}(\vec{0}, 1) = \{(x, 0) \mid x \in \mathbb{R}\} \cup \{(0, y) \mid y \in \mathbb{R}\}
$$

**Geometrie**: Die **beiden Achsen ohne den Ursprung entfernt**, d.h. **$x$- und $y$-Achse**, aber ohne Punkte, wo beide Koordinaten $\neq 0$ sind.

- **Zusammenfassung (Skizzenbeschreibung):**

| Metrik       | Geometrie der Einheitskugel                              |
|--------------|----------------------------------------------------------|
| $d_1$        | Raute (Ecken bei $(0,1)$, $(1,0)$, $(0,-1)$, $(-1,0)$)   |
| $d_2$        | Kreis mit Radius $1$                                     |
| $d_\infty$   | Quadrat, Seitenlänge $2$, Ecken bei $(\pm1, \pm1)$       |
| $d_H$        | Vereinigung der Koordinatenachsen, ohne Schnittpunkt     |

---

## Aufgabe 363: Tangenten mit Steigung $\pm 1$
![[Pasted image 20250612064123.png]]
Gegeben ist die Kurve:
$$
2x^2 - 4xy + 9y^2 = 36
$$

Ableitung:
$$
\frac{dy}{dx} = \frac{4y - 4x}{-4x + 18y}
$$

### Fall $\frac{dy}{dx} = 1$:
$$
\begin{split}
\frac{4y - 4x}{-4x + 18y} &= 1 \\
4y - 4x &= -4x + 18y \\
14y &= 0 \Rightarrow y = 0 \Rightarrow 2x^2 = 36 \Rightarrow x = \pm 3\sqrt{2}
\end{split}
$$

### Fall $\frac{dy}{dx} = -1$:
$$
\begin{split}
\frac{4y - 4x}{-4x + 18y} &= -1 \\
4y - 4x &= 4x - 18y \\
8x &= 22y \Rightarrow x = \frac{11}{4}y \\
2\left(\frac{11}{4}y\right)^2 - 4\cdot\frac{11}{4}y \cdot y + 9y^2 &= 36 \\
\frac{242}{16}y^2 - 11y^2 + 9y^2 &= 36 \Rightarrow \frac{105}{8}y^2 = 36 \Rightarrow y^2 = \frac{96}{35}
\end{split}
$$

---

## Aufgabe 381: Extrema der Funktion
![[Pasted image 20250612064144.png]]
Funktion:
$$
f(x, y) = \sin(x + y) + \sin x + \sin y
$$

### Kritische Punkte:
$$
\frac{\partial f}{\partial x} = \cos(x + y) + \cos x, \quad
\frac{\partial f}{\partial y} = \cos(x + y) + \cos y
$$

Setze $\cos x = \cos y \Rightarrow x = y$:
$$
\begin{split}
\cos(2x) + \cos x &= 0 \Rightarrow x_0 \approx 1.06
\end{split}
$$

### Hesse-Matrix:
$$
\begin{split}
f_{xx} &= -\sin(x + y) - \sin x \\
f_{yy} &= -\sin(x + y) - \sin y \\
f_{xy} &= -\sin(x + y) \\
\det H &= f_{xx} f_{yy} - f_{xy}^2 = \sin^2(2x_0) + 2\sin(2x_0)\sin x_0 + \sin^2 x_0 > 0
\end{split}
$$

→ Lokales Maximum bei $x = y = x_0$

---

## Aufgabe 397: Inhomogene lineare DGL
![[Pasted image 20250612064207.png]]

- Gegeben: $x y' + y = x^2 + 3x + 2$
- Normieren: $y' + \frac{1}{x} y = x + 3 + \frac{2}{x}$
- Integrierender Faktor: $\mu(x) = e^{\int \frac{1}{x} dx} = x$
- Multipliziere: $\frac{d}{dx}(x y) = x^2 + 3x + 2$
- Integration:
$$
\begin{split}
x y &= \int (x^2 + 3x + 2)\,dx \\
&= \frac{1}{3}x^3 + \frac{3}{2}x^2 + 2x + C
\end{split}
$$

- Löse nach $y$:
$$
\begin{split}
y &= \frac{1}{x} \left( \frac{1}{3}x^3 + \frac{3}{2}x^2 + 2x + C \right) \\
&= \frac{1}{3}x^2 + \frac{3}{2}x + 2 + \frac{C}{x}
\end{split}
$$

**Lösung**:
$$
\boxed{y(x) = \frac{1}{3}x^2 + \frac{3}{2}x + 2 + \frac{C}{x}}
$$
