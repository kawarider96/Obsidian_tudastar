# Adatszerkezetek összehasonlítása

Ez a táblázat segít megérteni az egyes adatszerkezetek fő tulajdonságait és jellemző műveleteik időkomplexitását.

---

## 📊 Összehasonlító táblázat

| Szerkezet | Keresés | Beszúrás | Törlés | Megjegyzés |
|-----------|---------|----------|--------|------------|
| Lista     | O(n)    | O(1) végén | O(n)   | Sorrendezett, duplikálható |
| Halmaz    | O(1)    | O(1)      | O(1)   | Nincs duplikátum, nincs sorrend |
| Szótár    | O(1)    | O(1)      | O(1)   | Kulcs-érték tárolás |
| Tuple     | O(1)    | ❌        | ❌     | Immutábilis lista |
| Verem     | O(1)    | O(1) push | O(1) pop | LIFO struktúra |
| Sor       | O(1)    | O(1)      | O(1)   | FIFO struktúra |
| Deque     | O(1)    | O(1)      | O(1)   | Kétirányú működés |
| BST       | O(log n)* | O(log n)* | O(log n)* | Rendezett tárolás, *kiegyensúlyozva |
| Hash tábla | O(1)   | O(1)      | O(1)   | Kulcs alapján gyors |
| Heap      | O(n)    | O(log n)  | O(log n) | Minimum vagy maximum elérés |
| Gráf      | O(n)    | O(1)      | O(1)   | Kapcsolatok modellezése |

