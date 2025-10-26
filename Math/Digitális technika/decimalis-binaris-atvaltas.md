# Decimális ↔ Bináris átváltás a ℕ, ℤ, ℚ halmazokon

Ez a jegyzet a **decimális és bináris** számrendszer közötti átváltást mutatja be, külön a természetes (ℕ), egész (ℤ) és racionális (ℚ) számokra.

Lásd még: [[binaris-osszeadas]] · [[binaris-kivonas]]

---

## ℕ – Természetes számok (0, 1, 2, 3, ...)

**Módszer:** folyamatos osztás 2-vel, a maradékok visszafelé olvasva adják a bináris számot.

Példa:
```
19 / 2 = 9  r1
9  / 2 = 4  r1
4  / 2 = 2  r0
2  / 2 = 1  r0
1  / 2 = 0  r1
```
→ **19₁₀ = 10011₂**

---

## ℤ – Egész számok (..., -3, -2, -1, 0, 1, ...)

A negatív számokat **kétkomplementes** formában ábrázoljuk.

Példa (8 biten):  
`-5₁₀`  
1. `5₁₀ = 00000101₂`  
2. Inverz → `11111010₂`  
3. +1 → `11111011₂`  
→ **-5₁₀ = 11111011₂**

---

## ℚ – Racionális számok (törtek)

A tört részt **szorzással 2-vel** konvertáljuk:
- a kapott egészrész lesz a következő bit,  
- a maradékot tovább szorozzuk 2-vel.

Példa:  
`0.625₁₀`  
```
0.625 × 2 = 1.25 → 1
0.25 × 2  = 0.5  → 0
0.5 × 2   = 1.0  → 1
```
→ **0.625₁₀ = 0.101₂**

---

## Ismétlődő törtek

Nem minden tizedes tört fejezhető ki pontosan binárisan.  
Példa:  
`0.1₁₀ = 0.0001100110011...₂` (végtelen ismétlődés)

---

## Összefoglaló táblázat

| Halmaz | Példa decimális | Bináris alak | Megjegyzés |
|--------|-----------------|---------------|-------------|
| ℕ | 13 | 1101 | természetes szám |
| ℤ | -13 | 11110011 (8 bit) | kétkomplementes |
| ℚ | 5.25 | 101.01 | 5 + 1/4 = 5.25 |

---

## Gyakorló feladatok

1. Váltsd át 37₁₀ → bináris  
2. Váltsd át -12₁₀ → bináris (8 bit)  
3. Váltsd át 0.75₁₀ → bináris  
