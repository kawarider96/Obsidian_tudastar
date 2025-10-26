
# 🧠 C nyelv – Dinamikus memóriafoglalás (`malloc`, `calloc`, `realloc`, `free`)

## 🔹 1. A memória két fő területe
| Terület | Kezelés | Példa |
|----------|----------|--------|
| **Stack** | automatikus, függvényhíváskor | `int x = 5;` |
| **Heap** | kézi (malloc/free) | `int *p = malloc(...);` |

- A stack gyors, de kicsi és automatikus.  
- A heap nagy, de **neked kell foglalni és felszabadítani**.

---

## 🔹 2. `malloc()` – memória foglalása

```c
void *malloc(size_t meret);
```
Lefoglal `meret` bájt memóriát, és visszaadja az első bájt címét (`void *`).  
Ha nem sikerül, `NULL`-t ad vissza.

```c
int *tomb = (int *)malloc(5 * sizeof(int));
```
➡️ Lefoglal 5 darab `int` méretű helyet a heapen.

---

## 🔹 3. `calloc()` – foglal és nulláz

```c
void *calloc(size_t elemek_szama, size_t elem_meret);
```
Lefoglal **elemszám × elem_méret** bájt memóriát, és **nullára inicializálja**.

```c
int *tomb = (int *)calloc(5, sizeof(int));
```

| Függvény | Nulláz | Megjegyzés |
|-----------|--------|-------------|
| `malloc` | ❌ nem nulláz | gyorsabb |
| `calloc` | ✅ nulláz | biztonságosabb |

---

## 🔹 4. `realloc()` – újraméretezés

```c
void *realloc(void *ptr, size_t uj_meret);
```
A `ptr` által mutatott memóriát átméretezi.  
Ha kell, új helyre másolja az adatokat.

```c
int *tomb = malloc(3 * sizeof(int));
tomb = realloc(tomb, 6 * sizeof(int));
```

➡️ A régi adatok megmaradnak, csak több helyet kapsz.

---

## 🔹 5. `free()` – memória felszabadítása

```c
void free(void *ptr);
```

Megszünteti a `malloc`/`calloc`/`realloc` által lefoglalt memóriát.

⚠️ Szabályok:
- **Mindig** hívd meg, ha már nincs rá szükség.  
- **Soha** ne hívd kétszer ugyanarra a pointerre!  
- Felszabadítás után a pointer már érvénytelen.

---

## 🔹 6. Példa – kombinált használat

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n;
    printf("Hány elemet szeretnél? ");
    scanf("%d", &n);

    int *tomb = (int *)calloc(n, sizeof(int));

    for (int i = 0; i < n; i++) {
        tomb[i] = i * 10;
    }

    printf("Tömb elemei: ");
    for (int i = 0; i < n; i++) printf("%d ", tomb[i]);

    tomb = (int *)realloc(tomb, (n + 2) * sizeof(int));
    tomb[n] = 999;
    tomb[n + 1] = 1000;

    printf("\nBővített tömb: ");
    for (int i = 0; i < n + 2; i++) printf("%d ", tomb[i]);

    free(tomb);
    return 0;
}
```

---

## 🔹 7. Összefoglalás táblázat

| Függvény | Jelentés | Nulláz | Cél |
|-----------|-----------|--------|------|
| `malloc` | Lefoglal memóriát | ❌ | Új memória |
| `calloc` | Lefoglal + nulláz | ✅ | Tiszta memória |
| `realloc` | Átméretez | ⚙️ | Bővítés / csökkentés |
| `free` | Felszabadít | 🚫 | Memória visszaadása |

---

💡 **Tipp:**  
Használj mindig `sizeof(tipus)`-t, ne fix számot, hogy hordozható legyen a kód.
