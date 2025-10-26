# Szinusz kiegészítés

[[math]], #szinusz, #matek, #kiegészítés

## 1) Grafikon és jellemzői

- Alapfüggvény: $y = \sin x$
- Értékkészlet: $[-1, 1]$
- Periódus: $2\pi$ (360°)
- Amplitúdó: 1
- Fő pontok:
  - $\sin 0 = 0$
  - $\sin 	\frac{\pi}{2} = 1$
  - $\sin \pi = 0$
  - $\sin 	\frac{3\pi}{2} = -1$
  - $\sin 2\pi = 0$

A grafikon hullámzó, szimmetrikus az origóra (páratlan függvény).
![[szinusz_grafikon.png]]


---

## 2) Inverz függvény – Arcsin
$$
\begin{aligned}
\textbf{Jelölés:}   &\quad y=\arcsin(x)\\
\textbf{Tartomány:} &\quad x\in[-1,1]\\
\textbf{Értékkészlet:} &\quad y\in\left[-\frac{\pi}{2},\frac{\pi}{2}\right]
\end{aligned}

\begin{aligned}
\arcsin(0.5) &= \frac{\pi}{6} = 30^\circ\\
\arcsin(-1)  &= -\frac{\pi}{2} = -90^\circ
\end{aligned}
$$



---

## 3) Gyakorlati alkalmazások

- **Fizika**: rezgések, hullámmozgás $y(t) = A \sin(\omega t + \varphi)$
- **Mérnöki tudományok**: jelanalízis, elektromos áram, hanghullámok
- **Geometria**: magasság, távolság számítás háromszögekben
- **Csillagászat**: Nap magassági szöge, Hold és bolygók mozgása

---

## 4) Haladó azonosságok

### Szorzat → összeg
$$
\begin{aligned}
\sin\alpha\,\sin\beta &= \frac{1}{2}\left[\cos(\alpha-\beta) - \cos(\alpha+\beta)\right],\\[4pt]
\cos\alpha\,\sin\beta &= \frac{1}{2}\left[\sin(\alpha+\beta) - \sin(\alpha-\beta)\right],\\[4pt]
\cos\alpha\,\cos\beta &= \frac{1}{2}\left[\cos(\alpha-\beta) + \cos(\alpha+\beta)\right].
\end{aligned}
$$
### Összeg → szorzat
$$
\begin{aligned}
\sin\alpha + \sin\beta &= 2\,\sin\frac{\alpha+\beta}{2}\,\cos\frac{\alpha-\beta}{2},\\[4pt]
\sin\alpha - \sin\beta &= 2\,\cos\frac{\alpha+\beta}{2}\,\sin\frac{\alpha-\beta}{2},\\[4pt]
\cos\alpha + \cos\beta &= 2\,\cos\frac{\alpha+\beta}{2}\,\cos\frac{\alpha-\beta}{2},\\[4pt]
\cos\alpha - \cos\beta &= -2\,\sin\frac{\alpha+\beta}{2}\,\sin\frac{\alpha-\beta}{2}.
\end{aligned}
$$

---

## 5) Trigonometrikus egyenletek

### Alapegyenlet
$$
\sin x = a
$$
- Megoldás: $x=\arcsin(a)+360^\circ k \quad \text{vagy}\quad x=180^\circ-\arcsin(a)+360^\circ k.$
  ($k \in \mathbb{Z}$)
Megjegyzés: ha $∣a∣>1|a|>1∣a∣>1$, nincs valós megoldás.
### Példa
$$
\sin x = 	\frac{1}{2}
$$

1. $x_1 = \arcsin(	\frac{1}{2}) =\frac{\pi}{6}$
2. $x_2 = \pi - 	\frac{\pi}{6} = 	\frac{5\pi}{6}$

Általános megoldás:

$x = 	\frac{\pi}{6} + 2k\pi \quad$ vagy $\quad x = \frac{5\pi}{6} + 2k\pi$
