[[math]], [[Matrixok]], #matrix, #matek

## Definíció
Egy mátrix **rangja** a benne lévő **lineárisan független sorok vagy oszlopok száma**.  
Ez megmutatja, hogy mennyi „független információt” tartalmaz a mátrix.

Jelölése:  
$$
\mathrm{rang}(A) \quad \text{vagy} \quad \mathrm{rk}(A)
$$

---

## Hogyan számoljuk?

1. **Sor/oszlopok lineáris függetlenségével**  
   Megnézzük, hány sor (vagy oszlop) állítható elő a többiek lineáris kombinációjaként.

2. **Gauss–Jordan-eliminációval**  
   A mátrixot **lépcsős alakra** hozzuk.  
   A rang = a nemnulla sorok száma.

3. **Determinánssal**  
   A legnagyobb olyan négyzetes aldetermináns mérete, ami nem nulla → ez a rang.

---

## Példa 1 (2×2 mátrix)

$$
A =
\begin{bmatrix}
1 & 2 \\
2 & 4
\end{bmatrix}
$$

A második sor kétszerese az elsőnek, tehát csak **1 független sor van**.

$$
\mathrm{rang}(A) = 1
$$

---

## Példa 2 (3×3 mátrix)

$$
B =
\begin{bmatrix}
1 & 2 & 3 \\
0 & 1 & 4 \\
0 & 0 & 0
\end{bmatrix}
$$

Ez lépcsős alakban van, és **2 nemnulla sora van**.  

$$
\mathrm{rang}(B) = 2
$$

---

## Példa 3 (teljes rang)

$$
C =
\begin{bmatrix}
1 & 0 & 2 \\
0 & 1 & -1 \\
3 & 4 & 0
\end{bmatrix}
$$

Ezt Gauss-eliminációval alakítva 3 független sort kapunk.  
Mivel 3×3-as mátrix, a rang maximum 3 lehet, és itt valóban:

$$
\mathrm{rang}(C) = 3
$$

---

## Tulajdonságok

- A rang **nem nagyobb** a sorok vagy oszlopok számánál:
  $$
  \mathrm{rang}(A) \leq \min(m,n)
  $$

- Egy mátrix invertálható akkor és csak akkor, ha:
  $$
  \mathrm{rang}(A) = n \quad (n\times n \text{ mátrix esetén})
  $$

- Transzponálás nem változtatja meg a rangot:
  $$
  \mathrm{rang}(A) = \mathrm{rang}(A^T)
  $$

---

## Megjegyzés
A rang fontos a **lineáris egyenletrendszerek megoldásánál**:
- Ha a rang = ismeretlenek száma, akkor egyértelmű a megoldás.  
- Ha kisebb, akkor vagy végtelen sok, vagy nincs megoldás.
