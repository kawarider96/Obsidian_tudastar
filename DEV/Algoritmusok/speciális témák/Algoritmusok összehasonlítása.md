# Algoritmusok összehasonlítása

Az algoritmusok összehasonlítása segít kiválasztani a megfelelő megoldást adott probléma és körülmények alapján.

---

## ⚖️ Összehasonlítási szempontok

| Szempont        | Jelentés |
|------------------|----------|
| Időkomplexitás   | Mennyi időbe telik lefutni (Big O) |
| Térkomplexitás   | Mennyi memóriát igényel |
| Stabilitás       | Megőrzi-e az elemek sorrendjét (pl. rendezésnél) |
| Rekurzió szükséges? | Használ-e rekurziót |
| Egyszerűség      | Mennyire könnyen implementálható |
| Valós környezet | Mennyire működik jól gyakorlatban is |

---

## 📊 Rendezési algoritmusok

| Algoritmus     | Időkomplexitás | Stabil? | In-place? | Megjegyzés                 |
|----------------|----------------|---------|-----------|----------------------------|
| Bubble Sort    | O(n²)          | ✅      | ✅        | Lassú, oktatási célra ok   |
| Insertion Sort | O(n²)          | ✅      | ✅        | Kis listáknál gyors        |
| Merge Sort     | O(n log n)     | ✅      | ❌        | Hatékony, de memóriaigényes |
| Quick Sort     | O(n log n)     | ❌      | ✅        | Átlagosan gyors, nem stabil |

---

## 🔍 Keresési algoritmusok

| Algoritmus      | Időkomplexitás | Feltétel                |
|-----------------|----------------|--------------------------|
| Lineáris keresés| O(n)           | Nem rendezett lista      |
| Bináris keresés | O(log n)       | Csak rendezett listán    |
| Hash keresés    | O(1) (átlagosan) | Kulcs-alapú, nem sorrendfüggő |

---

## 🧠 Mikor mit válassz?

| Szituáció                          | Algoritmus                   |
|------------------------------------|------------------------------|
| Gyors keresés rendezett listán     | Bináris keresés              |
| Kis adathalmaz, egyszerű rendezés  | Insertion Sort               |
| Nagy adathalmaz, stabilitás fontos | Merge Sort                   |
| Gyors, átlagos rendezés            | Quick Sort                   |
| Optimum részproblémákból épül fel  | Dinamikus programozás        |
| Lokális döntés → jó globálisan     | Greedy                       |
| Probléma jól darabolható           | Divide and Conquer           |
| Kombinatórikus probléma            | Backtracking / DFS           |

---

## 💬 Tipp

Nincs „legjobb” algoritmus – mindig a probléma jellege, az adatok mérete és a cél határozza meg, melyik a megfelelő!

