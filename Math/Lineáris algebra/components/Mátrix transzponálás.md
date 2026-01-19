[[math]], [[Matrixok]], #matrix, #matek

## Definíció
Egy mátrix **transzponáltját** úgy kapjuk meg, hogy a sorokat és az oszlopokat felcseréljük.  
Formálisan:
$$
(A^T)_{ij} = a_{ji}
$$

Vagyis: az \(i\)-edik sor az \(i\)-edik oszlop lesz, és fordítva.

---

## Példa 1 (2×2 mátrix)

$$
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}^T
=
\begin{bmatrix}
1 & 3 \\
2 & 4
\end{bmatrix}
$$

---

## Példa 2 (2×3 mátrix → 3×2 lesz belőle)

$$
\begin{bmatrix}
1 & 4 & 7 \\
2 & 5 & 8
\end{bmatrix}^T
=
\begin{bmatrix}
1 & 2 \\
4 & 5 \\
7 & 8
\end{bmatrix}
$$

---

## Tulajdonságok

- Dupla transzponálás visszaadja az eredetit:  
  $$
  (A^T)^T = A
  $$

- Összeadásnál:  
  $$
  (A+B)^T = A^T + B^T
  $$

- Szorzásnál a sorrend felcserélődik:  
  $$
  (AB)^T = B^T A^T
  $$

- Skalárral szorzásnál:  
  $$
  (kA)^T = kA^T
  $$

---

## Megjegyzés
- Ha egy mátrix **szimmetrikus**, akkor $(A^T = A)$.  
- A transzponálás nagyon fontos a vektor- és mátrixműveleteknél (pl. skaláris szorzat mátrixos formában: $(x^T y)$).
