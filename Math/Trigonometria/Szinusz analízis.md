# Szinusz – Analízis és haladó kiegészítés

[[math]], #szinusz, #analízis, #haladó

Lásd még: [[Szinusz]], [[SzinuszAzonossagok]], [[SzinuszKiegeszites]], [[Fok és Radián]]

## 1) Általános transzformációk
Egy általános szinusz függvény:
$$
y = A\sin(Bx + C) + D
$$
- **Amplitúdó:** $|A|$ (csúcsok: $D \pm |A|$)  
- **Periódus:** $T = \frac{2\pi}{|B|}$  
- **Fáziseltolás:** $x = -\frac{C}{B}$ (vízszintes eltolás)  
- **Vertikális eltolás:** $D$

**Példa:** $y = 3\sin\!\left(2x - \frac{\pi}{3}\right) - 1$ → $A=3$, $T=\pi$, fáziseltolás $x=\frac{\pi}{6}$, középvonal $y=-1$.

---

## 2) Deriválás és integrálás
- Derivált: $\frac{d}{dx}(\sin x)=\cos x$  
- Második derivált: $\frac{d^2}{dx^2}(\sin x)=-\sin x$  
- Integrál: $\int \sin x\,dx = -\cos x + C$  
- Általános: $\frac{d}{dx}\sin(ax+b)=a\cos(ax+b)$,  
  $\displaystyle \int \sin(ax+b)\,dx = -\frac{1}{a}\cos(ax+b)+C$.

---

## 3) Sorfejtés (Maclaurin)
$$
\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \cdots
$$
Konvergál minden $x\in\mathbb{R}$-re.

---

## 4) Euler-képlet és komplex exponenciális
$$
e^{ix} = \cos x + i\sin x
$$
Innen:
$$
\sin x = \frac{e^{ix} - e^{-ix}}{2i}, \qquad
\cos x = \frac{e^{ix} + e^{-ix}}{2}.
$$
Ez a Fourier-analízis alapja, mert a szinusz/koszinusz exponenciális komponensekre bontható.

---

## 5) Fourier-kapcsolat (vázlat)
Periodikus jelek $f(x)$ felbonthatók szinuszok és koszinuszok (vagy $e^{inx}$) összegére. Emiatt a szinusz **alapjel** jelanalízisben és jelfeldolgozásban.

---

## 6) Szinusz-tétel – kétértelmű eset (SSA)
Ha adott egy oldal és két szög közül az egyik nem a közbezárt (SSA), akkor lehet **két lehetséges háromszög**.  
Legyen $\displaystyle \frac{a}{\sin\alpha}=\frac{b}{\sin\beta}$ adott $a,\alpha,b$ értékekkel.
- Ha $\displaystyle \frac{b\sin\alpha}{a} > 1$ → nincs megoldás.  
- Ha $\displaystyle \frac{b\sin\alpha}{a} = 1$ → egyetlen megoldás (derékszögű eset).  
- Ha $\displaystyle 0 < \frac{b\sin\alpha}{a} < 1$ → két lehetséges $\beta$:  
  $\displaystyle \beta_1=\arcsin\!\left(\frac{b\sin\alpha}{a}\right)$ és $\beta_2=\pi-\beta_1$.

---

## 7) Inverz függvény deriváltja
$$
\frac{d}{dx}\arcsin x = \frac{1}{\sqrt{1-x^2}}, \qquad x\in(-1,1)
$$
**Következmény:** $\arcsin x$ növekvő, konvex $[0,1)$-on és konkáv $(-1,0]$-on.

---

## 8) Gyors összefoglaló képletek
- Periódus: $\sin(x+2\pi)=\sin x$  
- Páratlan: $\sin(-x)=-\sin x$  
- Pitagorasz: $\sin^2x+\cos^2x=1$  
- Kettős szög: $\sin(2x)=2\sin x\cos x$  
- Félszög: $\displaystyle \sin^2\frac{x}{2}=\frac{1-\cos x}{2}$
