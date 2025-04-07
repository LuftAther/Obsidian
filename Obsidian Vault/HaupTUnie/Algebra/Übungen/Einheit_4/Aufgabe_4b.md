Seien $A$ und $B$ Gruppen, und sei $\varphi : B \to \text{Aut}(A)$ ein Homomorphismus. Wir schreiben $\varphi_b$ statt $\varphi(b)$.

Auf der Menge $G := A \times B$ definieren wir eine Operation

$$
(a, b) \triangleright (a', b') := (a \ast \varphi_b(a'), b \ast b')
$$

1. Zeigen Sie, dass $(G, \triangleright, ?, ?)$ mit dieser Operation eine Gruppe ist. (Was muss man für die Fragezeichen einsetzen?)  
2. Zeigen Sie, dass $A \times \{1_B\} \triangleleft G$ und $\{1_A\} \times B \leq G$ gilt.  
3. Sei $A := \mathbb{Z}_4$, $B := \mathbb{Z}_2$, $\varphi : B \to \text{Aut}(A)$ nicht trivial. (Und zwar?) Zeigen Sie, dass $\{0_A\} \times B$ kein Normalteiler von $G$ ist.
---
### 1. Zeigen Sie, dass $(G, \triangleright, ?, ?)$ mit dieser Operation eine Gruppe ist. (Was muss man für die Fragezeichen einsetzen?) 
#### Behauptung:
Sei $e_G := (1_A, 1_B), \text{ wobei } 1_A, 1_B \text{ die neutralen Elemente der Gruppen } A \text{ und } B \text{ sind.}$
Weiters definiere die Abbildung: 
$$
\star : G \to G, \quad (a,b) \mapsto \star(a,b) := (\varphi_{b^{-1}}(a^{-1}), b^{-1})
$$

Dann ist : $(G, \rtimes, e_G, \star)$ ist eine Gruppe, d.h., zu zeigen:

(a) $\rtimes$ ist wohldefiniert und assoziativ  
(b) $e_G$ ist das neutrale Element  
(c) $\star$ definiert ein inverses Element  

---
### (a) Wohldefiniertheit

![[Pasted image 20250407055155.png]]
Also zu zeigen ist, dass für alle $(a,b), (a',b')\in G$  $\exists! y \in G$, sodass $y = (a,b) \rtimes (a',b')$

Da $\varphi$ ein Homomorphismus ist und $\varphi_b$ ein Automorphismus, ist $\varphi_b(a') \in A$ wohldefiniert.  

$\Rightarrow$:

$$
(a\ast \varphi_b(a'), b\ast b')\in G
$$

---

### (b) Assoziativität
$\forall (a_1,b_1),(a_2,b_2),(a_3,b_3)\in G: (a_1,b_1)\rtimes((a_2,b_2)\rtimes (a_3,b_3)) = ((a_1,b_1)\rtimes(a_2,b_2))\rtimes (a_3,b_3)$

Seien $(a_1,b_1),(a_2,b_2),(a_3,b_3)\in G$ beliebig. 
Aus der Definition des Homomorphismus und den Rechenregeln der Gruppen folgt

$$(a_1,b_1)\rtimes((a_2,b_2)\rtimes (a_3,b_3)) = (a_1, b_1)\rtimes (a_2\ast \varphi_{b_2}(a_3), b_2 \ast b_3) = (a_1 \ast \varphi_{b_1}(a_2\ast \varphi_{b_2}(a_3)), b_1 \ast (b_2 \ast b_3))$$
$$ = (a_1 \ast \varphi_{b_1}(a_2) \ast \varphi_{b_1}(\varphi_{ b_2}(a_3)), (b_1 \ast b_2)\ast b_3) = (a_1 \ast \varphi_{b_1}(a_2) \ast \varphi_{b_1 \ast b_2}(a_3), (b_1 \ast b_2)\ast b_3)$$
$$= (a_1 \ast \varphi_{b_1}(a_2), b_1 \ast b_2) \rtimes (a_3, b_3) = ((a_1,b_1)\rtimes(a_2,b_2))\rtimes (a_3,b_3)$$


---

### (c) Neutrales Element
Zu zeigen $\forall (a,b)\in G: (a,b)\rtimes e_G = e_G \rtimes (a,b) = (a,b)$
Seien $(a,b)\in G$ beliebig. Es gilt
$$(a,b) \rtimes e_G = (a,b) \rtimes (1_A,1_B) = (a\ast \varphi_b(1_A), b\ast 1_B) = (a\ast 1_A, b\ast 1_B)=(a,b)$$
$$(1_A,1_B) \rtimes (a,b) = (1_A \ast \varphi_{1_B}(a), 1_B \ast b) = (1_A \ast \text{id}(a), 1_B \ast b ) = (1_A \ast a, 1_B\ast b ) = (a,b)$$

Dmit haben wir das neutrale elment mit $(1_{A},1_{B}) = e_{G}$

---

### (d) Inverses Element
Zu zeigen . $\forall (a,b)\in G: (a,b) \rtimes \veebar(a,b) =  \veebar(a,b) \rtimes (a,b) = e_G$

Seien $(a,b)\in G$ beliebig. Es gilt 
$$(a,b) \rtimes \veebar(a,b) = (a,b) \rtimes (\varphi_{b^{-1}}(a^{-1}), b^{-1}) = (a\ast \varphi_b(\varphi_{b^{-1}}(a^{-1})), b\ast b^{-1}) = (a\ast \varphi_{b\ast b^{-1}}(a^{-1}), b\ast b^{-1}) = $$ $$(a\ast \varphi_{1_B}(a^{-1}), b\ast b^{-1}) = (a\ast a^{-1}, b\ast b^{-1}) = (1_A, 1_B) = e_G$$
$$\veebar(a,b) \rtimes (a,b) = (\varphi_{b^{-1}}(a^{-1}), b^{-1}) \rtimes (a,b) = (\varphi_{b^{-1}}(a^{-1}) \ast \varphi_{b^{-1}}(a), b^{-1} \ast b) = (\varphi_{b^{-1}}(a^{-1} \ast a), b^{-1}\ast b) = $$$$ = (\varphi_{b^{-1}}(1_A), 1_B) = (1_A,1_B) = e_G$$

---

### 2. Zeigen Sie, dass $A \times \{1_B\} \triangleleft G$ und $\{1_A\} \times B \leq G$ gilt.  

#### (a) $A \times \{1_B\} \vartriangleleft G$

### 2.a.1 z.z. $A\times \{1_B\} \leq G$


##### - Behauptung:  $\rtimes|_{A \times \{1_B\}}$ ist abgeschlossen
###### - Begründung: 
 $(a,b), (a',b')\in A\times \{1_B\}$ beliebig. Es gilt $b' = b = 1_B$ weiters gilt  
$$(a,1_B) \rtimes (a',1_B) = (a\ast \varphi_{1_B}(a'), 1_B \ast 1_B) = (a\ast a', 1_B) \in A \times \{1_B\}$$

##### - Behauptung: $\veebar|_{A \times \{1_B\}}$ ist abgeschlossen
#### - Begründung: 
$(a,b) \in A\times \{1_B\}$ beliebig. Es gilt $b = 1_B$, weiters gilt
$$\veebar(a,1_B) = (\varphi_{1_B^{-1}}(a^{-1}), 1_B^{-1}) = (\varphi_{1_B}(a^{-1}), 1_B) = (a^{-1}, 1_B) \in A $$

$\Rightarrow$ $A \times \{1_B\} \leq G$
 
### 2.a.2  z.z $A\times \{1_B\} \textbf{ist unter Konjugation abgeschlossen}$

$\forall g=(g_1,g_2)\in G : ((g \rtimes(A \times \{1_B\})\rtimes \veebar g) \subseteq (A \times \{1_B\}))$
Seien $(g_1,g_2) = g\in G$ und $(a,1_B)\in A\times \{1_B\}$ beliebig. Es gilt

$$\begin{split}
&(g_1, g_2) \rtimes (a,1_B) \rtimes \veebar(g_1,g_2) \\
&= (g_1 \ast \varphi_{g_2}(a), g_2 \ast 1_B) \rtimes (\varphi_{g_2^{-1}}(g_1^{-1}),g_2^{-1}) \\
&= (g_1\ast \varphi_{g_2}(a), g_2)  \rtimes (\varphi_{g_2^{-1}}(g_1^{-1}),g_2^{-1})\\
&= (g_1 \ast \varphi_{g_2}(a) \ast  \varphi_{g_2}(\varphi_{g_2^{-1}}(g_1^{-1})), g_2 \ast g_2^{-1})\\
&= (g_1 \ast \varphi_{g_2}(a) \ast  \varphi_{g_2\ast g_2^{-1}}(g_1^{-1}), g_2 \ast g_2^{-1})\\
&= (g_1 \ast \varphi_{g_2}(a) \ast g_1^{-1}, 1_B) \in A \times \{1_B\}
\end{split}
$$
Damit  $A \times \{1_B\} \vartriangleleft G$

---

#### 2.b.1 z.z $\{1_A\} \times B \leq G$
 $\{1_A\} \times B \leq G \textbf{ ist Untergruppe von } A \times B$


### - Behauptung:  $\rtimes|_{\{1_A\} \times B }$ ist abgeschlossen
#### -Begründung:
Seien $(a,b) , (a',b') \in \{1_A\} \times B$ beliebig. Es gilt $a = a' = 1_A$, weiters gilt 
$$(1_A, b) \rtimes (1_A, b') = (1_A \ast \varphi_{b}(1_A), b \ast b') = (1_A, b \ast b') \in \{1_A\} \times B$$

Beh. $\veebar|_{\{1_A\} \times B }$ ist abgeschlossen

Sei $(a,b)\in \{1_A\} \times B $ beliebig. Es gilt $a = 1_A$, weiters gilt 
$$\veebar(1_A, b) = (\varphi_{b^{-1}}(1_A^{-1}), b^{-1}) = (\varphi_{b^{-1}}(1_A), b^{-1})  = (1_A, b^{-1})\in \{1_A\}\times B $$
wzzw.


Wir haben somit gezeigt, dass $\{1_A\} \times B \leq G$

Abgeschlossenheit:

$$
(1_A, b) \rtimes (1_A, b') = (1_A, b \ast b') \in \{1_A\} \times B
$$

---

### (3) Gegenbeispiel

Wir betrachten:

$$
A = \mathbb{Z}_4, \quad B = \mathbb{Z}_2, \quad \varphi: \mathbb{Z}_2 \to \text{Aut}(\mathbb{Z}_4)
$$

$$
\varphi(0) = \text{id}, \quad \varphi(1) = \text{Negation}
$$

Berechnung:

$$
(3_A, 1_B) \rtimes (0_A, 1_B) \rtimes \star(3_A,1_B) = (2_A, 1_B) \notin \{0_A\} \times B
$$

Also ist $\{0_A\} \times B$ kein Normalteiler.
Wir betrachten $A := \mathbb Z_4$ und $B := \mathbb Z_2$. Sei weiters 
$$\varphi: \mathbb Z_2 \to \text{Aut}(\mathbb Z_4): \left\{\begin{array}{cc}
     0 \mapsto \text{id}_{\mathbb Z_4} \\
      1 \mapsto -_{\mathbb Z_4} 
\end{array} \right.$$
Betrachte weiters $(3_A,1_B)\in G$ und $(0_A, 1_B) \in \{0_A\}\times B$. Wir beobachten, dass
$$(3_A, 1_B) \rtimes (0_A, 1_B) \rtimes \veebar(3_A,1_B) = (3_A, 1_B) \rtimes (0_A, 1_B) \rtimes (\varphi_{-1_B}(-3_A),-1_B) $$
$$ = (3_A + \varphi_{1_B}(0_A), 1_B + 1_B) \rtimes (3_A, 1_B) = (3_A, 0_B)\rtimes (3_A,1_B) = (3_A + \varphi_{0_B}(3_A), 0_B+1_B) $$$$ = (3_A+3_A, 1_B ) = (2_A,1_B)\notin \{0_A\}\times B$$
