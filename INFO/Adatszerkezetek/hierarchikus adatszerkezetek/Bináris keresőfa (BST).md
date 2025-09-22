# Bináris keresőfa (BST)

Olyan bináris fa, amelyben:
- minden bal oldali gyerek kisebb, mint a szülő,
- minden jobb oldali gyerek nagyobb, mint a szülő.

---

## 🧱 Példa struktúra

```
       8
      / \
     3   10
    / \    \
   1   6    14
```

---

## 🛠️ Alapműveletek

```python
class Csucs:
    def __init__(self, ertek):
        self.ertek = ertek
        self.bal = None
        self.jobb = None

def beszur(gyoker, ertek):
    if not gyoker:
        return Csucs(ertek)
    if ertek < gyoker.ertek:
        gyoker.bal = beszur(gyoker.bal, ertek)
    else:
        gyoker.jobb = beszur(gyoker.jobb, ertek)
    return gyoker
```

---

## 📌 Tipikus felhasználás

- Rendezett adatok tárolása
- Hatékony keresés (O(log n)) kiegyensúlyozott fában

## ⚠️ Figyelem

- Ha nem kiegyensúlyozott → lehet O(n)
