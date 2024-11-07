Für $p \in [1, \infty]$ und $f, g \in L^p(\mu)$ gilt:

$$∥f+g∥p≤∥f∥p+∥g∥p.(7.2)\|f + g\|_p \leq \|f\|_p + \|g\|_p. \tag{7.2}∥f+g∥p​≤∥f∥p​+∥g∥p​$$

# Beweis:

Der Fall $p = \infty$ ist wieder trivial. Sei daher $p \in [1, \infty)$. Der linke Ausdruck in (7.2) wird nicht kleiner, wenn wir $f$ und $g$ durch $|f|$ und $|g|$ ersetzen. Wir können daher ohne Einschränkung annehmen, dass $f \geq 0$, $g \geq 0$ und $|f + g|_p > 0$ gilt.

Da $(f + g)^p \leq 2^p (f^p \lor g^p) \leq 2^p (f^p + g^p)$, folgt, dass $f + g \in L^p(\mu)$ ist. Unter Verwendung der [[Klenke Hölders Ungleichung]], angewandt auf $f \cdot (f + g)^{p-1}$ und $g \cdot (f + g)^{p-1}$, erhalten wir:

$$∥f+g∥pp=∫(f+g)p dμ=∫f(f+g)p−1 dμ+∫g(f+g)p−1 dμ.\|f + g\|_p^p$$ $$= \int (f + g)^{p \, d\mu = \int f (f + g)^{p-1} \, d\mu + \int g (f + g)^{p-1} \, d\mu.∥f+g∥pp}=∫(f+g)pdμ$$$$=∫f(f+g)p−1dμ+∫g(f+g)p−1dμ.$$
Unter Anwendung der Hölder-Ungleichung ergibt sich:

$$∥f+g∥^p_{p}\leq∥f∥p⋅∥(f+g)p−1∥q+∥g∥p⋅∥(f+g)p−1∥q$$$$=(∥f∥p+∥g∥p)⋅∥f+g∥pp−1,\|f + g\|_p^p \leq \|f\|_p \cdot \|(f + g)^{p-1}\|_q + \|g\|_p \cdot \|(f + g)^{p-1}\|_q$$$$ = (\|f\|_p + \|g\|_p) \cdot \|f + g\|_p^{p-1},∥f+g∥pp​≤∥f∥p​⋅∥(f+g)p−1∥q​+∥g∥p​⋅∥(f+g)p−1∥q​$$$$=(∥f∥p​+∥g∥p​)⋅∥f+g∥pp−1​,$$

wobei wir im letzten Schritt verwendet haben, dass $p - \frac{p}{q} = 1$ ist. Wenn wir nun beide Seiten durch $|f + g|_p^{p-1}$ teilen, folgt (7.2).