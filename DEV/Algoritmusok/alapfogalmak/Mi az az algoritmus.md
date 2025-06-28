# Mi az algoritmus?

Egy **algoritmus** egy jól definiált, véges lépéssorozat, amely egy adott problémát megold.

## 📌 Jellemzői

- **Determinált**: minden lépés egyértelmű
- **Véges**: egy ponton véget ér
- **Bemenettel dolgozik**
- **Kimenetet ad**
- **Hatékony**: optimális esetben erőforrás-takarékos

## 🧠 Példák a való életből

- Recept → bemenet: hozzávalók, lépések → kimenet: kész étel
- GPS útvonaltervező
- Sorrendezés névsor szerint

## 💻 Programozásban

Egy algoritmus leírása történhet:
- Pszeudokóddal
- Valós programnyelven (pl. Python)
- Blokkdiagrammal

## 🔢 Egyszerű példa – maximum keresés

```python
def max_ertek(lista):
    max_elem = lista[0]
    for elem in lista:
        if elem > max_elem:
            max_elem = elem
    return max_elem
```

## 🤔 Mi nem algoritmus?

- Egy végtelen ciklus
- Egy pontatlan vagy végtelen szabályrendszer

## 🧭 Miért fontos?

- Hatékonyság
- Skálázhatóság
- Interjúkban rendszeresen kérik

