In jeder Gruppe $(H, \cdot, 1, {}^{-1})$ ist $a^n$ für $n \in \mathbb{Z}$ folgendermaßen definiert:  
$a^0$ ist das neutrale Element $1$, $a^{n+1} := a^n \cdot a$ für $n \geq 0$, $a^{-1}$ ist das Inverse von $a$,  
und $a^{-n} := (a^{-1})^n$ für $n \geq 2$.  

Zeige, dass $a^{m+n} = a^m a^n$, für alle $a, b \in H$ und $m, n \in \mathbb{Z}$.  

### Hinweise:  
- Verwenden Sie vollständige Induktion, und geben Sie explizit an, auf welche Teilmenge von $\mathbb{N}$ Sie das Induktionsprinzip anwenden.  
  Achtung: Gelegentlich sind Fallunterscheidungen wie z.B. $n \geq 0, n < 0$ notwendig.  
- Geben Sie explizit an, wo und wie Sie das Assoziativgesetz verwenden.  
  ("Wie" bedeutet: Geben Sie an, für welche $A, B, C$ Sie $(AB)C = A(BC)$ verwenden.)  
- Beachten Sie, dass $H$ im Allgemeinen nicht kommutativ ist.  
- Im Rahmen dieses Beweises könnte vielleicht die Aussage $a^{n+1} = a^n \cdot a$ für alle $n \in \mathbb{Z}$ (die Sie dann beweisen müssen) nützlich sein.  
- Rechenregeln für die ganzen Zahlen (wie z.B. Assoziativ- oder Kommutativgesetze in $\mathbb{Z}$,  
  oder $n - 1 + 1 = n$) dürfen Sie ohne Beweis verwenden.


**Beweis:**  
1) $\forall n \in \mathbb{Z}: a^{m+n} = a^m a^n$  
2) $\forall n \in \mathbb{Z}: a^{-n} = (a^{-1})^n$

---

**Fallunterscheidung:**  

**1.**  
- Falls $n \geq 0$:  
  $$ a^{n+1} = a^n \cdot a $$
- Falls $n < 0$:  
  $$ a^{n+1} = a^n \cdot a = (a^{-1})^{-n} \cdot a $$
  $$ = (a^{-1})^{-n} \cdot a = (a^{-1})^{-n} \cdot a^{-1} \cdot a^{-1} \cdot a^{-1} $$  
  $\Rightarrow a^n a = a^k$

---

**2.**  
- Falls $n \geq 0$: trivial  
- Falls $n < 0$:  
  $$ \forall k \in \mathbb{N}: (a^{-1})^{-k} = (a^{-1})^{-1 \cdot k} = a^k $$  
  $\Rightarrow \exists k \in \mathbb{N}, x_k = n$  

  Also:  
  $$ a^n = a^{-k} $$  
  $$ a^n a^k = a^{-k} a^k = \mathbf{e} $$  
  $\Rightarrow (a^{-1})^n = a^{-n}$ ✅
