## Aufgabenstellung:
Sei$(V, \leq)$ **Verbandsordnung**. 
Zeigen Sie, dass in $V$ jede nichtleere endliche Menge ein *Supremum* und ein
*Infimum* hat.
- Hinweis Induktion.
- Wenn das zu leicht ist: Finden Sie eine Menge P und eine Verbandsordnung
$(P, \leq)$, in der zwar jede abzählbare Menge und jede endliche Menge ein Infimum
hat, es aber abzählbare Mengen ohne Supremum gibt.

### Definitionen:

- Eine partielle Ordnung $A$ heißt **Verbandsordnung**, wenn je zwei Elemente
$a, b$ eine größte untere Schranke $inf(a, b)$ oder i$nf\{a, b\}$ und eine kleinste
obere Schranke $sup(a, b)$ oder $sup\{a, b\}$ haben.

Sei $A  \subseteq V$ mit $|A| :=n < \infty$ zz.: $\forall n \exists inf{(A)}, inf{(A)}$
#### Induktion (Vgl. Hinweis)

- ##### Induktionsanfang
- ##### (n = 1) 
$A = \{a\}, a \in V$ , dammit ist $inf(A) = a = sup(a)$
- ##### (n = 2):
$A =\{a,b\} \dots$ per definition der Verbandsordnung  
- ##### Indunktionsschritt (n $\mapsto$ n+1):
Sei $A \subseteq V$ mit $|A| = n+1$, wähle ein belibiges $b \in A$ und sätze $\tilde{A} :=A \setminus \{b\}$
Da $|\tilde{A}| = n$ können wir die Inuktionsvorraussetzung anwenden.
Wähle also $c := sup(\tilde{A})$ bzw. $c':= inf(\tilde{A})$.

Nach Vs. betrachten wir eine Verbandsordnung dh. die Menge $\{c,b  \}$ hat wieder ein *Suprämum*, bzw. die Menge $\{ c',b \}$ hat ein *Infimum*

##### Behauptung:
$sup \{c,b  \} = sup\{A\}$ und equivalent dazu $inf\{a', b\} = inf \{ A \}$  
##### begründung:
$sup\{c,b  \} \leq c \wedge sup\{a,b\} \leq b$ so wie $ind\{c',b  \} \leq c' \wedge sup\{c',b\} \leq b$ 

Damit ist o.B.d.A belibige jede unterrre Schranke $t$ von $A$,
 $t \leq inf \{ c',b \}$ ist damit auch eine unterre schranke von $\tilde{A}$ und $inf\{ c',b \}$ bleibt die gröste untere schranke 