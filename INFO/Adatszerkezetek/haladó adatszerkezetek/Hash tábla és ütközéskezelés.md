# Hash tábla és ütközéskezelés

A hash tábla kulcsokat hash függvénnyel indexre alakít, így gyors elérésű asszociatív tároló jön létre.

---

## 🛠️ Alapműködés

```python
d = {}
d["kulcs"] = "érték"
```

A `kulcs` hash-elés után indexként szolgál → gyors elérés

---

## 📌 Ütközéskezelés (collision handling)

### 1. Láncolás (chaining)

Egy indexhez több elem listában

### 2. Nyílt címzés (open addressing)

Másik helyet keres lineárisan, kvadratiksuan vagy dupla hash-el

---

## 📊 Előnyök

- Gyors: `O(1)` hozzáférés és keresés
- Egyszerű használni (Python `dict`)

---

## ⚠️ Figyelem

- Kulcsoknak hash-elhetőnek kell lenniük (pl. tuple igen, lista nem)
- Túl sok ütközésnél lassulhat

---

## 🔄 Használat helye

- Indexelés
- Gyors keresés és lekérdezés
- Frekvencia számlálás
