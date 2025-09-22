# Kiegyensúlyozott fák (AVL, Red-Black)

Ezek a fák automatikusan **kiegyensúlyozzák** magukat beszúrás és törlés során, hogy a mélység logaritmikus maradjon.

---

## 🔹 AVL fa

- Minden csúcsnál: |bal magasság - jobb magasság| ≤ 1
- Magasságot tárol minden csúcson
- Forgatásokat végez beszúrásnál/törlésnél

---

## 🔹 Red-Black fa

- Bináris keresőfa, de színezett csúcsokkal (piros/fekete)
- Szabályok biztosítják az egyensúlyt:
  - Gyökér mindig fekete
  - Két piros nem lehet egymás mellett
  - Minden úton ugyanannyi fekete

---

## 📊 Összehasonlítás

| Tulajdonság     | AVL           | Red-Black     |
|------------------|---------------|----------------|
| Gyorsabb keresés | ✅             | ❌ (ritkán)     |
| Gyorsabb beszúrás| ❌             | ✅             |
| Használat        | memóriaindex  | Java TreeMap / Linux kernel |

---

## 🧠 Mikor használd?

- AVL: ha sok keresés van
- Red-Black: ha sok beszúrás/törlés van, és kisebb a keresési igény
