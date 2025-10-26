[[math]], #szinusz, #matek
## 1) Alapfogalom derékszögű háromszögben
$$
\sin \alpha = \frac{\text{szöggel szemben lévő befogó}}{\text{átfogó}}
$$

- **Átfogó**: a derékszöggel szembeni, leghosszabb oldal (nem attól függ, melyik szöget választod!).  
- **Szemben lévő befogó**: a kiválasztott szöggel szembeni befogó.  
- **Melletti befogó**: a kiválasztott szög mellett lévő befogó.  

![[szinusz_abra.png]]

---

## 2) Egységkörös értelmezés (áttekintés)
Az egységkörön (sugár = 1) a szögnek megfelelő pont **y-koordinátája** maga a szinusz:
$$
\sin \alpha = y
$$

---

## 3) Szinusz-tétel (bármely háromszögre)
$$
\frac{a}{\sin \alpha} = \frac{b}{\sin \beta} = \frac{c}{\sin \gamma}
$$

Ezzel ismeretlen oldalt vagy szöget tudsz számítani, ha van elég ismert adat.  

![[szinusz_minta.png]]

---

## 4) Háromszög területe szinusszal
Két oldal és a közbezárt szög esetén:
$$
T = \tfrac{1}{2}ab\sin \gamma = \tfrac{1}{2}bc\sin \alpha = \tfrac{1}{2}ac\sin \beta
$$

---

## 5) Példa
Adott az átfogó: 3740 m, és egy hegyesszög: $(31^\circ)$. Keressük a szöggel szemben lévő befogót $(X)$.

$$
\sin 31^\circ = \frac{X}{3740}
\quad\Rightarrow\quad
X = 3740\,\sin 31^\circ
$$

Számológéppel (fokban):  
$(\sin 31^\circ \approx 0{.}515)$, így  
$$
X \approx 3740 \cdot 0{.}515 \approx 1926{.}1\ \text{m}
$$

---

## 6) Gyors emlékeztető
- $(\sin(-x) = -\sin x)$ (páratlan függvény)  Mit jelent a páratlan függvény? Ha szög mínusz akkor a szinusszal kiszámolt tört érték is is mínusz lessz. $sin(30^\circ) = -sin(30^\circ)$
- Értékkészlet: $([-1, 1])$  a szinusz által kiszámolt tört mindig 1 és -1 közt lesz bármekkora szöget is adunk meg.  
- Periódus: $(2\pi)$ (azaz $360°$) bizonyos időközönként ismétlődik, azaz bármilyen szöghöz hozzáadok $2\pi$-t ami $360^\circ$ akkor a szinusz értéke nem változik $sin(30^\circ)=0,5$ és $sin(30^\circ + 360^\circ) = sin(390^\circ) = 0,5$
