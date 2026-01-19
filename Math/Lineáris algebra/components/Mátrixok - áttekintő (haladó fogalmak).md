[[math]], [[Matrixok]], #matrix, #matek

---

## 1) Determináns
Egy négyzetes mátrixhoz rendelhető egy szám, a **determináns**.

- 2×2 esetén:
$$
\det \begin{bmatrix} a & b \\ c & d \end{bmatrix} = ad - bc
$$

- 3×3 esetén:
$$
\det \begin{bmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{bmatrix}
= aei + bfg + cdh - ceg - bdi - afh
$$

**Tulajdonságok:**
- $\det(AB) = \det(A)\det(B)$  
- $\det(A^T) = \det(A)$  
- Ha $\det(A)=0$, akkor $A$ szinguláris (nincs inverze).  

---

## 2) Rang
A mátrix rangja: a lineárisan független sorok/oszlopok száma.  

**Meghatározás:**
- Gauss–Jordan-eliminációval: a lépcsős alak nemnulla sorainak száma = rang.  
- A legnagyobb nemnulla aldetermináns mérete = rang.

**Tulajdonság:**
- $\mathrm{rang}(A) \leq \min(m,n)$ egy $m \times n$ mátrixnál.  
- Invertálhatóság feltétele: $\mathrm{rang}(A)=n$ egy $n\times n$ mátrixnál.

---

## 3) Nyom (trace)
A főátló elemeinek összege.

$$
\mathrm{tr}(A) = \sum_{i=1}^n a_{ii}
$$

**Tulajdonságok:**
- $\mathrm{tr}(A+B) = \mathrm{tr}(A) + \mathrm{tr}(B)$  
- $\mathrm{tr}(kA) = k \cdot \mathrm{tr}(A)$  
- $\mathrm{tr}(AB) = \mathrm{tr}(BA)$  

---

## 4) Sajátérték és sajátvektor
Egy $A$ négyzetes mátrixhoz olyan $\lambda \in \mathbb{R}$ szám és $\vec{v} \neq 0$ vektor, hogy:
$$
A \vec{v} = \lambda \vec{v}
$$

- $\lambda$ = sajátérték  
- $\vec{v}$ = sajátvektor  

**Meghatározás:**  
Az egyenletből:
$$
\det(A - \lambda I) = 0
$$
Ez az ún. **karakterisztikus egyenlet**, megoldásai a sajátértékek.

---

## 5) Diagonalizálás
Egy $A$ mátrix diagonalizálható, ha létezik $P$ invertálható mátrix, hogy:
$$
A = P D P^{-1}
$$
ahol $D$ diagonális mátrix (főátlón a sajátértékek).  

**Feltétel:** $A$-nak legyen $n$ lineárisan független sajátvektora ($n\times n$ mátrix esetén).

---

## 6) Ortogonális mátrix
Egy $Q$ mátrix ortogonális, ha:
$$
Q^T Q = I
$$

**Tulajdonság:**
- Inverze: $Q^{-1} = Q^T$  
- Megőrzi a hosszakat és szögeket (forgatás, tükrözés).  

---

## 7) Pozitív definit mátrix
Egy $A$ szimmetrikus mátrix pozitív definit, ha:
$$
\vec{x}^T A \vec{x} > 0 \quad \forall \vec{x}\neq 0
$$

**Tulajdonságok:**
- Minden sajátértéke pozitív.  
- Fontos a kvadratikus alakoknál és optimalizálásban.  

---

## Megjegyzés
Ez az összefoglaló nem tartalmazza a mátrixok **alapműveleteit** (összeadás, szorzás, transzponált, inverz), mert azok külön jegyzetekben vannak.  
Ez inkább a **lineáris algebrai, haladóbb fogalmak** áttekintése.
