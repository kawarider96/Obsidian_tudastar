[[math]], #matek, #bináris, #oktális, #decimális, #hexadecmális, #számrendszer
# Hexadecimális számrendszer (16-os)

Alapja: **16**  
Számjegyek: `0–9`, `A–F` (A=10, B=11, …, F=15)

---

## Gyors jegyzetek
- 1 hex jegy = **4 bit** → gyors bináris konverzió.  
- Hex törtrész → szorozz **16-tal** és vedd az egész részt (ismételd).

---

## Hexából decimálisba

**Szabály:** `Σ (jegy_érték · 16^k)` az egész részre; a törtrészre `Σ (jegy_érték · 16^-k)`.

**Példa:** `F5.BAE14₁₆`
```text
Egész rész:  F5₁₆ = 15·16^1 + 5·16^0 = 240 + 5 = 245
Törtrész:    .BAE14₁₆ = 11·16^-1 + 10·16^-2 + 14·16^-3 + 1·16^-4 + 4·16^-5
≈ 0.6875 + 0.0390625 + 0.00341796875 + 0.00001525879 + 0.00000381470
≈ 0.73
```
**Eredmény (közelítő):** `F5.BAE14₁₆ ≈ 245.73₁₀`

---

## Hexából binárisba

**Szabály:** Minden hex jegyet válts **4 bitre** (A=1010, F=1111, stb.). A törtrésznél is 4 bit/jegy.

**Példa:** `F5.BAE14₁₆`
```text
F   5   .   B    A    E    1    4
1111 0101    1011 1010 1110 0001 0100
→ 11110101.10111010111000010100₂
```
**Eredmény:** `F5.BAE14₁₆ = 11110101.10111010111000010100₂`

---

## Hexából oktálisba (hex → bináris → oktális)

**Szabály:**  
1. Hex → bináris (4 bit/jegy).  
2. Bináris → oktális **3 bites csoportokkal**. Balra/jobbra 0-val egészítsd ki, hogy a csoportok kijöjjenek.

**Példa (egész rész):** `F5₁₆`
```text
F5₁₆ → 11110101₂ → (balról pótolva) 011110101 → 011 110 101 → 3 6 5 → 365₈
```
**Példa (törtrész):** `.BAE14₁₆`
```text
.BAE14₁₆ → .1011 1010 1110 0001 0100₂
→ .101 110 101 110 000 101 000₂ → .5 6 5 6 0 5 0₈
```
**Eredmény (közelítő):** `F5.BAE14₁₆ ≈ 365.565605₈`

---

## Tört átváltás hexből (általános)

**Hex törtrész → decimális:** `Σ (jegy · 16^-k)`  
**Hex törtrész → bináris:** 4 bit/jegy jobbra.  
**Hex törtrész → oktális:** előbb binárisra, majd 3-as csoportok.
