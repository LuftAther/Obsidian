## Stetigkeit der skalaren Multiplikation auf dem Faktorraum $X/N$
Führen Sie den Teil des Beweises von Proposition 2.4.6, der in der Vorlesung nicht gemacht wurde, aus.  
Zeigen Sie also, dass die skalare Multiplikation als Abbildung von  
$$
\mathbb{C} \times (X / N) \rightarrow X / N
$$
stetig ist.

---
Gegeben sei ein topologischer Vektorraum $X$ und ein abgeschlossener Untervektorraum $N \subset X$. Wir betrachten den **Faktorraum** $X/N$ mit der **finalen Topologie**, d.h. der **gröbsten Topologie**, sodass die **Quotientenabbildung**
$$
\pi_N: X \rightarrow X/N, \quad x \mapsto x * N
$$
stetig ist.  
Nach **Proposition 2.4.6**
![[Screenshot 2025-03-27 at 20-45-42 fana_maerz_2025.pdf.png]]
wissen wir: 

> Die Projektion $\pi_N$ ist offen, und $X/N$ ist mit dieser Topologie ein topologischer Vektorraum.

## Zu zeigen

Die Abbildung
$$
\cdot: \mathbb{C} \times (X/N) \rightarrow X/N, \quad (s, [x]) \mapsto [sx]
$$
ist **stetig**.

---
- Sei also $(s, [x]) \in \mathbb{C} \times (X/N)$ gegeben und $P \subseteq X/N$ eine offene Menge mit
$$
[sx] \in P
$$
Da $\pi_N$ offen ist, gibt es eine offene Menge $U \subset X$, sodass
$$
\pi_N(U) \subseteq P \quad \text{und} \quad sx \in U
$$
- Da die skalare Multiplikation $\mathbb{C} \times X \to X$, $(s,x) \mapsto sx$, **stetig** ist, existieren Umgebungen:
	- $V_s \in \mathcal{U}_{\mathbb{C}}(s)$
	- $V_x \in \mathcal{U}_X(x)$
sodass: $V_s \cdot V_x \subseteq U$

- Wegen der Offenheit von $\pi_N$ ist:
$$
\pi_N(V_s \cdot V_x) \subseteq \pi_N(U) \subseteq P
$$
Das heißt:
$$
\{ (s', [x']) \in \mathbb{C} \times X/N \mid s' \in V_s, x' \in V_x \} \subseteq \cdot^{-1}(P)
$$
> $.^{-1}(P) \dots$ **Urbild** der Menge $P$ unter der Abbildung $\cdot$⋅, also der skalaren Multiplikation.
> $\cdot^{−1}(P):=\{(s,[x])∈C×(X/N)∣s⋅[x]∈P\}$

- Da $V_s$ und $\pi_N(V_x)$ offen sind und das kartesische Produkt offener Mengen offen ist, folgt:
$$
\cdot^{-1}(P) \text{ enthält eine offene Umgebung von } (s, [x]) \Rightarrow \cdot \text{ ist stetig}
$$

- D.h:
	Die skalare Multiplikation auf dem Faktoraum $X/N$ ist stetig, weil:
	1. Die Multiplikation auf $X$ stetig ist,
	2. Die Projektion $\pi_N$ stetig und offen ist,
	3. Die finale Topologie genau so gewählt wurde, dass $\pi_N$ stetig ist und Offenheit bewahrt.