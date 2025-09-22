# Szótár (Dict / Map)

A szótár kulcs-érték párokat tárol, és gyors hozzáférést biztosít a kulcs alapján.

---

## 🧱 Tulajdonságok

- Rendezett (Python 3.7+)
- Kulcsok egyediek
- Érték bármi lehet

---

## 🛠️ Alapműveletek

```python
d = {"nev": "Krisz", "kor": 27}

print(d["nev"])         # elérés
d["email"] = "a@b.hu"   # új érték
del d["kor"]            # törlés

print("nev" in d)       # kulcs ellenőrzés
```

---

## 🔄 Iterálás

```python
for kulcs in d:
    print(kulcs, d[kulcs])

for k, v in d.items():
    print(k, v)
```

---

## 📊 Időkomplexitás

| Művelet       | Komplexitás |
|---------------|-------------|
| Kulcs elérés  | O(1) átlagosan |
| Hozzáadás     | O(1) |
| Törlés        | O(1) |

---

## 📌 Mikor használd?

- Ha kulcs alapján kell gyors hozzáférés
- Ha egy adott dologhoz kapcsolódó adatokat szeretnél tárolni

