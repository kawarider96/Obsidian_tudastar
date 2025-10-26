[[math]], [[Matrixok]], #matrix, #matek

## Definíció
Két mátrixot akkor szorozhatunk össze, ha az **első mátrix oszlopainak száma** megegyezik a **második mátrix sorainak számával**.  

Az eredmény egy új mátrix, ahol minden elem úgy jön ki, hogy az első mátrix adott sorát **beszorozzuk** a második mátrix megfelelő oszlopával.

Formálisan:
$$
C = A \cdot B, \quad
c_{ij} = \sum_{k=1}^n a_{ik} \cdot b_{kj}
$$

---

## Példa 1 (2×2 mátrixok)

$$
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
\cdot
\begin{bmatrix}
5 & 6 \\
7 & 8
\end{bmatrix}
=
\begin{bmatrix}
1\cdot 5 + 2\cdot 7 & 1\cdot 6 + 2\cdot 8 \\
3\cdot 5 + 4\cdot 7 & 3\cdot 6 + 4\cdot 8
\end{bmatrix}
=
\begin{bmatrix}
19 & 22 \\
43 & 50
\end{bmatrix}
$$

---

## Példa 2 (2×3 szorozva 3×2-vel → eredmény 2×2)

$$
\begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{bmatrix}
\cdot
\begin{bmatrix}
7 & 8 \\
9 & 10 \\
11 & 12
\end{bmatrix}
=
\begin{bmatrix}
1\cdot 7 + 2\cdot 9 + 3\cdot 11 & 1\cdot 8 + 2\cdot 10 + 3\cdot 12 \\
4\cdot 7 + 5\cdot 9 + 6\cdot 11 & 4\cdot 8 + 5\cdot 10 + 6\cdot 12
\end{bmatrix}
=
\begin{bmatrix}
58 & 64 \\
139 & 154
\end{bmatrix}
$$

---

## Tulajdonságok

- **Nem kommutatív** általában:  
  $$
  A \cdot B \neq B \cdot A
  $$

- **Asszociatív**:  
  $$
  (A \cdot B)\cdot C = A \cdot (B \cdot C)
  $$

- **Disztributív**:  
  $$
  A \cdot (B+C) = AB + AC
  $$

- Az **egységmátrix** szerepe:  
  $$
  A \cdot I = I \cdot A = A
  $$

---

## Megjegyzés
A mátrixszorzás a **vektorszorzás általánosítása**.  
Sokat használják lineáris egyenletrendszerek megoldásánál, transzformációknál (pl. forgatás, tükrözés), és számítógépes grafikában is.
