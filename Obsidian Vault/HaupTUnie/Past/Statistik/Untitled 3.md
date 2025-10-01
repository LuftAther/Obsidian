## Reflexivität von Hilberträumen mit Proposition 3.2.5

Sei $H$ ein Hilbertraum. Wir wollen zeigen, dass $H$ reflexiv ist, d.h. dass die kanonische Abbildung
$$
J : H \to H^{\prime\prime}, \quad x \mapsto (\varphi \mapsto \varphi(x))
$$
ein Isomorphismus ist.

Nach Proposition 3.2.5 ist die Abbildung
$$
\Phi: H \to H', \quad y \mapsto f_y := (x \mapsto (x, y))
$$
eine isometrische, konjugiert-lineare Bijektion.

Damit erhält man durch Dualisieren eine weitere konjugiert-lineare Bijektion
$$
\Phi': H'' \to H', \quad \Psi \mapsto \Phi'(\Psi), \quad \text{wobei } \Phi'(\Psi)(x) := \overline{\Psi(f_x)}.
$$

Setzt man nun $J: H \to H''$ wie oben, dann ergibt sich
$$
(\Phi' \circ J)(y)(x) = \overline{J(y)(f_x)} = \overline{f_x(y)} = \overline{(y, x)} = (x, y) = f_y(x).
$$

Also gilt:
$$
\Phi' \circ J = \Phi,
$$
und somit ist $J = (\Phi')^{-1} \circ \Phi$ eine isometrische, konjugiert-lineare Bijektion von $H$ auf $H''$.

Da $J$ zusätzlich linear ist, folgt, dass $H$ reflexiv ist.
