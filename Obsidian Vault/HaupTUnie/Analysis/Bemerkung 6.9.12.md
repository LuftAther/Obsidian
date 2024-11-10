
Betrachtet man die Abbildung $(r, t) \mapsto r (\cos t + i \sin t)$ von $[0, +\infty) \times [0, 2\pi)$, so erreicht man alle komplexen Werte $ w $ – einschließlich $ w = 0 $ – zu dem Preis, dass diese Abbildung nicht injektiv ist.

Gemäß Satz 6.9.10, (iii), kann dabei das Intervall $[0, 2\pi)$ durch ein beliebiges halboffenes Intervall der Länge $2\pi$ ersetzt werden, beispielsweise durch $(-\pi, \pi]$.

Offensichtlich ist die Abbildung $T : \mathbb{R}^+ \times [0, 2\pi) \to \mathbb{C} \setminus \{0\}$, als Zusammensetzung stetiger Funktionen, selbst stetig. Die Umkehrfunktion ist jedoch nicht stetig:

$$
\lim_{n \to \infty} \exp(i \cdot \frac{1}{n}) = 1
$$

aber

$$
\lim_{n \to \infty} T^{-1}\left(\exp\left(i \cdot \frac{1}{n}\right)\right) = \lim_{n \to \infty} \left(1, 2\pi - \frac{1}{n}\right) = (1, 2\pi) \neq (1, 0) = T^{-1}(1).
$$

Wählt man statt $[0, 2\pi)$ zum Beispiel das Intervall $[a, a + 2\pi)$, so treten entsprechende Probleme beim Winkel $a$ auf.
