# Determináns

[[math]], [[Matrixok]], #matrix, #determinans, #matek

## 1) 2×2-es determináns
$$
\det \begin{bmatrix}
a & b \\
c & d
\end{bmatrix} = ad-bc
$$

**Példa:**
$$
\det \begin{bmatrix}1&2\\3&4\end{bmatrix} = 1\cdot4-2\cdot3=-2
$$

---

## 2) 3×3-as determináns (Sarrus-szabály)
$$
\det \begin{bmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{bmatrix} =
aei+bfg+cdh-ceg-bdi-afh
$$

**Példa:**
$$
\det \begin{bmatrix}1&2&3\\0&1&4\\5&6&0\end{bmatrix} = 1
$$

---

## 3) Laplace-kifejtés (általános)
$$
\det A = \sum_{j=1}^n (-1)^{i+j} a_{ij}M_{ij}
$$
ahol $(M_{ij})$ az $(i,j)$-edik minor.

---

## 4) Tulajdonságok
- Ha két sor egyforma → det = 0
- Háromszögmátrix det-je = főátló szorzata
- $(\det(AB)=\det A \cdot \det B)$
