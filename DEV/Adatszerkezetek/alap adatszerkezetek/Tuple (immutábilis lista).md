# Tuple (immutábilis lista)

A tuple egy **sorrendezett, nem módosítható** (immutábilis) adatszerkezet.

---

## 🧱 Tulajdonságok

- Fix méretű, nem lehet módosítani
- Indexelhető
- Gyorsabb, mint lista

---

## 🛠️ Használat

```python
t = (1, 2, 3)
print(t[0])  # 1

# Tuple kibontás
a, b, c = t
```

---

## 🔄 Műveletek

```python
len(t)
t.index(2)
t.count(3)
```

---

## 📌 Mikor használd?

- Ha nem akarod, hogy az adat módosuljon
- Ha kulcsként akarod használni szótárban
- Ha adatstruktúrák eleme fix (pl. koordinátapár)
