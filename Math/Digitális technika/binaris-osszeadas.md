# Bináris összeadás

Ez a jegyzet a fixpontos (egész) **bináris összeadás** működését mutatja be.

Lásd még: [[binaris-kivonas]] · [[decimalis-binaris-atvaltas]]

---

## Alapelve

A bináris összeadás az **egyes helyi értékek összeadásán** alapul, akárcsak a tízes számrendszerben, csak itt a lehetséges számjegyek `0` és `1`.

| Összeadás | Eredmény | Átvitel |
|------------|-----------|----------|
| 0 + 0 | 0 | 0 |
| 0 + 1 | 1 | 0 |
| 1 + 0 | 1 | 0 |
| 1 + 1 | 0 | 1 ← átvitel a következő bitre |

---

## Példa (4 bites)

```
   0110   (6)
+  0011   (3)
────────────
   1001   (9)
```

Átvitel lépései:  
- 0+1=1  
- 1+1=0, átvitel=1  
- 1+0+1(átvitel)=0, átvitel=1  
- 0+0+1(átvitel)=1  

---

## Túlcsordulás (Overflow)

Ha az **összeg átvitele túllépi a legnagyobb helyi értéket**, túlcsordulás lép fel.

Példa 4 biten:
```
  1100  (12)
+ 1010  (10)
────────────
1 0110  (a legfelső 1 elveszik → eredmény: 6, overflow)
```

---

## Kétkomplementes előjeles összeadás

Ha **előjeles** számokat tárolunk (kétkomplementes formában), ugyanígy történik az összeadás, de az előjelbit értelmezése más:

```
  1110  (-2)
+ 0011  (3)
────────────
  0001  (1)
```

→ A helyes eredmény: **-2 + 3 = 1** ✅

---

## Gyakorló feladatok

1. Add össze: `1011₂ + 0110₂`  
2. Add össze: `1101₂ + 0011₂`  
3. Mi történik, ha 4 biten `1111 + 0001`?
