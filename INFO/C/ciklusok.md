
# 🔁 C nyelv – Ciklusok (loopok)

A **ciklusok** ismétlődő műveletek végrehajtására szolgálnak.  
C-ben három fő ciklustípus van:

1. `for` – ismétlések előre ismert számú végrehajtásához  
2. `while` – amíg a feltétel igaz  
3. `do while` – legalább egyszer lefut, majd feltétel alapján ismétel

---

## 🔹 1. `for` ciklus

A **for** ciklus a leggyakrabban használt, ha előre tudod, hányszor kell ismételni.

### Szintaxis:
```c
for (kezdet; feltétel; léptetés) {
    // ismétlendő utasítások
}
```

### Példa:
```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 5; i++) {
        printf("%d. ismétlés\n", i + 1);
    }
    return 0;
}
```

📘 Működés sorrendje:
1. inicializálás (`int i = 0`)
2. feltétel vizsgálat (`i < 5`)
3. törzs végrehajtása
4. léptetés (`i++`)
5. vissza a 2. ponthoz

---

### Többszörös léptetés
```c
for (int i = 0, j = 10; i < j; i++, j--) {
    printf("i=%d, j=%d\n", i, j);
}
```

---

## 🔹 2. `while` ciklus

A **while** ciklus addig fut, amíg a feltétel **igaz**.

### Szintaxis:
```c
while (feltétel) {
    // ismétlendő utasítások
}
```

### Példa:
```c
int i = 0;
while (i < 5) {
    printf("%d\n", i);
    i++;
}
```

Ha a feltétel kezdetben hamis, a ciklus **egyszer sem fut le.**

---

## 🔹 3. `do while` ciklus

Ez a ciklus **legalább egyszer lefut**, mert a feltételt **a végén** ellenőrzi.

### Szintaxis:
```c
do {
    // utasítások
} while (feltétel);
```

### Példa:
```c
int j = 0;
do {
    printf("%d\n", j);
    j++;
} while (j < 5);
```

Még ha `j >= 5` is az elején, a törzs **egyszer mindenképp lefut.**

---

## 🔹 4. `break` és `continue` utasítások

### `break` – megszakítja a ciklust:
```c
for (int i = 0; i < 10; i++) {
    if (i == 5) break;
    printf("%d\n", i);
}
```

Eredmény: 0–4

### `continue` – átugorja a ciklus hátralévő részét, és a következő iterációra ugrik:
```c
for (int i = 0; i < 10; i++) {
    if (i % 2 == 0) continue;
    printf("%d\n", i);
}
```
Eredmény: csak a páratlan számok (1, 3, 5, 7, 9)

---

## 🔹 5. Végtelen ciklus

```c
while (1) {
    printf("Ez örökké fut!\n");
}
```

Vagy:
```c
for (;;) {
    // szintén végtelen ciklus
}
```

Kilépni csak `break`-kel vagy `return`-nel lehet.

---

## 🔹 6. Egymásba ágyazott ciklusok (nested loops)

C-ben bármelyik ciklus lehet egy másik cikluson belül.

### Példa – szorzótábla:
```c
for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 3; j++) {
        printf("%d x %d = %d\n", i, j, i * j);
    }
}
```

---

## 🔹 7. Összefoglaló táblázat

| Ciklus | Mikor fut? | Ellenőrzés helye | Legalább egyszer lefut? |
|---------|-------------|------------------|---------------------------|
| `for` | előre ismert ismétlésszámnál | elején | ❌ |
| `while` | amíg igaz a feltétel | elején | ❌ |
| `do while` | legalább egyszer fut, aztán feltétel szerint | végén | ✅ |

---

💡 **Tipp:**  
Ha előre tudod a lépésszámot → `for` ciklus.  
Ha nem tudod, és feltétel alapján kell ismételni → `while`.  
Ha legalább egyszer mindenképp futnia kell → `do while`.
