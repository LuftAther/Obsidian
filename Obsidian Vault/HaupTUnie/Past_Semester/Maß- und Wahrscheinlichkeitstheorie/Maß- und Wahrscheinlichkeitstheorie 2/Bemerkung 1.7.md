### Stochastische oder Fast-überall-Konvergenz legt den Grenzwert eindeutig fest bis auf Gleichheit fast überall:
Tatsächlich: Sei $f_n \xrightarrow{\text{stoch}} f$ und $f_n \xrightarrow{\text{stoch}} g$. Sei $A_1, A_2, \dots \in \mathcal{A}$ mit $A_n \uparrow \Omega$ und $\mu(A_n) < \infty$ für jedes $n \in \mathbb{N}$.
Dann gilt (wegen $d(f, g) \leq d(f, f_n) + d(g, f_n)$) für jedes $m \in \mathbb{N}$ und $\epsilon > 0$:
$$\mu(A_m \cap \{ d(f, g) > \epsilon \}) \leq \mu(A_m \cap \{ d(f, f_n) > \epsilon/2 \}) + \mu(A_m \cap \{ d(g, f_n) > \epsilon/2 \}) \xrightarrow{n \to \infty} 0$$
Also ist $\mu(\{ d(f, g) > 0 \}) = 0$.
