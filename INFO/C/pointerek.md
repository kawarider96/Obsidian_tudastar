# 🧠 Jegyzet: Pointerek (mutatók) C nyelvben

## 🔹 Mi az a pointer?

A **pointer (mutató)** egy olyan változó, amely egy másik változó
**memóriacímét** tárolja.

### Példa:

``` c
int szam = 10;
int *ptr = &szam; // &: a címét adja vissza
```

Itt: - `ptr` egy mutató (`int *`), ami `szam` címét tartalmazza. -
`*ptr` → a cím **értékét** adja vissza (tehát 10).

------------------------------------------------------------------------

## 🔹 Különbség a `&` és `*` között

  Szimbólum   Jelentés
  ----------- -------------------------------------------------------
  `&`         Egy változó **memóriacímét** adja vissza
  `*`         Egy mutató által mutatott cím **értékét** adja vissza

### Példa:

``` c
#include <stdio.h>

int main() {
    int szam = 42;
    int *mutato = &szam;

    printf("A szam erteke: %d\n", szam);
    printf("A szam cime: %p\n", &szam);
    printf("A mutato erteke (cim): %p\n", mutato);
    printf("A mutato altal mutatott ertek: %d\n", *mutato);
    return 0;
}
```

------------------------------------------------------------------------

## 🔹 Miért fontosak a pointerek?

1.  **Dinamikus memória kezeléshez** (malloc, calloc, free).
2.  **Függvények paraméterátadásánál** -- ha egy függvényben módosítani
    akarjuk a változót, cím szerint kell átadni.
3.  **Tömbök kezelésekor** -- a tömb neve is pointer az első elemre.
4.  **Hatékony programozás** -- elkerüljük a felesleges másolásokat.

------------------------------------------------------------------------

### 📘 Példa: függvény, ami pointerrel módosít értéket

``` c
#include <stdio.h>

void novel(int *p) {
    *p = *p + 1;
}

int main() {
    int szam = 5;
    novel(&szam);
    printf("Uj ertek: %d\n", szam);
    return 0;
}
```

💡 A `novel(&szam)` a `szam` címét adja át, így a függvényben
ténylegesen a változó értéke változik.

------------------------------------------------------------------------

## 🔹 Összefoglaló táblázat

  Fogalom           Jelentés                    Példa
  ----------------- --------------------------- -----------------------
  Változó           értéket tárol               `int x = 5;`
  Pointer           címre mutat                 `int *p = &x;`
  Dereferálás       a címről az érték elérése   `*p`
  Cím lekérdezése   a változó címe              `&x`
  Dinamikus tömb    futásidőben méretezhető     `malloc()` + `free()`
