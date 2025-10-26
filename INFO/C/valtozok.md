# 🧩 Jegyzet: Változók létrehozása C nyelvben

## 🔹 Alapfogalom

A **változó** egy névvel ellátott memóriahely, amely adatokat tárol egy
adott típusban.

## 🔹 Szintaxis

``` c
típus változónév = érték;
```

### Példák:

``` c
int szam = 10;         // egész szám
float ar = 19.99;      // lebegőpontos szám
char betu = 'A';       // karakter
double hossz = 3.14159;// nagyobb pontosságú lebegőpontos
```

## 🔹 Változók létrehozása és használata

``` c
#include <stdio.h>

int main() {
    int eletkor = 25;
    printf("Az eletkor: %d\n", eletkor);
    return 0;
}
```

A `printf`-ben a `%d`, `%f`, `%c` stb. **formátum specifikátor**
határozza meg, milyen típusú adatot írunk ki.

  Típus    Specifikátor
  -------- --------------
  int      %d
  float    %f
  char     %c
  double   %lf

------------------------------------------------------------------------

## 🔹 Dinamikusan változó méretű tömb létrehozása

A C-ben a **statikus tömb** mérete fix:

``` c
int tomb[5];
```

Ez mindig 5 elemű lesz.

Ha **dinamikusan** szeretnénk létrehozni (futásidőben változó mérettel),
akkor a **malloc()** vagy **calloc()** függvényeket használjuk.

### Példa -- dinamikus tömb:

``` c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    char *nev = NULL;  // pointer, kezdetben üres string
    char buffer[256];  // ideiglenes puffer a beolvasáshoz

    printf("Add meg a neved: ");
    if (fgets(buffer, sizeof(buffer), stdin) != NULL) {
        buffer[strcspn(buffer, "\n")] = '\0';  // az ENTER-t levágjuk

        // dinamikusan lefoglaljuk a memóriát pontosan akkora méretben, amekkora kell
        nev = (char *)malloc((strlen(buffer) + 1) * sizeof(char));
        if (nev == NULL) {
            printf("Memoriafoglalasi hiba!\n");
            return 1;
        }

        strcpy(nev, buffer);  // a nevet bemásoljuk a lefoglalt memóriába
    }

    if (nev && strlen(nev) > 0) {
        printf("Szia, %s!\n", nev);
    } else {
        printf("Nem adtál meg nevet.\n");
    }

    free(nev); // mindig felszabadítjuk
    return 0;
}
```
### 🔍 Magyarázat

|Rész|Mit csinál|
|---|---|
|`char *nev = NULL;`|Ez egy **mutató**, ami egyelőre nem mutat semmire. Ez jelenti az “üres stringet”.|
|`char buffer[256];`|Ideiglenes fix méretű puffer a `fgets` számára (így biztonságosabb, mint `scanf("%s")`).|
|`fgets(buffer, sizeof(buffer), stdin)`|Beolvassa a felhasználó által beírt sort, szóközökkel együtt.|
|`strcspn(buffer, "\n")`|Megkeresi és levágja az `ENTER` karaktert.|
|`malloc((strlen(buffer) + 1) * sizeof(char))`|Pont akkora memóriát foglal, amekkora a név hossza.|
|`strcpy(nev, buffer)`|Átmásolja a nevet a dinamikusan lefoglalt helyre.|
|`free(nev)`|Felszabadítja a memóriát.|