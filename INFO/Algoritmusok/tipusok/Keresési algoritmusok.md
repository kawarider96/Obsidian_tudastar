# Keresési algoritmusok

A keresési algoritmusok célja, hogy **megtaláljanak egy adott elemet** egy adatszerkezetben (pl. listában, tömbben, fában).

---

## 🔹 Lineáris keresés (O(n))

Sorban végigmegy minden elemen.

```python
def linear_search(lista, keresett):
    for elem in lista:
        if elem == keresett:
            return True
    return False
```

- Előny: egyszerű, nincs szükség rendezésre
- Hátrány: lassú nagy listáknál

---

## 🔹 Bináris keresés (O(log n))

Csak **rendezett listán** működik! Mindig megfelezi a keresési tartományt.

```python
def binary_search(lista, keresett):
    bal, jobb = 0, len(lista) - 1
    while bal <= jobb:
        kozep = (bal + jobb) // 2
        if lista[kozep] == keresett:
            return True
        elif lista[kozep] < keresett:
            bal = kozep + 1
        else:
            jobb = kozep - 1
    return False
```

- Előny: nagyon gyors nagy adathalmaznál
- Hátrány: csak rendezett listán működik

---

## 🔹 Egyéb keresések (haladóbb témák)

| Algoritmus       | Használati terület         |
|------------------|-----------------------------|
| Hash keresés     | Szótárak, kulcs-érték párok |
| BFS, DFS         | Gráfok bejárása             |
| Trie keresés     | Szavak keresése szótárban   |

---

## 📊 Összefoglalás

| Algoritmus       | Időkomplexitás | Feltétel             |
|------------------|----------------|-----------------------|
| Lineáris keresés | O(n)           | Nem kell rendezés     |
| Bináris keresés  | O(log n)       | Rendezett lista kell  |
| Hash alapú       | O(1) átlagosan | Hash map              |
