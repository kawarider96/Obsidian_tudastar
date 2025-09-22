[[math]], #matek, #bináris, #oktális, #decimális, #hexadecmális, #számrendszer
# Bináris számrendszer (2-es)

Alapja: **2**  
Számjegyek: `0`, `1`

---

## Gyors jegyzetek
- 1 hex jegy = **4 bit** (nibble).  
- 1 oktális jegy = **3 bit**.  
- Tört átváltásnál: mindig **szorzunk** az alappal (binárisnál 2-vel).

---

## Binárisból decimálisba

**Szabály (helyiértékek):**  
Minden bit súlya `2^k`. Az egész rész balról jobbra `… 2^3, 2^2, 2^1, 2^0`, a törtrész jobbról balra `2^-1, 2^-2, …`.

**Példa:** `110110011.00111100101₂`  
Egész rész kiszámítása:
```text
1·2^8 + 1·2^7 + 0·2^6 + 1·2^5 + 1·2^4 + 0·2^3 + 0·2^2 + 1·2^1 + 1·2^0
= 256 + 128 + 0 + 32 + 16 + 0 + 0 + 2 + 1 = 435
```
Törtrész (példa-jegyek alapján):
```text
0.00111100101₂ = 2^-3 + 2^-4 + 2^-5 + 2^-6 + 2^-9 + 2^-11
≈ 0.23681640625
```
**Eredmény (közelítő):** `110110011.00111100101₂ ≈ 435.23681640625₁₀`

> Megjegyzés: a `435,239₁₀` decimális szám binárisban végtelen törtté alakul, a fenti minta a közelítés logikáját mutatja.

A leggyorsabb és egyszerűbb módszer: Mivel tudjuk hogy a bináris jegyek értékei a helyiértékük hatványa azaz:
![[Bináris-_decimális.png]]
---

## Binárisból hexadecimálisba

**Szabály:** Csoportosíts **4-4 bitet** a tizedesponttól kifelé. Pótold a hiányzó biteket 0-val **balra** (egész rész) és **jobbra** (törtrész). Minden 4 bit → 1 hex jegy.

**Példa:** `110110011.00111100101₂`
```text
Egész rész:   110110011 → 0001 1011 0011 → 0x1 B 3 → 1B3₁₆
Törtrész:       .00111100101 → .0011 1100 1010 → .3 C A → .3CA₁₆
```
**Eredmény (közelítő):** `110110011.00111100101₂ ≈ 1B3.3CA₁₆`

![[Bináris-_hexadecimális.png]]
---

## Binárisból oktálisba

**Szabály:** Csoportosíts **3-3 bitet** a tizedesponttól kifelé. 3 bit → 1 oktális jegy.

**Példa:** `110110011.00111100101₂`
```text
Egész rész:   110110011 → 110 110 011 → 6 6 3 → 663₈
Törtrész:       .00111100101 → .001 111 001 010 → .1 7 1 2 → .1712₈
```
**Eredmény (közelítő):** `110110011.00111100101₂ ≈ 663.1712₈`

![[Bináris-_oktális.png]]
---

## Tört átváltás binárisból (általános)

**Bináris törtrész → más alap**  
1. Bináris → **hex**: jobbra 4-es csoportok, 0‑val **kiegészítve**.  
2. Bináris → **oktális**: jobbra 3-as csoportok, 0‑val **kiegészítve**.  
3. Bináris → **decimális**: `Σ bit·2^-k` (k=1..n).

> Gyakorlatban 8–12 törtjegy pontosság bőven elég a legtöbb feladathoz.
