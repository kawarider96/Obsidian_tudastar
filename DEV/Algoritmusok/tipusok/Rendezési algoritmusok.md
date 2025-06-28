# Rendezési algoritmusok

A rendezési algoritmusok célja, hogy egy adathalmazt **növekvő vagy csökkenő sorrendbe** állítsanak.

---

## 🔹 Bubble Sort (O(n²))

Az elemeket ismételten összehasonlítja és cseréli, ha rossz sorrendben vannak.

```python
def bubble_sort(lista):
    n = len(lista)
    for i in range(n):
        for j in range(0, n-i-1):
            if lista[j] > lista[j+1]:
                lista[j], lista[j+1] = lista[j+1], lista[j]
```

- Egyszerű, de lassú nagy adathalmaznál

---

## 🔹 Insertion Sort (O(n²))

Az elemeket **egyesével helyére illeszti**.

```python
def insertion_sort(lista):
    for i in range(1, len(lista)):
        kulcs = lista[i]
        j = i - 1
        while j >= 0 and kulcs < lista[j]:
            lista[j + 1] = lista[j]
            j -= 1
        lista[j + 1] = kulcs
```

- Jó teljesítmény **majdnem rendezett** listákra

---

## 🔹 Merge Sort (O(n log n))

A listát **felezéssel** rendezi: bal-jobb oldal rekurzívan → összefűzés.

```python
def merge_sort(lista):
    if len(lista) > 1:
        kozep = len(lista) // 2
        bal = lista[:kozep]
        jobb = lista[kozep:]

        merge_sort(bal)
        merge_sort(jobb)

        i = j = k = 0
        while i < len(bal) and j < len(jobb):
            if bal[i] < jobb[j]:
                lista[k] = bal[i]
                i += 1
            else:
                lista[k] = jobb[j]
                j += 1
            k += 1

        while i < len(bal):
            lista[k] = bal[i]
            i += 1
            k += 1
        while j < len(jobb):
            lista[k] = jobb[j]
            j += 1
            k += 1
```

- Stabil, megbízható, de extra memória kell

---

## 🔹 Quick Sort (átlag O(n log n), legrosszabb O(n²))

Pivotelem köré rendezi a listát → rekurzív rendezés.

```python
def quick_sort(lista):
    if len(lista) <= 1:
        return lista
    pivot = lista[0]
    kisebb = [x for x in lista[1:] if x <= pivot]
    nagyobb = [x for x in lista[1:] if x > pivot]
    return quick_sort(kisebb) + [pivot] + quick_sort(nagyobb)
```

- Gyors, de nem stabil
- In-place verziók is léteznek

---

## 📊 Összefoglalás

| Algoritmus     | Időkomplexitás | Stabil? | Extra memória |
|----------------|----------------|---------|----------------|
| Bubble Sort    | O(n²)          | Igen    | Nem            |
| Insertion Sort | O(n²)          | Igen    | Nem            |
| Merge Sort     | O(n log n)     | Igen    | Igen           |
| Quick Sort     | O(n log n) átlag / O(n²) legrosszabb | Nem | Nem (in-place) |

---

## 💡 Tipp

- Ha **gyorsaság** kell: Quick Sort  
- Ha **stabilitás és kiszámíthatóság**: Merge Sort  
- Kis adathalmazokra: Insertion Sort

