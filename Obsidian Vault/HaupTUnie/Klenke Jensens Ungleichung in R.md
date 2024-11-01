Sei $G \subset \mathbb{R}^n $ konvex, und seien $X_1, \dots, X_n$ integrierbare reelle Zufallsvariablen mit $P[(X_1, \dots, X_n) \in G] = 1$. Sei ferner $\varphi : G \to \mathbb{R}$ konvex. Dann gilt $\mathbb{E}[\varphi(X_1, \dots, X_n)^-] < \infty$ und
$$
\mathbb{E}[\varphi(X_1, \dots, X_n)] \geq \varphi(\mathbb{E}[X_1], \dots, \mathbb{E}[X_n]).
$$

### Beweis
Wir betrachten zunächst den Fall, dass $G$ offen ist. Die Argumentation verläuft hier ähnlich wie beim Beweis von Satz 7.9.

Sei $g \in L(\varphi)$ mit $g(\mathbb{E}[X_1], \dots, \mathbb{E}[X_n]) = \varphi(\mathbb{E}[X_1], \dots, \mathbb{E}[X_n])$. Da $g \leq \varphi$ linear ist, folgt
$$
\mathbb{E}[\varphi(X_1, \dots, X_n)] \geq \mathbb{E}[g(X_1, \dots, X_n)] = g(\mathbb{E}[X_1], \dots, \mathbb{E}[X_n]).
$$

Die Integrierbarkeit von $\varphi(X_1, \dots, X_n)^-$ folgt völlig analog wie im eindimensionalen Fall.

Nun betrachten wir den allgemeinen Fall, d.h., wenn $G$ nicht notwendigerweise offen ist. Das Problem, wenn $(\mathbb{E}[X_1], \dots, \mathbb{E}[X_n]) \in \partial G$ liegt, ist etwas komplizierter als im eindimensionalen Fall, da $\partial G$ flache Abschnitte haben kann, die jedoch ebenfalls notwendigerweise konvex sind. Es ist also nicht möglich, daraus zu schließen, dass $(X_1, \dots, X_n)$ fast sicher gleich dem Erwartungswert ist.

Wir skizzieren das Argument nur: Zunächst kann man nur folgern, dass $(X_1, \dots, X_n)$ fast sicher in einem solchen flachen Abschnitt liegt. Dieser Abschnitt ist dann notwendigerweise von einer Dimension kleiner als $n$ (oder Null, falls der Abschnitt ein einzelner Punkt ist). Jetzt muss man $\varphi$ auf den flachen Abschnitt einschränken und iterativ in der Dimension herunterarbeiten.
