# Aufgabenstellung
Beantworten Sie die folgenden Fragen:  
(Beweisen Sie oder finden Sie ein Gegenbeispiel.)

1. Sei $(A, +, 0, -)$ eine Gruppe (und daher auch eine Halbgruppe), und $(B, +)$ eine Unterhalbgruppe von $(A, +)$.  
   Kann $B$ durch geeignete Wahl von Operationen $0'$, $-'$ zu einer Gruppe $(B, +, 0', -')$ gemacht werden?
*(Analog sind die folgenden Aufgaben zu verstehen, d.h., es geht immer darum, neue Operationen/Konstante hinzuzufügen, niemals neue Elemente.)*

2. Sei $(A, +, 0)$ ein Monoid (und daher auch eine Halbgruppe $(A, +)$), und $B$ eine Unterhalbgruppe von $A$, die zu einem Monoid gemacht werden kann.  
   Ist $B$ ein Untermonoid?

3. Sei $A$ eine Gruppe (und daher auch eine Halbgruppe), und $B$ eine Unterhalbgruppe von $A$, die zu einer Gruppe gemacht werden kann. Ist $B$ eine Untergruppe?

4. Sei $A$ ein 1-Ring und $B$ ein Unterring, der zu einem 1-Ring gemacht werden kann.  
   Ist $B$ ein Unter-1-Ring?
---
### Definitionen:
#### Monoid:
![[Monoid – Wikipedia.png]]
#### 1-Ring:
![[Ring (Algebra) – Wikipedia.png]]
##### Untergruppe:
![[untergruppe.png]]

### 1) **Frage**: 
#### Behauptung: Falsch

**Gegenbeispiel**(1):  
- $A = (\mathbb{R}^+, \cdot)$ ist eine Gruppe  
- $B = (\mathbb{N} \setminus \{0\}, \cdot)$ ist eine Unterhalbgruppe

Wähle $1$ als neutrales Element ⇒ dann müsste für jedes $n \in B$ auch $n^{-1} \in B$ gelten  
Aber z. B. $1/2 \notin \mathbb{N}$ ⇒ kein Inverses
$\Rightarrow$ $B$ kann **nicht** zu einer Gruppe gemacht werden
**Gegenbeispiel(2)**:
- $A:=(\mathbb{Z}, +, 0,-)$ eine Gruppe dann ist
- $B :=  (\mathbb{N} \setminus \{ 0 \}, +)$ eine Untergruppe aner **keine** Gruppe 

---

### 2)  **Frage**: 
#### Behauptung: Falsch

**Gegenbeispiel**:  
- $A = (\mathbb{N}, \max, 0)$ ist ein Monoid  
	- Sei o.B.d.A $l,n,m \in \mathbb{N} l<n<m$ dann gilt:
		- $max\{max \{ l,n \},m\} = max\{l,max \{ n,m \}\} \dots$ Assoziativität
		- $max\{ n,0 \} = n \dots$ Neutrales Element
- $B = (\mathbb{N} \setminus \{0\}, \max)$ ist Halbgruppe, **aber** $0 \notin B$ ⇒ kein neutrales Element in $B$
$\Rightarrow$ $B$ ist Monoid aber**kein** Untermonoid

---
### 3) **Frage**: 
#### Behauptung: Wahr
**Beweis**: Zeige, dass $0' = 0$

- Sei $b \in B$, dann:
$$b + 0' = b \Rightarrow 0' = -b + b = 0 \tag{1}$$
	Außerdem:
$$b + (-'b) = 0 \Rightarrow -' = -\mathbb{1}_{B}  \tag{2}$$
- $B$ ist bezüglich der Addition abgeschlossen

⇒ Da $B$ eine Unterhalbgruppe ist und $(B, +, 0, -)$ eine Gruppe ist, folgt:  
$B$ ist **Untergruppe** von $A$

---

### 4) **Frage**:

#### Behauptung: Falsch
**Gegenbeispiel**:  
- $A = (\mathbb{R}, +, -, 0, \cdot, 1)$  
- $B = 2\mathbb{Z}$ (gerade Zahlen)

⇒ $B$ ist Unterring von $\mathbb{R}$  **aber**: $1 \notin 2\mathbb{Z}$ ⇒ $B$ ist **kein** Unter-1-Ring
