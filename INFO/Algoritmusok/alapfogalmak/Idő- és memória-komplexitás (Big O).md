# Idő- és memória-komplexitás (Big O)

A Big O jelölés azt mutatja meg, hogy egy algoritmus **mennyi időt vagy memóriát** igényel a bemenet méretének függvényében.

---

## ⏱️ Időkomplexitás

Azt írja le, hogy **hány műveletet** végez az algoritmus egyre nagyobb bemenetnél.

| Jelölés       | Jelentés                         | Példa                         |
|---------------|----------------------------------|-------------------------------|
| `O(1)`        | Konstans idő                     | Hozzáférés listában index alapján |
| `O(log n)`    | Logaritmikus idő                 | Bináris keresés               |
| `O(n)`        | Lineáris idő                     | Lista végignézése             |
| `O(n log n)`  | Hatékony rendezési algoritmusok  | Merge sort, Quick sort        |
| `O(n^2)`      | Négyzetes idő                    | Két egymásba ágyazott ciklus  |
| `O(2^n)`      | Exponenciális idő                | Backtracking, rekurzió        |

---

## 💾 Memóriakomplexitás

Megmutatja, mennyi **plusz memóriát** igényel a művelet a bemenet méretéhez képest.

- Például: ha új listát készítünk a bemenet alapján → `O(n)`
- Ha csak pár változót használunk: `O(1)`

---

## 🧠 Példa: lineáris vs. logaritmikus keresés

```python
# Lineáris keresés: O(n)
def linear_search(lst, target):
    for x in lst:
        if x == target:
            return True
    return False

# Bináris keresés: O(log n)
def binary_search(lst, target):
    left, right = 0, len(lst)-1
    while left <= right:
        mid = (left + right) // 2
        if lst[mid] == target:
            return True
        elif lst[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return False
```

---

## 📊 Összefoglalás

- **Big O** = legrosszabb eset
- Fontos az **interjúkban**, **nagy adathalmazoknál**, **optimalizálásnál**
- Nem csak idő, hanem **memóriahasználat** is számít!

