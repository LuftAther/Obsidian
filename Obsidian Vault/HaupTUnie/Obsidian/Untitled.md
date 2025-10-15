Gegeben ist die Funktion:

$$
f(x, y) = 
\begin{cases}
\frac{x^3 - y^3}{\sqrt{x^2 + y^2}} \cdot \sin\left( \frac{1}{x^2 + y^2} \right), & (x, y) \ne (0, 0) \\
0, & (x, y) = (0, 0)
\end{cases}
$$

Wir sollen zeigen, dass $f$ **stetig im Punkt $(0,0)$** ist.

---

## Ziel

Zeige:
$$
\lim_{(x,y) \to (0,0)} f(x,y) = f(0,0) = 0
$$

---

## Umformung in Polarkoordinaten

Setze:
$$
x = r \cos\varphi,\quad y = r \sin\varphi \quad \Rightarrow \quad x^2 + y^2 = r^2
$$

Dann ergibt sich:

$$
\begin{aligned}
f(x,y) 
&= \frac{x^3 - y^3}{\sqrt{x^2 + y^2}} \cdot \sin\left( \frac{1}{x^2 + y^2} \right) \\
&= \frac{(r \cos\varphi)^3 - (r \sin\varphi)^3}{r} \cdot \sin\left( \frac{1}{r^2} \right) \\
&= \frac{r^3(\cos^3 \varphi - \sin^3 \varphi)}{r} \cdot \sin\left( \frac{1}{r^2} \right) \\
&= r^2 (\cos^3 \varphi - \sin^3 \varphi) \cdot \sin\left( \frac{1}{r^2} \right)
\end{aligned}
$$

---

## Abschätzung

Da $|\sin(1/r^2)| \leq 1$, gilt:

$$
|f(x,y)| \leq r^2 \cdot |\cos^3 \varphi - \sin^3 \varphi|
$$

und da $|\cos^3 \varphi - \sin^3 \varphi| \leq 2$, folgt:

$$
|f(x,y)| \leq 2r^2 \longrightarrow 0 \quad \text{für } r \to 0
$$

---

## Fazit

$$
\lim_{(x,y)\to(0,0)} f(x,y) = 0 = f(0,0)
$$

Die Funktion $f$ ist somit **stetig in $(0,0)$**.
