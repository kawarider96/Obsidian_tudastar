## **1. A `stdin` az inputcsatorna**

Amikor a program elindul, a C futtatókörnyezet automatikusan megnyit három adatfolyamot:

- `stdin` → standard input (alapértelmezés: billentyűzet)
- `stdout` → standard output (képernyő)
- `stderr` → standard error (hibák kiírása)

A `scanf()` konkrétan a `stdin`-t használja, vagyis:

```c
scanf("%d", &x);`
```
ugyanaz, mint:

```c
fscanf(stdin, "%d", &x);`
```

Tehát a `scanf` **valójában csak egy rövidített forma** az `fscanf()`-hoz, ami a `stdin` adatfolyamra hivatkozik.

---
## **2. Mi történik a gép szintjén**

1. Amikor beírsz valamit (pl. `42`), az operációs rendszer **puffereli** (elmenti) a beírt karaktereket addig, amíg le nem ütöd az `Enter`-t.  
    – Ezt hívják **line buffering**-nek.
2. Az OS ezután átadja a puffer tartalmát a programnak a `stdin` csatornán keresztül.
3. A `scanf()` megpróbálja **formátum szerint értelmezni** az adatot (pl. `"%d"` → egész szám).
4. Ha sikerül, az értéket beírja abba a memóriacímbe, amit megadtál (`&x`).

---

## **3. Példa – működés megfigyelése**

`#include <stdio.h>  int main() {     int x;     printf("Adj meg egy számot: ");     scanf("%d", &x);     printf("A beolvasott szám: %d\n", x);     return 0; }`

**Lépésenként:**

- A `printf` a `stdout`-ra ír.
- A `scanf` a `stdin`-ről olvas.
- Amikor beírod: `123` majd `Enter`, a `stdin` pufferbe bekerül: `"123\n"`.
- A `scanf` kiolvassa az `123`-at, leáll a `\n` előtt, és eltárolja `x`-be.
---
## **4. De nem csak billentyűzetből olvashat**

A `stdin` átirányítható! Például:

`./program < input.txt`

Ebben az esetben a `scanf` **nem a billentyűzetről**, hanem az `input.txt` fájlból olvas, mert a shell átirányította a standard inputot oda.  
Ez ugyanaz, mintha így írnád:

`fscanf(fopen("input.txt", "r"), "%d", &x);`