[[math]], [[Matrixok]], #matrix, #matek

## Definíció
A mátrix **nyoma** (angolul *trace*) egy négyzetes mátrix főátlójának elemeinek összege.  

Formálisan, ha
$$
A = (a_{ij}) \in \mathbb{R}^{n\times n},
$$
akkor:
$$
\mathrm{tr}(A) = \sum_{i=1}^{n} a_{ii}
$$

---

## Példa 1 (2×2 mátrix)

$$
A =
\begin{bmatrix}
3 & 2 \\
5 & 7
\end{bmatrix}
$$

$$
\mathrm{tr}(A) = 3 + 7 = 10
$$

---

## Példa 2 (3×3 mátrix)

$$
B =
\begin{bmatrix}
1 & 4 & 0 \\
-2 & 5 & 3 \\
7 & 8 & 9
\end{bmatrix}
$$

$$
\mathrm{tr}(B) = 1 + 5 + 9 = 15
$$

---

## Tulajdonságok

- Lineáris:  
  $$
  \mathrm{tr}(A+B) = \mathrm{tr}(A) + \mathrm{tr}(B)
  $$
  $$
  \mathrm{tr}(kA) = k \cdot \mathrm{tr}(A)
  $$

- Transzponálás nem változtatja:  
  $$
  \mathrm{tr}(A^T) = \mathrm{tr}(A)
  $$

- Szorzatnál körkörös tulajdonság:  
  $$
  \mathrm{tr}(AB) = \mathrm{tr}(BA)
  $$
  (de általában \(AB \neq BA\)!)

---

## Megjegyzés
- A nyom sok helyen felbukkan a lineáris algebrában és fizikában.  
- Például: egy mátrix sajátértékeinek összege mindig egyenlő a nyommal.  
- Kvantummechanikában a sűrűségmátrix nyoma = 1, ami a valószínűségek normalizáltságát fejezi ki.
