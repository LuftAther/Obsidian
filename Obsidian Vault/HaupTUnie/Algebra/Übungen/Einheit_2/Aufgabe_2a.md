# Aufgabenstellung

(1.) Finden Sie eine unendliche Gruppe $\mathcal{G} = (G, *, 1, ^{-1})$ mit zwei Elementen $s, t$, sodass $\langle \{s\} \rangle$ und $\langle \{t\} \rangle$ endlich sind, aber $\langle \{s,t\} \rangle = G$ gilt. 
	**Hinweis**: Für $k \in \mathbb{Z}$ sei $s_k: \mathbb{Z} \to \mathbb{Z}$ durch $s_k(z) = k - z$ definiert. Berechnen Sie $s_0 \circ s_1$.

(2.) Zeigen Sie, dass es in der von Ihnen gefundenen Gruppe unendlich viele *2-stellige Termfunktionen* gibt. Geben Sie explizit mindestens **5 verschiedene** 2-stellige Termfunktionen an. 
	(Achtung! Die Terme $x * 1$ und $x$ sind verschieden, die induzierten Termfunktionen aber nicht!) Falls Ihnen dies zu einfach ist: Geben Sie unendlich viele (oder noch besser: alle) **einstelligen Termfunktionen** in Ihrer Gruppe an.

----
## Definitionen:

##### Gruppe:
Eine Paar $(G, *)$ mit
- $G$ $\dots$ Menge und 
- $*$ $\dots$  **zweistellige Verknüpfung** bezüglich $G$.  
Dadurch wird die Abbildung $*: G \times G \to G, \quad (a, b) \mapsto a * b$ 
beschrieben. Zudem Gelten die folgenden **Axiome** für die Verknüpfung
- **Assoziativität**: Für alle Gruppenelemente $a, b$ und $c$ gilt:  
  $(a * b) * c = a * (b * c).$
- Es gibt ein **neutrales Element** $e \in G$, mit dem für alle Gruppenelemente $a \in G$ gilt:  
   $a * e = e * a = a.$
- Zu jedem Gruppenelement $a \in G$ existiert ein **inverses Element** $a^{-1} \in G$ mit  
  $a * a^{-1} = a^{-1} * a = e.$
Eine Gruppe $(G, *)$ heißt **abelsch** oder **kommutativ**, wenn:
- **Kommutativität**: Für alle Gruppenelemente $a$ und $b$ gilt:  $a * b = b * a.$

##### Term (Definition 2.1.8.1):
![[Termfunktion.png]]

---
### 1) Aufgabe 

Nach dem Hinweis, betrachte:
- $s_k(z) := k - z$ .
- $t_{k}(z) := - k+z$
und die verknüpfung $\circ$ 
-  $s_k \circ s_\ell(z) = s_k(s_\ell(z)) \Leftrightarrow  k - ( \ell - z ) = (k - \ell) + z$
-  $t_k \circ t_\ell(z) = t_k(s_\ell(z)) \Leftrightarrow  -k + ( \ell+ z )$
Alleine bilden$\langle \{s\} \rangle$ und $\langle \{t\} \rangle$ mit $\circ$ keine (Unendliche)gruppe
##### Behauptung: 
$\langle \{s,t\} \rangle = G$
##### Beweis

- $s_k \circ t_k = \text{id}$ ist neutral :
	Sei $z\in \mathbb{Z}$ belibig dann gilt $s_k \circ t_k \circ (z) = s_{k} \circ (-k +z) = k - (k+z) = z$
- Inverse existieren ( $t_{k} = -s_{k}$)
	$s_k \circ (-t_k \circ (0)) = s_{k} \circ (k - 0) = k - (k + 0) = 0$
- 
- Assoziativität wegen $\circ$  
- Abgeschlossenheit: 
	Wir erzuegen die Gruppe ja 

**Beispiel**: Betrachte $\langle \{s_0\} \rangle$ und $\langle \{s_2\} \rangle$

Wir sehen:
- $s_0 \circ s_0 = s_0^2 = s_{0} = \text{id}$   ⇒ $\langle \{s_0\} \rangle = \{s_0, \text{id} \}$  
- $s_2 \circ s_2 = 2 -(2-0) =  s_2^2 = s_0$ ⇒ $\langle \{s_2\} \rangle = \{s_0, s_2\}$
Aber:
- $s_0 \circ s_2 = 0 - (2 - 0) = -2 = s_{2} =t_{-2}$  
- $s_2 \circ s_0 = 2-(0-0) = 2 = s_{-2}= t_{2}$
Daher: $\langle \{s_0, s_2\} \rangle = \mathcal{G}$

Setze:
- $s_k$ bel.: ⇒ $s_k = (t_2)^k$ (hängt vom Vorzeichen von $k$ ab)  
- $s_k$ bel.: ⇒ $s_k = s_0 \circ t_k$

⇒ Damit erzeugt $\{s_0, t_{0}\}$ ganz $\mathcal{G}$

---

## (2) Unendlich viele 2-stellige Termfunktionen

Betrachte eine Familie von Termen $(t_n)_{n \in \mathbb{N}} \in T$ in der Termalgebra vom Typ $(2, 0, 1)$
Definiere rekursiv Terme $t_n \in T$:
- $t_1 := \omega_{1}(x,y) = x \circ y \dots$ ein term fon Grad 1
- $t_{n+1} = \omega \circ \omega \circ \underbrace{\cdots}_{n-mal} \circ \omega (x,y) = x t_n$ (Term $n+1$-ter Ordnung)

Also:
- $v(t_n) = \{x, y\} \dots$ Menge der vorkommenden Variablen (rekursiv definiert)  
⇒ Damit bezeichnet $t_n(x, y)$ einen Term, in $\mathcal{G}$ und die von $\mathcal{G}$ induzierte (vgl. einsätzungshomomorphismus)Termfunktion ist:

$$t_{n+1}^\mathcal{G}(g_1, g_2) = g_1^n \circ t_{n}^{\mathcal{G}}(g_{1}, g_2)$$

Induktiv kann man mit der *Assoziativität* zeigen das $t^{\mathcal{G}}_{n}(g_{1}, g_{2}) = g_{1}^n \circ g_{2}$.

Wählen wir z. B. $g_1 = t_1$, womit $(g_1)^n = t_n^+$, dann erkennt man:

$$t_n \circ g_2 \neq t_m \circ g_2 \quad \text{für } n \neq m
$$

⇒ Also sind die Termfunktionen **alle verschieden**
⇒ Es gibt unendlich viele

### 5 Beispiele: 

Wir arbeiten in der Termalgebra vom Typ $(2, 0, 1)$ mit einer binären Verknüpfung $\omega$ (die der Verknüpfung $\circ$ entspricht).

Die Terme $t_n(x, y)$ sind rekursiv definiert durch:

- $t_1(x, y) := \omega(x, y) = x \circ y$
- $t_2(x, y) := \omega(x, \omega(x, y)) = x \circ (x \circ y)$
- $t_3(x, y) := \omega(x, t_2(x, y)) = x \circ (x \circ (x \circ y))$
- $t_4(x, y) := x \circ (x \circ (x \circ (x \circ y)))$
- $t_5(x, y) := x \circ t_4(x, y)$

Diese Terme definieren die Folgenden 2-stelligen Termfunktionen:

1. **$f_1(g_1, g_2) := g_1 * g_2$**
2. **$f_2(g_1, g_2) := g_1 * (g_1 * g_2) = g_1^2 * g_2$**
3. **$f_3(g_1, g_2) := g_1 * (g_1 * (g_1 * g_2)) = g_1^3 * g_2$**
4. **$f_4(g_1, g_2) := g_1^4 * g_2$**
5. **$f_5(g_1, g_2) := g_1^5 * g_2$**

**Bemerkung:**  
Diese Funktionen sind alle **unterschiedlich**, da die Anwendung von $g_1$ mehrfach erfolgt und $\mathcal{G}$ unendlich ist – also $g_1^n \neq g_1^m$ für $n \neq m$.

Damit gibt es unendlich viele solcher 2-stelligen Termfunktionen und jede Funktion hat die Form: $$f_n(g_1, g_2) := g_1^n * g_2$$