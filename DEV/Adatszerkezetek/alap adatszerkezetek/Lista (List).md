# Lista (List)

A lista egy **sorrendezett, módosítható** adatszerkezet, amelyben elemek indexelhetők és duplikálhatók.

---

## 🧱 Tulajdonságok

- Indexelt: minden elemnek van pozíciója
- Változtatható (mutable)
- Lehetnek benne duplikált értékek
- Dinamikusan méretezhető

---

## 🛠️ Létrehozás és műveletek

```python
# Lista létrehozása
lista = [1, 2, 3]

# Elem elérése
print(lista[0])  # 1

# Hozzáadás
lista.append(4)

# Beszúrás adott helyre
lista.insert(1, 99)

# Törlés
lista.remove(2)       # első előfordulást
del lista[0]          # index alapján

# Iterálás
for elem in lista:
    print(elem)
```

---

## 🔄 Hasznos metódusok

```python
lista.sort()        # rendezés
lista.reverse()     # megfordítás
lista.count(3)      # előfordulások száma
lista.index(99)     # első előfordulás indexe
```

---

## 📊 Időkomplexitás

| Művelet             | Komplexitás |
|----------------------|-------------|
| Indexelés (`l[i]`)   | O(1)        |
| Beszúrás/törlés elején | O(n)      |
| Hozzáadás a végére   | O(1) amortizált |
| Keresés, `in`        | O(n)        |

---

## 📌 Mikor használd?

- Ha **sorrend** számít
- Ha gyakran kell hozzáadni a végére
- Ha indexek alapján kell dolgozni

---

## ⚠️ Mire figyelj?

- Beszúrás/törlés a közepén vagy elején lassabb lehet
- Ha nem fontos a sorrend, lehet hogy Set vagy Dict jobb választás

