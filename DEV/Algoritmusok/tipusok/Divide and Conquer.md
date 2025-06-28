# Divide and Conquer

A **Divide and Conquer (Oszd meg és uralkodj)** stratégia lényege, hogy egy problémát kisebb részekre bontunk, azokat megoldjuk, majd az eredményeket összekombináljuk.

---

## 📌 Fő lépések

1. **Felosztás**: a bemenet kisebb részekre bontása
2. **Meghódítás**: rekurzívan megoldjuk a részproblémákat
3. **Összefűzés**: az eredmények összeállítása

---

## 🔁 Klasszikus példák

| Algoritmus     | Leírás                               |
|----------------|--------------------------------------|
| Merge Sort     | Lista felosztása és rendezett összeolvasása |
| Quick Sort     | Pivot köré rendezés, részhalmazokra rekurzió |
| Binary Search  | Keresés felezéssel egy rendezett listában |
| Karatsuba      | Gyors egész szorzás nagy számokra    |
| Strassen       | Mátrixszorzás hatékonyabban          |

---

## 🔸 Merge Sort emlékeztető

```python
def merge_sort(lista):
    if len(lista) <= 1:
        return lista
    mid = len(lista) // 2
    bal = merge_sort(lista[:mid])
    jobb = merge_sort(lista[mid:])
    return merge(bal, jobb)
```

---

## 📊 Előnyök

- Strukturált, skálázható algoritmusok
- Gyakran **logaritmikus mélységű** rekurzióval működik → gyors

## ⚠️ Hátrányok

- Rekurzió miatt extra memóriát igényelhet
- Nehéz lehet összeállítani az eredményt (pl. merge lépés)

---

## 💡 Tipp

Ha a probléma természetesen felosztható → gondolj a Divide & Conquer stratégiára!

