# Gráf (Graph)

A gráf egy adatszerkezet, amely csúcsokat (node) és közöttük húzódó éleket (edge) tárol.

---

## 📌 Típusok

- Irányított vs. irányítatlan
- Súlyozott vs. súly nélküli
- Ciklikus vs. aciklikus

---

## 🛠️ Reprezentáció

### Szomszédsági lista

```python
graf = {
    'A': ['B', 'C'],
    'B': ['C'],
    'C': ['A'],
    'D': ['C']
}
```

### Szomszédsági mátrix

```python
matrix = [
    [0, 1, 1, 0],
    [0, 0, 1, 0],
    [1, 0, 0, 0],
    [0, 0, 1, 0]
]
```

---

## 🔁 Alap algoritmusok

- DFS, BFS
- Dijkstra, Bellman-Ford
- Topologikus rendezés
- Cikluskeresés

---

## 📌 Használat

- Hálózatok (pl. net, közlekedés)
- Kapcsolati modellek (pl. közösségi hálók)
- Függőségek kezelése (pl. build rendszer)
