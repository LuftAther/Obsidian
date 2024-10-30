Die intuitivste Definition der Konvergenz einer Folge von Funktionen $(f_n)_{n > 1}$ gegen eine Funktion $f$, wobei $f, f_n: \Omega \to \mathbb{R}$, ist die punktweise Konvergenz: 
Für jedes $(\omega \in \Omega)$ konvergiert $f_n(\omega)$ für $n \to \infty$  zu $f(\omega)$. Da Mengen von Maß Null oft vernachlässigt werden kann, kommen wir zu der Definition der fast überall Konvergenz. In vielen Fällen konvergieren Folgen $(f_n)_{n > 1}$ jedoch im Großteil des Raums nahe an  $f$, aber nicht fast überall. Daher werden weitere Konvergenzbegriffe eingeführt, wie Konvergenz im Maß, in $\mathcal{L}^1$, $\mathcal{L}^p$, usw.

1. ==Konvergiert fast sicher:==
Sei $f, f_1, f_2, \dots$ eine Folge messbarer Funktionen von $(\Omega, \mathcal{A})$ nach $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$. 
Wir sagen, dass $f_n$ fast überall (a.s.) gegen $f$  konvergiert, falls eine Menge $N \in \mathcal{A}$ mit  $\mu(N) = 0$ existiert, so dass für jedes $\omega \in \Omega \setminus N$ gilt: $f_n(\omega) \to f(\omega) \quad \text{für } n \to \infty.$  Wir schreiben dann $f_n \xrightarrow{\text{a.s.}} f$ 

2. ==Konvergenz Im Maß:==
Wir sagen, dass $f_n$ im Maß (stochastisch) gegen $f$ konvergiert, und schreiben $f_n \xrightarrow{\text{stoch}} f$, wenn für jedes $A \in \mathcal{A}$ mit $\mu(A) < \infty$ und für jedes $\epsilon > 0$ gilt:  $\lim_{n \to \infty} \mu\left(\{ \omega \in A : |f_n(\omega) - f(\omega)| > \epsilon \} \right) = 0$.

3. ==Konvergenz in $\mathcal{L}¹$: ==
 Wir sagen, dass $f_n$ im Maß (stochastisch) gegen $f$ konvergiert, und schreiben $f_n \xrightarrow{\text{stoch}} f$, wenn für jedes $A \in \mathcal{A}$ mit $\mu(A) < \infty$ und für jedes $\epsilon > 0$ gilt:  $\lim_{n \to \infty} \mu\left(\{ \omega \in A : |f_n(\omega) - f(\omega)| > \epsilon \} \right) = 0.$ 

- Wenn darüber hinaus $f, f_1, f_2, \dots \in L^1(\mu)$, dann sagen wir, dass $f_n$ in $L^1(\mu)$ konvergiert (konvergiert in Mittel) gegen $f$, und schreiben $f_n \xrightarrow{L^1} f$, wenn $\|f_n - f\|_1 := \int |f_n - f| \, d\mu \to 0 \quad \text{für } n \to \infty$