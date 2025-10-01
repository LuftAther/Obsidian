## Aufgabe 1: Berechnen Sie das Integral  
$$
\int (x - 1)^2 e^x \, dx
$$

#### Lösung:

Zunächst wird der Binom ausmultipliziert:  
$$
(x - 1)^2 = x^2 - 2x + 1
$$

Zerlegen des Integrals:  
$$
\int (x - 1)^2 e^x \, dx = \int (x^2 - 2x + 1) e^x \, dx  
= \int x^2 e^x \, dx - 2 \int x e^x \, dx + \int e^x \, dx
$$

Bekannte Integrale:  
$$
\begin{split}
\int e^x \, dx &= e^x + C\\
\int x e^x \, dx &= (x - 1)e^x + C\\
\int x^2 e^x \, dx &= (x^2 - 2x + 2)e^x + C
\end{split}
$$

Zusammensetzen:
$$
\begin{split}
\int (x - 1)^2 e^x \, dx &= (x^2 - 2x + 2)e^x - 2(x - 1)e^x + e^x \\
&= \left[x^2 - 2x + 2 - 2x + 2 + 1\right] e^x \\
&= (x^2 - 4x + 5)e^x + C
\end{split}
$$

**Ergebnis:**  
$$
\boxed{ \int (x - 1)^2 e^x \, dx = (x^2 - 4x + 5) e^x + C }
$$

---

## Aufgabe 2: Untersuchen Sie das uneigentliche Integral auf Konvergenz  
$$
\int_1^\infty \frac{\sin^2(x)}{x^2} \, dx
$$

#### Lösung:

Da $|\sin(x)| \leq 1$ für alle $x$ gilt, folgt:
$$
0 \leq \frac{\sin^2(x)}{x^2} \leq \frac{1}{x^2}
$$

Vergleich mit der Majorante:
$$
\int_1^\infty \frac{1}{x^2} \, dx = \left[ -\frac{1}{x} \right]_1^\infty = 1
$$

Die Majorante ist konvergent ⇒ **Majorantenkriterium** anwendbar.

**Ergebnis:**  
$$
\boxed{ \int_1^\infty \frac{\sin^2(x)}{x^2} \, dx \text{ konvergiert} }
$$
---

## Aufgabe 3: Gradient – Steilster Anstieg  
Gegeben sei die Höhenfunktion:  
$$
f(x, y) = \sin(xy)
$$  
und der Punkt $(\sqrt{\pi}, -\sqrt{\pi})$.

#### Gesucht:
- Richtung, in die es am steilsten bergauf geht.
- Wie steil es dort ist.

#### Lösung:

Gradient berechnen:  
$$
\nabla f(x, y) = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right)
= \left( y \cos(xy), x \cos(xy) \right)
$$

Einsetzen von $x = \sqrt{\pi}$, $y = -\sqrt{\pi}$:  
$$
xy = -\pi \quad \Rightarrow \quad \cos(xy) = \cos(-\pi) = -1
$$

Also:  
$$
\nabla f(\sqrt{\pi}, -\sqrt{\pi}) = \left( -\sqrt{\pi} \cdot (-1), \ \sqrt{\pi} \cdot (-1) \right)
= (\sqrt{\pi}, -\sqrt{\pi})
$$

**Richtung des steilsten Anstiegs:**  
$$
\boxed{(\sqrt{\pi}, -\sqrt{\pi})}
$$

**Steigung (Betrag des Gradienten):**  
$$
\begin{split}
\left\| \nabla f(\sqrt{\pi}, -\sqrt{\pi}) \right\| 
&= \sqrt{ (\sqrt{\pi})^2 + (-\sqrt{\pi})^2 } \\
&= \sqrt{ \pi + \pi } = \sqrt{2\pi}
\end{split}
$$

**Ergebnis:**  
- Richtung: $\boxed{(\sqrt{\pi}, -\sqrt{\pi})}$  
- Steigung: $\boxed{\sqrt{2\pi}}$
