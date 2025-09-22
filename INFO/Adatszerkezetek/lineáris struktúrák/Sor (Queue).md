# Sor (Queue)

A sor (queue) egy **FIFO** (First In First Out) adatszerkezet: az elsőként betett elem jön ki először.

---

## 🛠️ Műveletek

```python
from collections import deque

sor = deque()
sor.append(1)   # enqueue
sor.append(2)
sor.popleft()  # dequeue → 1
```

---

## 📌 Tipikus alkalmazás

- Ütemezés (pl. nyomtatás)
- Szélességi keresés (BFS)

---

## 📊 Időkomplexitás

| Művelet    | Komplexitás |
|------------|-------------|
| enqueue    | O(1) |
| dequeue    | O(1) |

---

## ⚠️ Megjegyzés

- Ne használj `list.pop(0)`-t – lassú (O(n))
- Használj `deque`, ha hatékony FIFO kell
