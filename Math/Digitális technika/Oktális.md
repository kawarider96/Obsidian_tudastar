[[math]], #matek, #bináris, #oktális, #decimális, #hexadecmális, #számrendszer
# Oktális számrendszer (8-as)

Alapja: **8**  
Számjegyek: `0–7`

---

## Gyors jegyzetek
- 1 oktális jegy = **3 bit** → gyors bináris konverzió.  
- Tört átváltásnál: szorzás **8-cal** (és az egész rész a következő jegy).

---

## Oktálisból decimálisba

**Szabály:** `Σ (jegy · 8^k)` az egész részre; a törtrészre `Σ (jegy · 8^-k)`.

**Példa:** `365.565605₈`
```text
Egész rész: 3·8^2 + 6·8^1 + 5·8^0 = 3·64 + 6·8 + 5 = 192 + 48 + 5 = 245
Törtrész:  .565605₈ = 5·8^-1 + 6·8^-2 + 5·8^-3 + 6·8^-4 + 0·8^-5 + 5·8^-6
≈ 0.625 + 0.09375 + 0.009765625 + 0.00146484375 + 0 + 0.00007629395
≈ 0.73
```
**Eredmény (közelítő):** `365.565605₈ ≈ 245.73₁₀`

---

## Oktálisból binárisba

**Szabály:** Minden oktális jegy → **3 bit**. Törtrésznél is 3 bit/jegy.

**Példa:** `365.5656₈`
```text
3   6   5   .   5    6    5    6
011 110 101     101 110 101 110
→ 011110101.101110101110₂
```
**Eredmény:** `365.5656₈ = 011110101.101110101110₂`

> Vezető nullák az egész rész elején nem számítanak (pl. `011110101₂ = 11110101₂`).

---

## Oktálisból hexadecimálisba (oktális → bináris → hex)

**Szabály:**  
1. Oktális → bináris (3 bit/jegy).  
2. Bináris → hex **4 bites csoportokkal**. Balra/jobbra pótold 0‑val, hogy a 4-es csoportok kijöjjenek.

**Példa:** `365.565605₈`
```text
365₈ → 011110101₂ → (balról pótolva) 0011 1101 01 → 0001 1110 101 → 1  E  5 → 1E5₁₆  (illusztratív csoportosítás)
Valós konverzió: 365₈ = 11110101₂ = F5₁₆
Törtrész: .565605₈ → .101 110 101 110 000 101 → .101110101110000101₂
→ 4-es csoportok: .1011 1010 1110 0001 0100 → .B A E 1 4 → .BAE14₁₆
```
**Eredmény (közelítő):** `365.565605₈ ≈ F5.BAE14₁₆`

---

## Tört átváltás oktálisból (általános)

**Oktális törtrész → decimális:** `Σ (jegy · 8^-k)`  
**Oktális törtrész → bináris:** 3 bit/jegy jobbra.  
**Oktális törtrész → hex:** előbb binárisra, majd 4-es csoportok.
