[[math]], [[Vektorok – Áttekintő (haladó fogalmak)]], #vektorok, #matek

---

## 1) Lineáris függetlenség
A vektorok **lineárisan függetlenek**, ha egyik sem állítható elő a többiek lineáris kombinációjaként.  
Ha mégis előállítható, akkor **lineárisan függők**.

**Formális definíció:**
$$
\alpha_1 v_1 + \alpha_2 v_2 + \dots + \alpha_n v_n = 0
$$
csak akkor teljesül, ha minden $\alpha_i = 0$, akkor a vektorok lineárisan függetlenek.

**Példa:**
- $(1,0)$ és $(0,1)$ függetlenek $\mathbb{R}^2$-ben.  
- $(2,4)$ és $(1,2)$ függők, mert $(2,4) = 2 \cdot (1,2)$.

---

## 2) Bázis és dimenzió
- **Bázis**: olyan vektorrendszer, amely lineárisan független, és **kifeszíti a teret**.  
- **Dimenzió**: a bázis vektorainak száma.

**Példa:**
- $\mathbb{R}^2$ bázisa lehet: $((1,0),(0,1))$. Dimenzió: 2.  
- $\mathbb{R}^3$ bázisa lehet: $((1,0,0),(0,1,0),(0,0,1))$. Dimenzió: 3.

---

## 3) Ortogonalitás
Két vektor **merőleges** (ortogonális), ha a skaláris szorzatuk 0:
$$
\vec{u}\cdot \vec{v} = 0
$$

**Példa:**
$$
(1,2)\cdot (2,-1) = 1\cdot 2 + 2\cdot (-1) = 2-2=0
$$
Tehát merőlegesek.

---

## 4) Ortonormált bázis
- **Ortogonális bázis**: bázis, amelynek vektorai páronként merőlegesek.  
- **Ortonormált bázis**: olyan ortogonális bázis, ahol minden vektor hossza 1.

**Példa:**
- $\mathbb{R}^2$-ben: $((1,0),(0,1))$ ortonormált bázis.  
- $\mathbb{R}^3$-ban: $((1,0,0),(0,1,0),(0,0,1))$ ortonormált bázis.

---

## 5) Gram–Schmidt eljárás
Cél: egy lineárisan független vektorrendszerből **ortogonális (vagy ortonormált) bázist** készítünk.

**Lépések:**
1. Első vektor: $v_1 = u_1$  
2. Második vektor: $v_2 = u_2 - \frac{u_2\cdot v_1}{\|v_1\|^2}v_1$  
3. Harmadik vektor: $v_3 = u_3 - \frac{u_3\cdot v_1}{\|v_1\|^2}v_1 - \frac{u_3\cdot v_2}{\|v_2\|^2}v_2$  
… és így tovább.  
4. Ha **ortonormált** bázist akarunk, minden $v_i$-t normálunk:  
$$
e_i = \frac{v_i}{\|v_i\|}
$$

**Példa:**
Legyen:
$$
u_1=(1,1,0),\quad u_2=(1,0,1)
$$

Első lépés:
$$
v_1 = u_1 = (1,1,0)
$$

Második lépés:
$$
v_2 = u_2 - \frac{u_2\cdot v_1}{\|v_1\|^2} v_1
= (1,0,1) - \frac{1\cdot 1+0\cdot 1+1\cdot 0}{1^2+1^2+0^2}(1,1,0)
= (1,0,1) - \tfrac{1}{2}(1,1,0)
= \bigl(\tfrac{1}{2}, -\tfrac{1}{2}, 1\bigr)
$$

Így $(v_1,v_2)$ ortogonális bázis lesz.

---

## 6) Projekció
Egy $\vec{u}$ vektor **vetülete** egy $\vec{v}$ vektorra:
$$
\mathrm{proj}_{\vec{v}}(\vec{u}) = \frac{\vec{u}\cdot \vec{v}}{\|\vec{v}\|^2}\, \vec{v}
$$

**Példa:**
$$
\vec{u}=(3,4),\ \vec{v}=(1,0)
$$

$$
\mathrm{proj}_{\vec{v}}(\vec{u}) = \frac{3\cdot 1 + 4\cdot 0}{1^2+0^2}(1,0) = 3\cdot (1,0) = (3,0)
$$

---

## Megjegyzés
Ez az összefoglaló nem tartalmazza a vektorok **alapműveleteit** (hossz, összeadás, szorzatok), mert azok külön jegyzetekben vannak.  
Ez inkább a **lineáris algebrai, haladóbb fogalmak** áttekintése.
