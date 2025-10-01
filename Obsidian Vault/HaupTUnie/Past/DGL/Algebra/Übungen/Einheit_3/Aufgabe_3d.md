Sei $G$ eine Gruppe, $U \leq G$ eine Untergruppe. 
- Sei $G / U$ die Menge $\{xU : x \in G\}$der Linksnebenklassen, 
- und $U \backslash G$ die Menge  $\{Ux : x \in G\}$ der Rechtsnebenklassen.

**Achtung!** Hier ist nicht (leere) Differenzmenge $U \backslash G$ gemeint.
1. **Zeigen Sie an Hand eines Beispiels, dass die Abbildungsvorschrift** 
$$
f : U \backslash G \to G / U, \quad xU \mapsto Ux
$$
**im Allgemeinen nicht wohldefiniert ist.**

2. **Geben Sie eine Bijektion von** $U \backslash G$ **nach** $G / U$ **an.**  
   *(Wir setzen nicht voraus, dass $G$ endlich ist.)*
3. **Zeigen Sie: Wenn** $\lvert G / U \rvert = 2$ **gilt, dann ist** $U$ **Normalteiler von** $G$.

---
#### (1) Beispiel für eine nicht wohldefinierte Abbildung

Die Abbildung: $f : U \backslash G \to G / U, \quad Ux \mapsto xU$
### Beispiel

Betrachte die Gruppe $G = S_3$ (Symmetrische Gruppe auf drei Elementen)
- Die Gruppe $S_3$ enthält **alle Permutationen** von drei Elementen. Sie hat $|S_3| = 6$ Elemente.
Und betrachte die  Untergruppe $U = \langle (12) \rangle = \{ e, (12) \} \dots$. eine Zyklische Gruppe von Ordung $2$

- Wähle die Permutationen $x = (13)$ und $y = (13)(12) = (132)$.  
- Berechne die Rechtsnebenklassen:
	- $Ux = \{(13), (13)(12)\} = \{(13), (132)\}$
	- $Uy = \{(132), (13)\}$

Daraus folgt: $Ux = Uy$

- Berechne nun die Linksnebenklassen:
	- $xU = \{(13), (123)\},$ 
	- $yU = \{(132), (13)\}$

Daraus folgt: $xU \neq yU$


Die Abbildung $f : Ux \mapsto xU$ ist daher **nicht wohldefiniert**, weil zwei verschiedene Rechtsnebenklassen $Ux$ und $Uy$ auf verschiedene Linksnebenklassen $xU$ und $yU$ abgebildet werden.

---
#### (2) Gebe eine Bijektion $\phi$ : $U  \setminus G \to G /U$
- **Behauptung:** die Abbildung: $\phi: U \backslash G \to G / U, \quad \phi(Ux) = x^{-1}U$ ist bijektiv
- **Beweis**

1. Die Definierte Abbildung ist wirklich eine Abbildung und Wohldefiniert:

Falls $Ux = Uy$, dann existiert ein $u \in U$, sodass $y = ux$.  
Also:
$$
\phi(Uy) = (ux)^{-1}U = x^{-1}u^{-1}U = x^{-1}U = \phi(Ux)
$$

2. **Injektivität:**  

Angenommen $\phi(Ux) = \phi(Uy)$.  
Dann gilt:
$$
x^{-1}U = y^{-1}U \implies y^{-1}x \in U \implies Ux = Uy
$$

3. **Surjektivität:**  

Sei $xU \in G/U$.  
Wähle $g = x^{-1}$. Dann gilt:
$$
\phi(Ux^{-1}) = x^{-1}U = gU
$$
Damit ist $\phi$ surjektiv.

---

#### (3)  Zu Zeigen: Wenn$\lvert G / U \rvert = 2$ **gilt, dann ist** $U$ Normalteiler von $G$

Wenn $|G / U| = 2$, dann ist $U$ ein Normalteiler von $G$.  
Das bedeutet, dass $G$ genau **zwei Linksnebenklassen** besitzt:

$$
G / U = \{U, gU\} \quad \text{für ein } g \in G \setminus U
$$

Ebenso gibt es genau **zwei Rechtsnebenklassen**:

$$
U \backslash G = \{U, Ug\}
$$

---

### Beweis

Falls $U$ kein Normalteiler ist, gibt es ein $g \in G$ mit
$$
gUg^{-1} \neq U
$$
Nun betrachten wir die Nebenklassen:
$$
G/U = \{U, gU\}, \quad U \backslash G = \{U, Ug\}
$$

Wenn $gUg^{-1} \neq U$, dann müsste $gUg^{-1}$ eine neue Nebenklasse bilden.  
Da es aber nur **zwei Nebenklassen** gibt, folgt:

$$
gUg^{-1} = U
$$

Also ist $U$ unter Konjugation invariant, d. h.:

$$
gUg^{-1} \subseteq U \quad \text{für alle } g \in G
$$

Damit ist $U \leq G$.


1. Die Abbildung $f: U \backslash G \to G / U, \, Ux \mapsto xU$ ist **nicht wohldefiniert**.  
2. Eine wohldefinierte Bijektion $\phi: U \backslash G \to G / U$ ist gegeben durch $\phi(Ux) = x^{-1}U$.  
3. Wenn $|G/U| = 2$, dann ist $U$ ein Normalteiler von $G$.  

