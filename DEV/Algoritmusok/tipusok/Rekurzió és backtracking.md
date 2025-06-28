# Rekurzió és backtracking

A **rekurzió** olyan programozási technika, ahol egy függvény önmagát hívja meg.  
A **backtracking** pedig egy próbálkozás-alapú keresési algoritmus, amely lépésenként visszalép, ha zsákutcába jut.

---

## 🔁 Rekurzió

## Alapelv

Minden rekurziónak két része van:

1. **Alapeset** (base case) – mikor álljon le
2. **Rekurzív hívás** – önmaga meghívása kisebb bemenettel

### Példa: faktoriális

```python
def fakt(n):
    if n == 0:
        return 1
    return n * fakt(n - 1)

print(fakt(5))  # 120
```

---

## 🔍 Backtracking

### Példa: összes bináris szám 3 biten

```python
def backtrack(szo):
    if len(szo) == 3:
        print(szo)
        return
    for c in ['0', '1']:
        backtrack(szo + c)

backtrack("")
```

Eredmény:
```
000
001
010
011
100
101
110
111
```

---

## 🧠 Mire használható?

- Permutáció, kombináció generálás
- Sudoku, n-queens, labirintus megoldás
- Minden olyan probléma, ahol **minden lehetőséget ki kell próbálni**

---

## ⚠️ Rekurzió korlátai

- Maximális rekurzív mélység (`RecursionError`)
- Gyakran memóriában drágább, mint iteráció
- De néha sokkal olvashatóbb, egyszerűbb

---

## 💡 Tippek

- Használj **memoizálást** vagy **dinamikus programozást**, ha túl sok az ismétlés
- Gondolkozz rekurzívan: „mi lenne, ha már megoldottam volna egy kisebb problémát?”

