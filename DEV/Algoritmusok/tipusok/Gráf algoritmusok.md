# Gráf algoritmusok

A gráf egy olyan adatszerkezet, ahol csúcsok (node) és élek (edge) kapcsolódnak egymáshoz.

---

## 🌐 Alapfogalmak

- **Irányított / irányítatlan gráf**
- **Súlyozott él**: az élekhez érték (költség) tartozik
- **Szomszédsági lista**: Pythonban `dict[list]` formában

---

## 🔎 Gráf bejárások

### 🔁 DFS – Mélységi bejárás (Depth-First Search)

```python
def dfs(graf, csucs, latogatott=None):
    if latogatott is None:
        latogatott = set()
    latogatott.add(csucs)
    print(csucs)
    for szomszed in graf[csucs]:
        if szomszed not in latogatott:
            dfs(graf, szomszed, latogatott)
```

- Rekurzív
- Stack-alapú
- Lehet ciklikus

---

### 🔁 BFS – Szélességi bejárás (Breadth-First Search)

```python
from collections import deque

def bfs(graf, kezdo):
    latogatott = set([kezdo])
    sor = deque([kezdo])
    while sor:
        cs = sor.popleft()
        print(cs)
        for sz in graf[cs]:
            if sz not in latogatott:
                latogatott.add(sz)
                sor.append(sz)
```

- Queue-alapú
- Legkevesebb lépéses út keresésére jó

---

## 📦 Útvonal- és súlyozott algoritmusok

### Dijkstra – Legkisebb súlyú út (O(E + V log V))

```python
import heapq

def dijkstra(graf, start):
    tav = {cs: float("inf") for cs in graf}
    tav[start] = 0
    q = [(0, start)]
    while q:
        akt_tav, akt_cs = heapq.heappop(q)
        for sz, suly in graf[akt_cs]:
            uj_tav = akt_tav + suly
            if uj_tav < tav[sz]:
                tav[sz] = uj_tav
                heapq.heappush(q, (uj_tav, sz))
    return tav
```

- Nem működik negatív súlyokra

---

## 🧠 Mire használható?

- Útvonaltervezés (pl. térkép)
- Kapcsolatok keresése (pl. közösségi hálók)
- Minimális feszítőfa (Kruskal, Prim)
- Kördetektálás, topologikus rendezés

---

## 💡 Tipp

Gráfokat reprezentálhatsz:
- Szomszédsági listával: `{A: [B, C]}`
- Szomszédsági mátrixszal: 2D tömb (ritkán praktikus nagy gráfokra)

