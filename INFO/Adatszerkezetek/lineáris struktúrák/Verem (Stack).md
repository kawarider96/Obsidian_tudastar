# Verem (Stack)

A verem (stack) egy **LIFO** (Last In First Out) adatszerkezet: az utoljára betett elem kerül először ki.

---

## 🛠️ Műveletek

```python
verem = []

verem.append(1)    # push
verem.append(2)
verem.pop()        # pop → 2
```

---

## 📌 Tipikus alkalmazás

- Visszalépés (pl. undo)
- Kifejezés kiértékelés
- Mélységi keresés (DFS)

---

## 📊 Időkomplexitás

| Művelet   | Komplexitás |
|-----------|-------------|
| push      | O(1) |
| pop       | O(1) |
| top/peek  | O(1) |

---

## ⚠️ Megjegyzés

- Pythonban a `list` használható veremként
- `collections.deque` is használható, hatékonyabb lehet
