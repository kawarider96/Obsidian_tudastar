[[math]], #matek, #bináris, #oktális, #decimális, #hexadecmális, #számrendszer
# Decimális számrendszer (10-es)

A decimális számrendszer a leggyakrabban használt rendszer, alapja a **10**.  
Számjegyek: 0–9

---

## Segédlet – gyors táblázat (0–15)

> Tipp: a bináris oszlopban 4 biten (4 helyiérték: 8, 4, 2, 1) ábrázolunk.

| Decimális | Bináris | Oktális | Hexadecimális |
| :-------: | :-----: | :-----: | :-----------: |
|     0     |  0000   |    0    |       0       |
|     1     |  0001   |    1    |       1       |
|     2     |  0010   |    2    |       2       |
|     3     |  0011   |    3    |       3       |
|     4     |  0100   |    4    |       4       |
|     5     |  0101   |    5    |       5       |
|     6     |  0110   |    6    |       6       |
|     7     |  0111   |    7    |       7       |
|     8     |  1000   |         |       8       |
|     9     |  1001   |         |       9       |
|    10     |  1010   |         |       A       |
|    11     |  1011   |         |       B       |
|    12     |  1100   |         |       C       |
|    13     |  1101   |         |       D       |
|    14     |  1110   |         |       E       |
|    15     |  1111   |         |       F       |

---

## Átváltások decimálisból

### Decimális → Bináris (egész szám)

**Lépések**
1. Oszd el a számot 2-vel (egész osztás).  
2. Jegyezd fel a **maradékot** (0 vagy 1).  
3. Ismételd az osztást a hányadossal, amíg az 0 nem lesz.  
4. A bináris szám a **maradékok visszafelé olvasva**.

**Példa: 13 → bináris**
```text
13 / 2 = 6, maradék 1
 6 / 2 = 3, maradék 0
 3 / 2 = 1, maradék 1
 1 / 2 = 0, maradék 1
```
**Eredmény:** `13₁₀ = 1101₂`

> Megjegyzés: az utolsó osztásnál a hányados 0 lesz; a maradékokat mindig **hozzáadjuk**, és a végén **visszafelé** olvassuk össze.

---

### Decimális (törtes) → Bináris

**Szabály**  
- Az **egész részt** az előző módszerrel alakítjuk.  
- A **tört részt** *szorzással* számoljuk: szorozd meg 2-vel; az **egész része** lesz a következő bináris jegy; a maradék törtrészt ismét szorozd 2-vel; folytasd a kívánt pontosságig.  
- Sok decimális tört **végtelen** bináris törtté alakul → gyakorlatban 8–12 jegy pontosság elég.

**Példa: 435,239 → bináris**

Egész rész (435):
```text
435 / 2 = 217, maradék 1
217 / 2 = 108, maradék 1
108 / 2 = 54,  maradék 0
 54 / 2 = 27,  maradék 0
 27 / 2 = 13,  maradék 1
 13 / 2 = 6,   maradék 1
  6 / 2 = 3,   maradék 0
  3 / 2 = 1,   maradék 1
  1 / 2 = 0,   maradék 1
```
**Egész rész eredmény:** `435₁₀ = 110110011₂`

Tört rész (0,239):
```text
0,239 × 2 = 0,478 → egész 0
0,478 × 2 = 0,956 → egész 0
0,956 × 2 = 1,912 → egész 1 (maradék 0,912)
0,912 × 2 = 1,824 → egész 1 (maradék 0,824)
0,824 × 2 = 1,648 → egész 1 (maradék 0,648)
0,648 × 2 = 1,296 → egész 1 (maradék 0,296)
0,296 × 2 = 0,592 → egész 0
0,592 × 2 = 1,184 → egész 1 (maradék 0,184)
0,184 × 2 = 0,368 → egész 0
0,368 × 2 = 0,736 → egész 0
0,736 × 2 = 1,472 → egész 1 (maradék 0,472)
0,472 × 2 = 0,944 → egész 0
0,944 × 2 = 1,888 → egész 1 (maradék 0,888)
…
```
**Közelítő tört rész:** `0,239₁₀ ≈ 0,00111100101₂`

**Teljes eredmény:**  
`435,239₁₀ ≈ 110110011,00111100101₂`

---

### Decimális → Hexadecimális (egész szám)

**Lépések**
1. Oszd el a számot **16-tal** (egész osztás).  
2. Jegyezd fel a maradékot (0–9, **A**=10 … **F**=15).  
3. Ismételd a hányadossal, amíg 0.  
4. A maradékokat **visszafelé** olvasd össze.

**Példa: 245 → hex**
```text
245 / 16 = 15, maradék 5
 15 / 16 = 0,  maradék 15 (F)
```
**Eredmény:** `245₁₀ = F5₁₆`

> Tipp a maradék gyors ellenőrzésére: `245 ÷ 16 = 15,3125`; `15 × 16 = 240`; `245 − 240 = 5` → maradék `5` (utolsó jegy).

---

### Decimális (törtes) → Hexadecimális

**Szabály**  
- Egész rész: mint fent.  
- Tört rész: **szorozd 16-tal**; az egész része adja a következő hex jegyet; a maradékkal ismételd a kívánt pontosságig.

**Példa: 245,73 → hex**
Egész rész:
```text
245 / 16 = 15, maradék 5
 15 / 16 = 0,  maradék 15 (F)
→ F5
```
Tört rész:
```text
0,73 × 16 = 11,68 → B, maradék 0,68
0,68 × 16 = 10,88 → A, maradék 0,88
0,88 × 16 = 14,08 → E, maradék 0,08
0,08 × 16 = 1,28  → 1, maradék 0,28
0,28 × 16 = 4,48  → 4, maradék 0,48
…
```
**Teljes eredmény (közelítő):** `245,73₁₀ ≈ F5.BAE14…₁₆`

---

### Decimális → Oktális (egész és törtes)

**Szabály**
- Egész rész: osztás **8-cal**, maradékok visszafelé.  
- Tört rész: **szorozd 8-cal**; az egész rész az első oktális jegy; maradékkal ismételd.

**Példa: 245,73 → oktális**

Egész rész:
```text
245 / 8 = 30, maradék 5
 30 / 8 = 3,  maradék 6
  3 / 8 = 0,  maradék 3
```
**Egész rész eredmény:** `245₁₀ = 365₈`

Tört rész:
```text
0,73 × 8 = 5,84 → 5, maradék 0,84
0,84 × 8 = 6,72 → 6, maradék 0,72
0,72 × 8 = 5,76 → 5, maradék 0,76
0,76 × 8 = 6,08 → 6, maradék 0,08
0,08 × 8 = 0,64 → 0, maradék 0,64
0,64 × 8 = 5,12 → 5, maradék 0,12
…
```
**Teljes eredmény (közelítő):** `245,73₁₀ ≈ 365,565605…₈`

---

## Gyors jegyzetek
- **Végtelen törtek:** tizedesben véges szám sokszor más alapban végtelen törtté válik. Gyakorlatban elég 6–12 jegy pontosság.  
- **Hex ↔ Bináris gyors konverzió:** 1 hex jegy = **4 bit** (pl. `F` = `1111`).  
- **Oktális ↔ Bináris gyors konverzió:** 1 oktális jegy = **3 bit** (pl. `7` = `111`).
