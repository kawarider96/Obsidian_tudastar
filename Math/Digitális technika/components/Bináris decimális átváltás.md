---
title: Bináris decimális átváltás
tags:
  - matek
  - math
  - matematika
  - bináris
  - decimális
  - átváltás
  - számrendszer
  - informatika
status: complete
created: 2026-01-17
---

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

> [!warning] `435,239₁₀` decimális szám binárisban végtelen törtté alakul, a fenti minta a közelítés logikáját mutatja.

A leggyorsabb és egyszerűbb módszer: Mivel tudjuk hogy a bináris jegyek értékei a helyiértékük hatványa azaz:
![[Bináris-_decimális.png]]
---
