# Heap (Prioritási sor)

A heap egy bináris fa alapú adatszerkezet, amelyben minden szülő kisebb/nagyobb, mint a gyermekei. Prioritási sor implementációjára szolgál.

---

## 🔹 Típusok

- Min-heap: a legkisebb érték van legfelül
- Max-heap: a legnagyobb érték van legfelül

---

## 🛠️ Használat Pythonban

```python
import heapq

lista = [3, 1, 4, 2]
heapq.heapify(lista)

heapq.heappush(lista, 0)
legkisebb = heapq.heappop(lista)
```

---

## 📌 Tipikus alkalmazás

- Dijkstra algoritmus
- Ütemezők
- Top-K legnagyobb/legkisebb érték keresése

---

## 📊 Komplexitás

| Művelet     | Időkomplexitás |
|-------------|----------------|
| beszúrás    | O(log n)       |
| kivétel     | O(log n)       |
| minimum     | O(1)           |
