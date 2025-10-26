# C – UTF-8 kompatibilis konzol Windows alatt

## 🧠 Miért nem működik alapból az UTF-8?
A Windows konzol (CMD / PowerShell) alapértelmezés szerint **nem UTF-8**, hanem ún. *code page*-eket használ.
- Magyar Windows: `852 (OEM Latin-2)`
- UTF-8: `65001`

Ha a program UTF-8 karaktereket ír ki (pl. `Ö`, `é`, `ű`), de a konzol 852-es kódlapon van, akkor furcsa karakterek (`├í`, `Ã³`, stb.) jelennek meg.

---

## ⚙️ 1. Egyszerű, gyors megoldás
A konzolban futtatás előtt írd be:
```bash
chcp 65001
```
Ez átállítja a code page-et UTF-8-ra (65001).

Ezután futtasd:
```bash
./training.exe
```

---

## 🧠 2. Automatikus megoldás C kódon belül
A program elejére illeszd be a következő sort:

```c
#include <windows.h>

int main(void) {
    SetConsoleOutputCP(CP_UTF8);  // Kimenet UTF-8
    SetConsoleCP(CP_UTF8);        // Bemenet UTF-8
```
Ezzel a program automatikusan UTF-8 módba állítja a konzolt.

---

## 💡 3. A forráskód mentése UTF-8-ban
Győződj meg róla, hogy a `.c` fájl **UTF-8 kódolású**:
- Visual Studio Code: alul jobbra → `UTF-8` → *Save with encoding → UTF-8*
- Notepad++: *Encoding → Convert to UTF-8 (without BOM)*

---

## 🧩 4. Példa működő UTF-8 kompatibilis kódra

```c
#include <stdio.h>
#include <string.h>
#include <windows.h>

int main(void) {
    SetConsoleOutputCP(CP_UTF8);
    SetConsoleCP(CP_UTF8);

    printf("Üdvözöllek a C programodban!\n");
    printf("Írd be a parancsot: ");
    fflush(stdout);

    char input[100];
    fgets(input, sizeof(input), stdin);
    input[strcspn(input, "\n")] = '\0';

    if (strcmp(input, "exit") == 0) {
        printf("Kilépek. Viszlát!\n");
    } else {
        printf("Nem ismert parancs: %s\n", input);
    }

    printf("\nNyomj ENTER-t a kilépéshez...");
    getchar();
    return 0;
}
```

---

## ⚙️ 5. Alternatív parancssori megoldás (tartósabban)
```bash
chcp 65001
setx LANG en_US.UTF-8
```
Ez tartósabban beállítja az UTF-8 környezetet, de csak új terminálokra érvényes.

---

## 🧩 6. MSYS2 / MinGW64 alatt
Az MSYS2 terminál (amit fejlesztéshez használsz) **alapból UTF-8 kompatibilis**, így ott nem kell sem `chcp`, sem `SetConsoleOutputCP`.

---

## ✅ Összefoglalás

| Cél | Megoldás |
|------|-----------|
| Egyszeri futtatás UTF-8-ban | `chcp 65001` |
| Programból beállítani | `SetConsoleOutputCP(CP_UTF8);` és `SetConsoleCP(CP_UTF8);` |
| Forráskód ékezetes mentése | Mentsd UTF-8-ban (BOM nélkül) |
| MSYS2-ben futtatás | már alapból UTF-8-as |
| Tartós beállítás | `setx LANG en_US.UTF-8` |
