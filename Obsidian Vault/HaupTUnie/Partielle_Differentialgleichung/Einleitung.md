
TARGET DECK: Partielle_Differentialgleichung
## 1.1 Was ist eine partielle Differentialgleichung?

ei einer ==Partielle Differentialgleichung== treten **partielle Ableitungen** auf. Wir schreiben partielle Ableitungen einer Funktion $u: \Omega \subset \mathbb{R}^n \to \mathbb{R}$ abgekürzt als $$u_{x_{i}}=\frac{\partial u}{\partial x_{i}},\quad u_{x_{i}xj}= \frac{\partial^2u}{\partial x_{i}\partial x_{j}}, \quad etc,$$
Eine partielle Differentialgleichung hat damit die Struktur $$F(x_{1}, \dots, x_{n},u,u_{x_{1}},\dots u_{x_{n}},u_{x_{1}x_{1}},\dots, u_{x_{n}x_{n}},\dots)= 0$$
In dem wir Multindizes verwenden können wir diese Gleichung kompakter schrieben. Dazu definieren wir:
einen **Multiindex** $\alpha = (\alpha_1,\dots,\alpha_n) \in \mathbb{N}_0^n$ und den **Grad** von $\alpha$: $|\alpha| = \alpha_1 + \cdots + \alpha_n$.  Weiters setzen wir
$$
D^\alpha u = \frac{\partial^{|\alpha|} u}{\partial x_1^{\alpha_1} \cdots \partial x_n^{\alpha_n}}, 
\qquad D^k u = \{D^\alpha u : |\alpha| = k\}.\tag{1.0}
$$
Dabei bezeichnen wir die Größe $Du = (u_{x_1}, \dots, u_{x_n})^T$ als den **Gradient** von $u$, 
$D^2 u$ ist die **Hesse-Matrix** von $u$. Die Gelichung (1.0) können wir schreiben als
$$
F(x, u(x), Du(x), \dots, D^k u(x)) = 0, 
\qquad x \in \Omega. \tag{1.1}
$$

Enthält die Gleichung partielle Ableitungen bis zur Ordnung $k$, dann nennen wir sie eine partielle Differentialgleichung der Ordnung $k$. 
Wir nennen eine Funktion $u : \Omega \to \mathbb{R}$ eine ==Lösung== von (1.1),  wenn $u$ $k$-mal differenzierbar ist und (1.2) für alle $x \in \Omega$ löst.


---
## Flashcards

---

- Definition 1.1.0 (a) Partielle Ableitungen #flashcard 
Wir schreiben partielle  $u: \Omega \subset \mathbb{R}^n \to \mathbb{R}$ abgekürzt als $$u_{x_{i}}=\frac{\partial u}{\partial x_{i}},\quad u_{x_{i}xj}= \frac{\partial^2u}{\partial x_{i}\partial x_{j}}, \quad etc,$$
Eine partielle Differentialgleichung hat damit die Struktur $$F(x_{1}, \dots, x_{n},u,u_{x_{1}},\dots u_{x_{n}},u_{x_{1}x_{1}},\dots, u_{x_{n}x_{n}},\dots)= 0$$
- Definition 1.1.0 (b) Multindizes #flashcard 
Multiindex$\alpha = (\alpha_1,\dots,\alpha_n) \in \mathbb{N}_0^n$ 
<!--ID: 1759512404375-->

- Definition 1.1.0 (c) Grad #flashcard 
Grad von $\alpha$: $|\alpha| = \alpha_1 + \cdots + \alpha_n$.  
<!--ID: 1759512404402-->

- Definition 1.1.0 (d) Gradient  #flashcard 
$$
D^\alpha u = \frac{\partial^{|\alpha|} u}{\partial x_1^{\alpha_1} \cdots \partial x_n^{\alpha_n}}, 
\qquad D^k u = \{D^\alpha u : |\alpha| = k\}
$$
Dabei bezeichnen wir die Größe $Du = (u_{x_1}, \dots, u_{x_n})^T$ als den **Gradient** von $u$, 
<!--ID: 1759512424500-->


- Definition 1.1.0 (e) Hesse-Matrix #flashcard 
$D^2 u$ ist die **Hesse-Matrix** von $u$. 
<!--ID: 1759512404409-->

- Definition 1.1.0 (f) Ordnung einer PDE #flashcard 
Enthält 
$$
F(x, u(x), Du(x), \dots, D^k u(x)) = 0, 
\qquad x \in \Omega
$$ partielle Ableitungen bis zur Ordnung $k$, dann nennen wir sie eine partielle Differentialgleichung der Ordnung $k$. 
<!--ID: 1759512404416-->

- Definition 1.1.0 (g) Lösung #flashcard 
Wir nennen eine Funktion $u : \Omega \to \mathbb{R}$ eine ==Lösung== von ,  wenn $u$ $k$-mal differenzierbar ist und $$
F(x, u(x), Du(x), \dots, D^k u(x)) = 0, 
\qquad x \in \Omega
$$ für alle $x \in \Omega$ löst.
<!--ID: 1759512436500-->

---

### Definition 1.1.1 (a) Linear PDE #flashcard 

Eine Partielle Differentialgleichung  der Formßt $F(x, u(x), Du(x), \dots, D^k u(x)) = 0, \qquad x \in \Omega$. heißt ==linear== wenn sie die folgende Form besitzt:
$$
\sum_{|\alpha|\leq k} c_\alpha(x) D^\alpha u(x) = f(x),
$$
wobei $c_\alpha$ und $f$ gegebene Funktionen sind. Falls $f=0$, so heißt die Differentialgleichung ==homogen==, andernfalls ==inhomogen==.  
<!--ID: 1759512873848-->


### Definition 1.1.1 (b) Semilinear PDE #flashcard 

Die Differentialgleichung $F(x, u(x), Du(x), \dots, D^k u(x)) = 0, \qquad x \in \Omega$. heißt ==semilinear==, wenn sie die Gestalt
$$
\sum_{|\alpha|=k} c_\alpha(x) D^\alpha u(x) + G(x,u(x),Du(x),\dots,D^{k-1}u(x)) = 0
$$
besitzt. Mit anderen Worten: Die Gleichung ist **linear bezüglich den Termen mit den höchsten partiellen Ableitungen, aber u.U. nichtlinear in allen anderen Termen**.  
<!--ID: 1759512873864-->



### Definition 1.1.1 (c)  Quasilineare PDE #flashcard 

Die Differentialgleichung $F(x, u(x), Du(x), \dots, D^k u(x)) = 0, \qquad x \in \Omega$. heißt ==quasilinear==, wenn sie die Form
$$
\sum_{|\alpha|=k} c_\alpha(x,u(x),Du(x),\dots,D^{k-1}u(x)) D^\alpha u(x) 
+ G(x,u(x),Du(x),\dots,D^{k-1}u(x)) = 0
$$
besitzt.  
<!--ID: 1759512831540-->

### Definition 1.1.1 (d) Voll nichtlineare PDE #flashcard 

Die Differentialgleichung $F(x, u(x), Du(x), \dots, D^k u(x)) = 0, \qquad x \in \Omega$. heißt ==voll nichtlinear==, wenn sie nichtlinear von den höchsten partiellen Ableitungen abhängt.
<!--ID: 1759509792651-->

Wichtige Beiepiele von PDEs sind dabei 

- Poissopn Gleichung #flashcard 
$$
  \Delta u = \sum_{i=1}^n \frac{\partial^2 u}{\partial x_i^2} = f(x);
  $$
- Wärmeleitungsgleichung #flashcard 
$$
  u_t - \Delta u = f(x);
$$
- Wellengleichung #flashcard 
$$
  u_{tt} - \Delta u = f(x).
$$
<!--ID: 1759514296852-->


Wichtige Fragestellungen sind bei PDEs 
#### Existenz und Eindeutigkeit einer Lösung

- PDEs dienen oft als Modelle für Natur- oder Sozialwissenschaften.
- **Keine Lösung** → Hinweis auf Probleme im Modell.
- **Eindeutigkeit** verlangt zusätzliche Bedingungen (Anfangs-/Randbedingungen, Verhalten im Unendlichen).
- Wichtige Eigenschaft: Die Lösung sollte **stetig von den Daten abhängen**, d.h. kleine Änderungen der Daten führen nur zu kleinen Änderungen der Lösung.
#### Schwache Lösungen und Regularität

- Nicht immer sind klassisch differenzierbare Lösungen vorhanden.
- Beispiel: $u_{xx} = f(x)$ mit unstetigem $f$ → Lösung $u$ evtl. nicht zweimal stetig differenzierbar.
- Stattdessen betrachtet man **schwache Lösungen**:
    - $u$ besitzt schwächere (integrable) Ableitugen.
    - Oft sind PDEs so formuliert, dass auch nicht klassisch differenzierbare Lösungen möglich sind.
- Ziel: Nachweisen, dass schwache Lösungen eine gewisse **Regularität** besitzen.
    
####  Qualitatives Lösungsverhalten

- Exakte Lösungen sind selten verfügbar.
- Stattdessen untersucht man qualitative Eigenschaften:
    - Verhalten im **Unendlichen** (bei unbeschränktem Gebiet).
    - Verhalten für **große Zeiten** (bei zeitabhängigen PDEs).
- Diese Informationen sind entscheidend für die **numerische Mathematik**:
    - Erlauben, numerische Verfahren zu überprüfen.
    - Sicherstellen, dass approximierte Lösungen zuverlässig sind.

---
## 1.2 Einige Definitionen und Resultate aus der Analysis

Wir betrachten Funktionen und Funktionenräume sei hirfür $\Omega \subset \mathbb{R}^n$ eine Offene Menge und $u: \Omega \to \mathbb{R}$ eine **zweimal stetig differentierbare** Funktion (d.h.\ $u \in C^2(\Omega)$) und  $v = (v_1, \dots, v_n)^T : \Omega \to \mathbb{R}^n$ eine vektorwertige stetig differenzierbare Funktion (d.h. $v \in C^1(\Omega;\mathbb{R}^n)$).
Dann bezeichnen wir

- Laplace-Operator #flashcard 
$$\Delta u = \sum_{i=1}^n \frac{\partial^2 u}{\partial x_i^2}$$
- Divergenz #flashcard 
$$\mathrm{div}\, v = \sum_{i=1}^n \frac{\partial v_i}{\partial x_i}$$
<!--ID: 1759514296875-->


- $C^k(\overline{\Omega})$ #flashcard 
Für beschränkte Mengen $\Omega$ ist $C^k(\overline{\Omega})$ der Raum aller $k$-mal stetig differenzierbaren Funktionen auf $\overline{\Omega}$. 
<!--ID: 1759514296882-->


Die Norm ist definiert durch
$$
\| f \|_{C^k(\overline{\Omega})} 
= \sum_{|\alpha| \leq k} \sup_{x \in \Omega} |D^\alpha f(x)|.
$$
Damit ist $C^k(\overline{\Omega})$ ein **Banachraum**.

-  Der Raum $C^\infty(\Omega)$ #flashcard 
$$
C^\infty(\Omega) = \bigcap_{k=0}^\infty C^k(\Omega).
$$
Dieser Raum ist **Kein Banachraum**
<!--ID: 1759514479724-->


- Träger einer Funktion #flashcard 
Der Träger (engl.\ support) einer Funktion $f$ ist definiert durch
$$
\mathrm{supp}(f) = \{ x \in \Omega : f(x) \neq 0 \}.
$$
<!--ID: 1759514543547-->


- $C_0^k(\Omega)$ #flashcard 
$$
C_0^k(\Omega) 
= \{ f \in C^k(\Omega) : \mathrm{supp}(f) \text{ kompakt in } \Omega \}, 
\qquad k \in \mathbb{N}_0 \cup \{\infty\}.
$$
<!--ID: 1759514507076-->

Weiters betrachten wir Räume von Lebesgue-integrierbaren Funktionen. Eine Definition hirfür is
- Lebesgue-Räume (Nicht ganz Korrekt)  #flashcard 
$$
L^p(\Omega) = \{ f : \Omega \to \mathbb{R} \ \text{messbar} : \|f\|_{L^p(\Omega)} < \infty \},
$$
wobei $1 \leq p < \infty$, und
$$
\|f\|_{L^p(\Omega)} = \left( \int_\Omega |f(x)|^p \, dx \right)^{1/p}
$$
die Norm von $L^p(\Omega)$ ist.
<!--ID: 1759515071150-->


Diese Definition ist nicht ganz korrekt, da sie außer Acht lässt, dass Funktionen, die bis auf eine Nullmenge übereinstimmen, miteinander identifiziert werden. 
Eine präzisere, aber abstraktere Definition ist wie folgt: 
Der Raum $L^p(\Omega)$ ist definiert durch die Vervollständigung des Raums $C_0^\infty(\Omega)$ bezüglich der Norm $\|\cdot\|_{L^p(\Omega)}$.

- Lebesgue-Räume (Abstrakt .. Korrekt ?) #flashcard 
Für $p = \infty$ definieren wir
$$
\|f\|_{L^\infty(\Omega)} = \mathrm{ess}\,\sup_{x \in \Omega} |f(x)| = \inf\{ K \geq 0 : |f(x)| \leq K \ \text{für fast alle } x \in \Omega\},
$$
und führen entsprechend den Raum $L^\infty(\Omega)$ aller (Äquivalenzklassen von) messbaren Funktionen $f$ mit $\|f\|_{L^\infty(\Omega)} < \infty$ ein. 
<!--ID: 1759515071166-->


Der Raum $L^p(\Omega)$ ist für alle $1 \leq p \leq \infty$ ein Banachraum. 
Falls $p=2$, so ist $L^2(\Omega)$ mit dem Skalarprodukt
$$
(f,g)_{L^2} = \int_\Omega f(x) g(x) \, dx
$$
ein Hilbertraum.

Für den Satz von Gauß in $\mathbb{R}^n$ betrachten wir $\Omega \subset \mathbb{R}^n$ eine offene und beschränkte Menge und $k \in \mathbb{N}_0$. Weiters bezeichnen wir 


- $B_r(x)$ #flashcard 
$x \in \mathbb{R}^n$ und $r > 0$ die (n-dimensionale) Kugel um $x$ mit Radius $r$,
$$
B_r(x) = \{ y \in \mathbb{R}^n : |y - x| < r \}.
$$
<!--ID: 1759515095724-->


### Definition 1.2  $\partial \Omega \in C^k$ #flashcard 

Wir sagen, dass $\partial \Omega \in C^k$ ist, 
wenn für alle $x^* \in \partial \Omega$ ein $r > 0$ und eine $k$-mal stetig differenzierbare Funktion $g$ existieren, 
so dass – bis auf eventuelle Umbenennung der Variablen – gilt:
$$
\Omega \cap B_r(x^*) = \{ x = (x_1,\dots,x_n) \in B_r(x^*) : x_n < g(x_1,\dots,x_{n-1}) \}.
$$
<!--ID: 1759515071174-->

Mit anderen Worten: Der Rand $\partial \Omega$ ist von der Klasse $C^k$, wenn er lokal durch eine $C^k$-Funktion dargestellt werden kann.  

### Definition 1.3  (äußere) Normalableitung #flashcard 

Seien $\partial \Omega \in C^1$ mit (äußerem) Normaleneinheitsvektor $v$ und  $f \in C^1(\overline{\Omega})$. Dann nennen wir
$$
\frac{\partial f}{\partial \nu}(x) = \nabla f(x) \cdot v(x), 
\qquad x \in \partial \Omega,
$$
die (äußere) Normalableitung von $f$ an $x$. 
<!--ID: 1759515307798-->

Sie ist stetig auf $\partial \Omega$.

### Theorem 1.5 (Gauß) Aussage #flashcard 

Sei $\Omega \subset \mathbb{R}^n$ eine offene und beschränkte Menge mit $\partial \Omega \in C^1$ und äußerem 
Normaleneinheitsvektor $v$, definiert auf $\partial \Omega$. Ferner sei $F \in C^1(\Omega; \mathbb{R}^n) \cap C^0(\overline{\Omega}; \mathbb{R}^n)$ 
eine vektorwertige Funktion, so dass $\mathrm{div} F$ integrierbar auf $\Omega$ ist. Dann gilt:
$$
\int_{\Omega} \mathrm{div} F \, dx 
= \int_{\partial \Omega} F \cdot v \, ds.
$$
<!--ID: 1759515437173-->

### Theorem 1.7 (a) Cauchy-Schwarz Ungleichung #flashcard 

Seien $f, g \in L^2(\Omega)$. Dann gilt :
$$
(f,g)_{L^2} = \int_\Omega f g \, dx 
\leq \sqrt{\int_\Omega f^2 dx} \, \sqrt{\int_\Omega g^2 dx} 
= \|f\|_{L^2(\Omega)} \|g\|_{L^2(\Omega)}.
$$
<!--ID: 1759515618648-->


### Theorem 1.7 (b) Hölder-Ungleichung #flashcard 

Sind $1 < p, q < \infty$ mit $\tfrac{1}{p} + \tfrac{1}{q} = 1$ und $f$, $g \in L^q(\Omega)$ gegeben, so gilt die:
$$
\int_\Omega f g \, dx \leq \|f\|_{L^p(\Omega)} \, \|g\|_{L^q(\Omega)}.
$$
<!--ID: 1759515618671-->

### Lemma 1.8 Integrierbarkeit  #flashcard 

Sei $f : \Omega \subset \mathbb{R}^n \to \mathbb{R}$ eine integrierbare Funktion. 
Gilt
$$
\int_\omega f(x) \, dx = 0 
\qquad \text{für alle offenen Mengen } \omega \subset \Omega,
$$
so folgt $f(x) = 0$ für fast alle $x \in \Omega$.
<!--ID: 1759515764374-->



### Lemma 1.9 Integrierbarkeit  (lokal) #flashcard 

Sei $\Omega \subset \mathbb{R}^n$ eine offene Menge, 
$f : \Omega \to \mathbb{R}$ lokal integrierbar (d.h.\ auf jeder kompakten Menge integrierbar), 
und es gelte
$$
\int_\Omega f \varphi \, dx = 0 
\qquad \text{für alle } \varphi \in C_0^\infty(\Omega),
$$
so folgt $f(x) = 0$ für fast alle $x \in \Omega$.
<!--ID: 1759515764389-->
