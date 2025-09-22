# Greedy algoritmusok

A **greedy (mohó) algoritmusok** mindig a pillanatnyi legjobb (lokálisan optimális) döntést hozzák meg abban a reményben, hogy a végén is jó (globálisan optimális) eredményt kapunk.

---

## 📌 Jellemzők

- Lokális optimumra épít
- Nincs visszalépés (nem vizsgál újra korábbi döntéseket)
- Gyors és egyszerű implementáció

---

## 🧠 Mikor működik jól?

- Ha a probléma **greedy-kompatibilis** (matematikailag bizonyítható, hogy a lokális optimum → globális optimum)
- Példa: pénzérmék váltása, ha a címletek jól viselkednek

---

## 🔸 Példa: pénzérmék váltása (coin change)

```python
def greedy_coin_change(cimletek, osszeg):
    cimletek.sort(reverse=True)
    eredmeny = []
    for erme in cimletek:
        while osszeg >= erme:
            osszeg -= erme
            eredmeny.append(erme)
    return eredmeny

print(greedy_coin_change([100, 50, 20, 10, 5, 1], 87))
# → [50, 20, 10, 5, 1, 1]
```

---

## 🧠 Más klasszikus greedy problémák

| Probléma                    | Rövid leírás                           |
|-----------------------------|----------------------------------------|
| Activity Selection          | Legtöbb nem ütköző intervallum kiválasztása |
| Huffman kódolás             | Karakterek tömörítése súly alapján     |
| Kruskal / Prim algoritmus  | Minimális feszítőfa keresés (gráfokban) |
| Fractional Knapsack         | Szakaszolható hátizsák probléma        |

---

## 📊 Összehasonlítás DP-vel

| Típus        | Módszer       | Eredmény                      |
|--------------|----------------|-------------------------------|
| DP           | Minden lehetőség → optimális | Biztos optimális |
| Greedy       | Lokális optimum alapján     | Csak ha igazolható |

---

## ⚠️ Figyelem

- Nem mindig ad helyes/optimális megoldást!
- Mindig **vizsgáld meg**, hogy a probléma valóban alkalmas-e greedy megoldásra.

