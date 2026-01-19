# Kétvégű sor (Deque)

A deque (double-ended queue) olyan sor, amely **két végén is tud elemeket felvenni és eltávolítani**.

---

## 🛠️ Műveletek

```python
from collections import deque

dq = deque()
dq.append(1)       # jobb oldal
dq.appendleft(0)   # bal oldal

dq.pop()           # jobb oldalról
dq.popleft()       # bal oldalról
```

---

## 📌 Tipikus alkalmazás

- Csúszóablakos maximum/átlag
- Undo-redo rendszerek

---

## 📊 Időkomplexitás

| Művelet         | Komplexitás |
|------------------|-------------|
| append           | O(1) |
| appendleft       | O(1) |
| pop              | O(1) |
| popleft          | O(1) |

---

## 💡 Megjegyzés

- A `deque` a `collections` modulból érhető el
- Hatékonyabb, mint listával trükközni
