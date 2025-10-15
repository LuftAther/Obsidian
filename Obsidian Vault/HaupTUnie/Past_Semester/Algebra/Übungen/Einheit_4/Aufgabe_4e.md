
### 1. Zeige: Die Abbildung $G/G_{x} \rightarrow G \circ x$, die die Linksklasse $gG_{x}$ auf $gx$ abbildet, ist (wohldefiniert und) eine Bijektion.  

### 2. Sei $G$ endlich. Zeige: $\lvert G \circ x \rvert \cdot \lvert G_{x} \rvert = \lvert G \rvert$.

---
![[Pasted image 20250407204202.png]]
# **1. Wohldefiniertheit und Bijektivität der Abbildung $G/G_{x} \rightarrow G \circ x$**

#### Gegeben:
- Gruppe $G$ und Stabilisator $G_{x} = \{ g \in G \mid gx = x \}$  
- Abbildung: $G/G_{x} \rightarrow G \circ x$, definiert durch $gG_{x} \mapsto gx$

Deffiniere:$\varphi: G/G_x \to G \circ x, \quad gG_x \mapsto g \cdot x$ Damit die Abbildung einen Namen hat.
## 1.1 Bijektivität
### 1.1.1 Injektivität:
ine Abbildung $\varphi: G/G_x \to G \circ x$ ist injektiv, wenn gilt:  
$$
\varphi(g_1G_x) = \varphi(g_2G_x) \implies g_1G_x = g_2G_x
$$

Angenommen, es seien $g_1, g_2 \in G$ mit 
$$
g_1 \cdot x \neq g_2 \cdot x
$$

Nun betrachten wir die Abbildung $\varphi$:

$$
\varphi(g_1G_x) = g_1 \cdot x \quad \text{und} \quad \varphi(g_2G_x) = g_2 \cdot x
$$

Da nach Annahme $g_1 \cdot x \neq g_2 \cdot x$, folgt:

$$
\varphi(g_1G_x) \neq \varphi(g_2G_x)
$$

Das bedeutet, dass die Linksklassen $g_1G_x$ und $g_2G_x$ **verschiedene Bilder** unter $\varphi$ haben. Da verschiedene Elemente des Urbildes auch verschiedene Bilder haben, ist die Abbildung **injektiv**.
### 1.1.2 Surjektivität:
$\varphi: G/G_x \to G \circ x$ ist surjektiv, wenn jedes Element der Bahn $G \circ x$ ein Urbild unter $\varphi$ besitzt
$$
   \varphi(gG_x) = g \cdot x
   $$

   ZZ: Es existiert ein $gG_x \in G/G_x$, sodass:
   $$
   \varphi(gG_x) = y
   $$
   Da $y = g \cdot x$, folgt:
   $$
   \varphi(gG_x) = y
   $$
### 2. **Wohldefiniertheit:**  
![[Pasted image 20250407055155.png]]
##### Wohldefiniertheit der Abbildung $G/G_{x} \rightarrow G \circ x$
Z.Z: Die Abbildung $\varphi$ ist wohldefiniert, d.h. wenn zwei Repräsentanten $g_1, g_2 \in G$ dieselbe Linksklasse bilden, dann haben sie auch dasselbe Bild unter $\varphi$.

Angenommen, es seien $g_1, g_2 \in G$ mit  
$$
g_1G_x = g_2G_x
$$  
Das bedeutet, dass es ein Element $h \in G_x$ gibt, sodass:  
$$
g_2 = g_1h
$$  
Da $h \in G_x$, gilt per Definition des Stabilisators:
$$
h \cdot x = x
$$

Nun betrachten wir:  
$$
\varphi(g_2G_x) = g_2 \cdot x = (g_1h) \cdot x = g_1 \cdot (h \cdot x) = g_1 \cdot x = \varphi(g_1G_x)
$$



---

### **2. Zeige: $\lvert G \circ x \rvert \cdot \lvert G_{x} \rvert = \lvert G \rvert$**

## Gegeben:
- $G$ ist eine **endliche Gruppe**.
- $G_x \leq G$ ist der **Stabilisator** eines Elements $x \in X$.  

$\lvert G : G_x \rvert = \frac{\lvert G \rvert}{\lvert G_x \rvert}$
Das bedeutet, dass die Anzahl der **Linksklassen** von $G_x$ in $G$ gleich dem Verhältnis der Ordnungen von $G$ und $G_x$ ist.

Betrachte den *Satz von Lagrange*

![[Pasted image 20250407204507.png]]

---

## **Beweis**

- Da $\varphi$ eine Bijektion ist, gilt:
  $$
  \lvert G/G_x \rvert = \lvert G \circ x \rvert
  $$

- Außerdem gilt nach dem Satz von Lagrange:
  $$
  \lvert G \rvert = \lvert G_x \rvert \cdot \lvert G/G_x \rvert
  $$

- Wenn wir $G/G_x$ durch $G \circ x$ ersetzen, erhalten wir:
  $$
  \lvert G \rvert = \lvert G_x \rvert \cdot \lvert G \circ x \rvert
  $$

- Also ist:
  $$
  \lvert G \circ x \rvert = \frac{\lvert G \rvert}{\lvert G_x \rvert}
  $$