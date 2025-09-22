# Halmaz (Set)

A halmaz egy **nem sorrendezett, egyedi elemeket** tartalmazó adatszerkezet.

---

## 🧱 Tulajdonságok

- Nincs elem sorrend → nem indexelhető
- Nincs duplikáció
- Változtatható (mutable)

---

## 🛠️ Műveletek

```python
s = {1, 2, 3}
s.add(4)
s.remove(2)
print(3 in s)  # True
```

---

## 🔄 Halmazműveletek

```python
a = {1, 2, 3}
b = {3, 4, 5}

a | b      # unió: {1, 2, 3, 4, 5}
a & b      # metszet: {3}
a - b      # különbség: {1, 2}
a ^ b      # szimmetrikus különbség: {1, 2, 4, 5}
```

---

## 📊 Időkomplexitás

| Művelet        | Komplexitás |
|----------------|-------------|
| `in` keresés   | O(1) átlagosan |
| Hozzáadás      | O(1) |
| Törlés         | O(1) |

---

## 📌 Mikor használd?

- Egyediség biztosítására
- Gyors keresésre, összehasonlításra
