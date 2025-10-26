# Bináris kivonás

Ez a jegyzet a fixpontos **bináris kivonást** mutatja be, beleértve a kétkomplementes módszert.

Lásd még: [[binaris-osszeadas]] · [[decimalis-binaris-atvaltas]]

---

## Alaplogika

A bináris kivonás a **kölcsönzés** elvén alapul (mint a tízes rendszerben):

| Kivonás | Eredmény | Kölcsönzés |
|----------|-----------|-------------|
| 0 − 0 | 0 | 0 |
| 1 − 0 | 1 | 0 |
| 1 − 1 | 0 | 0 |
| 0 − 1 | 1 | 1 ← kölcsönzés a következő bitből |

---

## Példa (kölcsönzéssel)

```
   1000   (8)
-  0011   (3)
────────────
   0101   (5)
```

Magyarázat:  
- 0 nem tud 1-et kivonni → kölcsönzünk a következő bitből.  
- A kölcsönzött 1 tízes (itt kettes) helyi értékként jelenik meg: `10₂ = 2₁₀`,  
  így `10 - 1 = 1`.

---

## Kétkomplementes módszer

A kivonás binárisan **összeadásként is elvégezhető**, ha a kivonandót kétkomplementes formában adjuk hozzá:

1. Képzd a kivonandó szám **kétkomplementjét** (invertálás + 1 hozzáadása).  
2. Add hozzá az eredeti számhoz.

### Példa:
```
   0101   (5)
-  0011   (3)
```

1. 3 → 0011  
   Inverz: 1100  
   +1 → 1101  
2. 5 + (−3):
```
   0101
+  1101
────────
   1010
```
→ 4 bites kétkomplement szerint ez **−6** lenne, de ha csak pozitív tartományban dolgozunk, az alsó 4 bit: `0010` → 2 ✅

---

## Gyakorló feladatok

1. `1000₂ − 0101₂ = ?`  
2. `0111₂ − 0011₂ = ?`  
3. `0100₂ − 0110₂` (figyeld meg a negatív eredményt!)
