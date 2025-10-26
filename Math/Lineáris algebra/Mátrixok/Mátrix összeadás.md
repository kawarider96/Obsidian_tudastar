[[math]], [[Matrixok]], #matrix, #matek

## Definíció
Két azonos méretű mátrixot úgy adunk össze, hogy az **egymásnak megfelelő elemeket** összeadjuk.

Formálisan:
$$
C = A + B \quad \Rightarrow \quad c_{ij} = a_{ij} + b_{ij}
$$

Ez azt jelenti, hogy minden sor-oszlop pozícióban külön számoljuk ki az összeget.

---

## Példa 1 (2×2 mátrixok)

$$
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
+
\begin{bmatrix}
5 & 6 \\
7 & 8
\end{bmatrix}
=
\begin{bmatrix}
1+5 & 2+6 \\
3+7 & 4+8
\end{bmatrix}
=
\begin{bmatrix}
6 & 8 \\
10 & 12
\end{bmatrix}
$$

---

## Példa 2 (3×3 mátrixok)

$$
\begin{bmatrix}
1 & -1 & 2 \\
0 & 3 & 4 \\
5 & 0 & -2
\end{bmatrix}
+
\begin{bmatrix}
2 & 4 & 0 \\
1 & -3 & 2 \\
-1 & 2 & 3
\end{bmatrix}
=
\begin{bmatrix}
3 & 3 & 2 \\
1 & 0 & 6 \\
4 & 2 & 1
\end{bmatrix}
$$

---

## Tulajdonságok

- **Kommutatív**:  
  $$
  A + B = B + A
  $$

- **Asszociatív**:  
  $$
  (A + B) + C = A + (B + C)
  $$

- **Nullmátrix** létezik:  
  $$
  A + 0 = A
  $$

---

## Megjegyzés
Az összeadás csak **azonos dimenziójú** mátrixok esetén értelmezett.
