
# ✂️ C nyelv – Szövegkezelés (string műveletek)

A C-ben nincs beépített `string` típus — minden szöveg **karaktertömb (char[])**.

---

## 🔹 1. Alapfogalom
```c
char nev[50] = "Krisz";
printf("%s", nev);
```

A string **null terminátorral (`\0`)** zárul.  
Ez jelzi a végét a függvényeknek (`strlen`, `strcpy`, stb.).

---

## 🔹 2. Hossz meghatározása – `strlen()`

```c
#include <string.h>

int hossz = strlen(nev);
printf("Hossz: %d", hossz);
```

`strlen()` visszaadja a karakterek számát a `\0` előtt.

---

## 🔹 3. Másolás – `strcpy()` és `strncpy()`

```c
char cel[100];
strcpy(cel, "Hello");
```
⚠️ A `strcpy` nem védi túlcsordulás ellen. Biztonságosabb a `strncpy`:

```c
strncpy(cel, "Hello", sizeof(cel) - 1);
cel[sizeof(cel) - 1] = '\0'; //manuálisan odatesszük a végére a lezáró terminátort mert előfordulhat hogy ha a másolandó string hosszabb mint a rendelkezésre álló memória akkor lehagyja azt. És ha nincs lezáró terminátor akkor az baj, hiba lehet belőle meg minden szóval ez a rész a biztonság miatt kell.
```

---

## 🔹 4. Összefűzés – `strcat()` és `strncat()`

```c
char szo[100] = "Hello, ";
strcat(szo, "világ!");
printf("%s", szo);
```

Biztonságosabb változat:
```c
strncat(szo, "világ!", sizeof(szo) - strlen(szo) - 1);
```

---

## 🔹 5. Összehasonlítás – `strcmp()` és `strncmp()`

```c
if (strcmp(nev, "Krisz") == 0) {
    printf("Ugyanaz!");
}
```

`strcmp` = 0 → azonos,  
pozitív / negatív → különböznek.

---

## 🔹 6. Karakter keresés – `strchr()` és `strrchr()`

```c
char *ptr = strchr(nev, 'r');
if (ptr != NULL) printf("Megtaláltam az 'r'-t!");
```

- `strchr` → első előfordulás  
- `strrchr` → utolsó előfordulás

---

## 🔹 7. Részszöveg keresése – `strstr()`

```c
char *talalat = strstr("almafa", "fa");
if (talalat) printf("Benne van!");
```

---

## 🔹 8. Szöveg feldarabolása – `strtok()`

```c
#include <string.h>

char szoveg[] = "alma,banan,korte";
char *resz = strtok(szoveg, ",");

while (resz != NULL) {
    printf("%s\n", resz);
    resz = strtok(NULL, ",");
}
```

Eredmény:
```
alma
banan
korte
```

---

## 🔹 9. Újsor vagy szóköz levágása – `strcspn()`

```c
char szoveg[50];
fgets(szoveg, sizeof(szoveg), stdin);
szoveg[strcspn(szoveg, "\n")] = '\0';
```

➡️ Levágja az `ENTER` karaktert a végéről.

---

## 🔹 10. Összefoglalás táblázat

| Függvény            | Feladat             |
| ------------------- | ------------------- |
| `strlen`            | hossz meghatározás  |
| `strcpy`, `strncpy` | másolás             |
| `strcat`, `strncat` | összefűzés          |
| `strcmp`, `strncmp` | összehasonlítás     |
| `strchr`, `strrchr` | karakter keresés    |
| `strstr`            | részszöveg keresés  |
| `strtok`            | darabolás           |
| `strcspn`           | karakterek levágása |

---

💡 Tipp: mindig figyelj a **buffer méretre** és a **\0 lezárásra**, különben a program túlcsordulhat.
