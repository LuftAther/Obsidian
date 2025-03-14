## Aufgabenstellung:
==(1)== Finden Sie alle Untergruppen der Gruppe $S_3$ (das ist die Gruppe aller Permutationen der Menge $\{1,2,3\}$). ==(2)== Welche davon sind kommutativ?

(Um Ihnen Schreibarbeit zu ersparen, können Sie die Permutation  
$$ \begin{pmatrix} 1 & 2 & 3 \\ 2 & 1 & 3 \end{pmatrix} $$  
auch einfach als 213 schreiben. Sie können natürlich auch Zyklenschreibweise $(12)$ verwenden, siehe Skriptum 2.2.45.)

### Bemerkung 2.2.4.5

![[Anmerkung_2_2_4_5.png]]

- In einer untergruppe $U$ muss $id$  ein Element sein
- $\forall x \in U : x^{-1} \in U$
#### (1)
Die möglichen Permutationen sind:

$id$,$\underbrace{\left(\begin{array}{c c c} 1&2&3 \\ 2 & 1&3 \end{array}\right)}_{T_{1,2}}$,  $\underbrace{\left(\begin{array}{c c c} 1&2&3 \\ 2 & 3&1 \end{array}\right)}_{T_{1,2,3}}$, $\underbrace{\left(\begin{array}{c c c} 1&2&3 \\ 1 &3&2 \end{array}\right)}_{T_{2,3}}$, $\underbrace{\left(\begin{array}{c c c} 1&2&3 \\ 3&1&2 \end{array}\right)}_{T_{1,3,2}}$, $\underbrace{\left(\begin{array}{c c c} 1&2&3 \\ 3&2&1 \end{array}\right)}_{T_{1,3}}$
Das bedeutet $S_{3} = \{ id, T_{1,2},T_{1,3}, T_{2,3}, T_{1,2,3}, T_{1,3,2} \}$ 

#### (2)
Davon sind kommutativ:
- $id$ 
- $\{ id,t_{1,2} \}$, $\{ id, t_{2,3} \}$, $\{id,t_{1,3}  \}$
- $\{ id, T_{123},T_{132} \}$
- $S_{3}$

| ∘               | *id*        | **$T_{1,2}$** | *$T_{2,3}$* | **$T_{1,3}$** | *$T_{1,2,3}$* | *$T_{1,3,2}$* |
| --------------- | ----------- | ------------- | ----------- | ------------- | ------------- | ------------- |
| *id*            | id          |               | 1 3 2       | 3 2 1         | 2 3 1         | 3 1 2         |
| **$T_{1,2}$**   | $T_{1,2}$   | id            | $T_{1,3,2}$ | 3 1 2         | $T_{2,3}$     | $T_{1,3}$     |
| **$T_{2,3}$**   | $T_{1,3,2}$ | $T_{1,3,2}$   | id          | $T_{1,2,3}$   | $T_{1,3}$     | $T_{1,2}$     |
| **$T_{1,3}$**   | $T_{1,3}$   | $T_{1,2,3}$   | $T_{1,2,3}$ | id            | $T_{1,2}$     | $T_{2,3}$     |
| **$T_{1,2,3}$** | $T_{1,2,3}$ | $T_{1,3}$     | $T_{1,2}$   | $T_{2,3}$     | $T_{1,2,3}$   | id            |
| *$T_{1,3,2}$*   | $T_{2,3}$   | $T_{2,3}$     | $T_{1,3}$   | $T_{1,2}$     | id            | $T_{1,2,3}$   |
|                 |             |               |             |               |               |               |
