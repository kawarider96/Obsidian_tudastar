[[math]], [[Matrixok]], #matrix, #matek

## Definíció
Egy \(A\) négyzetes mátrix inverze \(A^{-1}\) olyan mátrix, amelyre:
$$
A \cdot A^{-1} = A^{-1} \cdot A = I
$$

ahol \(I\) az egységmátrix.

---

## Mikor létezik?
- Csak **négyzetes mátrixnak** lehet inverze.  
- A **determinánsa nem lehet nulla**:  
  $$
  \det(A) \neq 0
  $$

Ha $(\det(A)=0)$, a mátrixot **szingulárisnak** nevezzük, és nincs inverze.

---

## Képlet (2×2 mátrix esetén)

Ha
$$
A = 
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$

akkor
$$
A^{-1} = \frac{1}{ad-bc}
\begin{bmatrix}
d & -b \\
-c & a
\end{bmatrix}
$$

---

## Példa 1 (2×2 mátrix)

$$
A = 
\begin{bmatrix}
2 & 1 \\
5 & 3
\end{bmatrix}
$$

Determináns:
$$
\det(A) = 2\cdot 3 - 5\cdot 1 = 6 - 5 = 1
$$

Tehát:
$$
A^{-1} =
\begin{bmatrix}
3 & -1 \\
-5 & 2
\end{bmatrix}
$$

Ellenőrzés:
$$
A \cdot A^{-1} =
\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix} = I
$$

---

## Példa 2 (nagyobb mátrix)

3×3 vagy nagyobb mátrixnál az inverz bonyolultabb.  
Általános módszerek:
- **Gauss–Jordan elimináció**: melléírjuk az egységmátrixot, és sorlépésekkel $(I)$-vé alakítjuk $(A)$-t. Ami az egységmátrix helyén lesz, az az $(A^{-1}$).  
- **Adjungált mátrix módszer**: kofaktor mátrixot képezünk, transzponáljuk, majd osztjuk a determinánssal.

---

## Tulajdonságok

- Ha \(A\) invertálható, akkor:
  $$
  (A^{-1})^{-1} = A
  $$

- Szorzat inverze:
  $$
  (AB)^{-1} = B^{-1}A^{-1}
  $$

- Transzponált inverze:
  $$
  (A^T)^{-1} = (A^{-1})^T
  $$

---

## Megjegyzés
Az inverz mátrix szerepe olyan, mint a számoknál a reciprok:  
ahogy $(a \cdot \tfrac{1}{a} = 1)$, úgy $(A \cdot A^{-1} = I)$.
