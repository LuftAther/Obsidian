Seien $G_1$ und $G_2$ Gruppen, und seien $N_i \leq G_i$ für $i = 1, 2$.

1. Sei $N_1 \cong N_2$ und $G_1 / N_1 \cong G_2 / N_2$. Folgt daraus $G_1 \cong G_2$?
2. Sei $N_1 \cong N_2$ und $G_1 \cong G_2$. Folgt daraus $G_1 / N_1 \cong G_2 / N_2$?
3. Sei $G_1 \cong G_2$ und $G_1 / N_1 \cong G_2 / N_2$. Folgt daraus $N_1 \cong N_2$?

---
#### (1) Aussage: 
- **Aussage:** Sei $N_1 \cong N_2$ und $G_1 / N_1 \cong G_2 / N_2$. Folgt daraus $G_1 \cong G_2$?
- **Behauptung:** Nein

##### Gegenbeispiel:
- $G_1 = \mathbb{Z}_4$, $G_2 = \mathbb{Z}_2 \times \mathbb{Z}_2$  
- $N_1 := \langle 2 \rangle \cong \mathbb{Z}_2$, $N_2 := \{(0,0), (1,0)\} \cong \mathbb{Z}_2$  
Dann ist:  
- $G_1/N_1 \cong \mathbb{Z}_2$,  
- $G_2/N_2 \cong \mathbb{Z}_2$.  
Aber $\mathbb{Z}_4 \not\cong \mathbb{Z}_2 \times \mathbb{Z}_2$, da diese beiden Gruppen unterschiedlich erzeugt werden.  

---
##### Begründung: Weil man es durch multiplizieren kann weil wir wissen ja alle das faktogruppen was mit fakor und damit multiplizieren utun haben

#### (2) Aussage: 
- **Aussage:** Sei $N_1 \cong N_2$ und $G_1 / N_1 \cong G_2 / N_2$. Folgt daraus $G_1 \cong G_2$?
- **Behauptung:** Nein
##### Gegenbeispiel:
- $G_1 = G_2 = \mathbb{Z}_2 \times \mathbb{Z}_4$  
- $N_1 = \{(0,0), (1,0)\} \cong \mathbb{Z}_4$,  
- $N_2 = \{(0,0), (0,2)\} \cong \mathbb{Z}_2$  

Dann ist:  
- $G_1/N_1 \cong \mathbb{Z}_4$,  
- $G_2/N_2 \cong \mathbb{Z}_2 \times \mathbb{Z}_2$.  

Diese Gruppen sind nicht isomorph.
#### (3) Aussage: 
- **Aussage:** Sei $G_1 \cong G_2$ und $G_1 / N_1 \cong G_2 / N_2$. Folgt daraus $N_1 \cong N_2$?
- **Behauptung:** ja

##### Gegenbeispiel: 
- $G_1 = \mathbb{Z}_2 \times \mathbb{Z}_4 = G_2$.  
- $N_1 = \{(0,0), (0,1), (0,2), (0,3)\} \cong \mathbb{Z}_4$,  
- $N_2 = \{(0,0), (1,0), (0,2), (1,2)\} \cong \mathbb{Z}_2 \times \mathbb{Z}_2$.  

Dann ist:  
- $G_1/N_1 \cong \mathbb{Z}_2$,  
- $G_2/N_2 \cong \mathbb{Z}_2$.  
Offensichtlich ist $N_1 \not\cong N_2$.