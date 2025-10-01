## Aufgabenstellung:
==(1)== Wenn $\mathcal{P} = (P, \leq)$ eine Partielle Ordung ist, in der jede Teilmenge $A \subseteq P$ ein *infimum* hat,
dann hat auch jede Teilmenge $B \subseteq P$ ein *supremum*. ==(2)== Erklären Sie auch, warum die natürlichen Zahlen mit der üblichen Ordnung *kein*Gegenbeispiel bilden.

### Definitionen:

- Eine binäre Realtaion $p$ auf einer Mänge $A$ definiert eine **Prtielle Ordung** wenn sie 
	- Reflexif,
	- anitsymetrisch  und
	- Transitiv ist
- Wir betrachten hir $\mathcal{P} :=(P, \leq)$ 

- **Infimum** : $p_0$ Infimum von A, wenn $p_{0}$ die größte untere Schranke von $A$ ist; wir schreiben dann $p_0$ = $inf A$ (Wenn $A$ ein kleinstes Element m hat, dann gilt $m = inf A$. Wenn $A$ kein kleinstes Element hat, dann kann es dennoch ein Infimum geben; dieses liegt dann aber nicht in $A$.)

-  **Supremum** : $p_0$ supremum von A, wenn $p_{0}$ die kleinste obere Schranke von $A$ ist; wir schreiben dann $p_0$ = $sup A$.

### Bemerkungen:
- **Anmerkung 2.1.2.5** 
	$\forall x \in \mathbb{X} : x$  ist obere und unterre schranke von $\emptyset$  aber man betrachte, dass die leere Menge zwar kein kleinstes oder minimales Element enthalten kann.

#### (1)
Wähle $B   \subseteq P$ beliebig, betrachte  $b \in B \text{ ang. } \forall b \in B : b \leq a$ dann ist a eine Obere Schranke von $B$ 

##### Definiere:
- $O_{B}:\{p \in P |\forall b \in B : p \geq b\}$ $\dots$ Die Menge aller oberen Schranken von B
- $U_{B} := \{p \in P | \forall b \in B :p \leq b\}$ $\dots$ Die menge aller unterren Schranken von B

Nach vorraussetzung wissen wir das $O_{B}$ ein Infimum hat. Sei also $a := inf\{O_{B}\}$ dann ist  a also die größte untere Schranke von den Oberen schranken. D.h $inf(O_{B}) = sup(B)$

#### (2)
Nach *Anmerkung 2.1.2.5* Wissen wir das $\emptyset$ keine Unterre schranke hat da $\emptyset \subset \mathbb{N}$ sind die Vorraussetzungen nicht erfüllt.
