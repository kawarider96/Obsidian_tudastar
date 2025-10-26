A `stdout` ugyanolyan alapfogalom, mint a `stdin`, csak **ellenkező irányba folyik rajta az adat**. Nézzük részletesen:

## 🧩 **1. Mi a `stdout`?**

A `stdout` (standard output) a **programod kimeneti adatfolyama**.

- Ez is egy **FILE*** típusú objektum, amit az operációs rendszer automatikusan létrehoz a program indításakor.
- Alapértelmezésben a **képernyőre (terminálra)** ír, vagyis a te „output ablakodra”.
- Belső azonosítója a **fájlleíró 1** (a `stdin` 0, a `stderr` 2).

---

## ⚙️ **2. Hogyan működik a háttérben**

Ha ezt írod:

`printf("Hello");`

akkor a folyamat így néz ki:

```c
C forráskód:    printf("Hello");         
│         
▼ C runtime:    vfprintf(stdout, "Hello", args)
│
▼ OS hívás:     write(1, "Hello", 5)         
│
▼ Kernel:       elküldi az adatot a terminál drivernek
│
▼ Terminál:     megjeleníti a karaktereket a képernyőn`
```
Tehát:

- a **`printf`** → az **`stdout`**-ra ír,
- az **`stdout`** → a kernel felé továbbítja az adatot (system call: `write`),
- a **kernel** → a terminál eszköznek adja,
- az **eszközmeghajtó** → végül a képernyőn megjeleníti.

---

## 🧠 **3. A `stdout` pufferelése**

A `stdout` **pufferelt adatfolyam**, vagyis az adatok **nem rögtön** jelennek meg a képernyőn, hanem előbb egy memória-pufferbe kerülnek.

Ez a teljesítményt növeli, mert így az OS ritkábban hívja a drága I/O műveleteket.

### Három pufferelési mód:

|Típus|Mikor ürül?|Példa|
|---|---|---|
|**Fully buffered**|ha megtelik a puffer vagy `fflush()`|fájlba írás|
|**Line buffered**|új sor (`\n`) esetén vagy ha olvasás történik a stdin-ről|terminál output|
|**Unbuffered**|azonnal|`stderr` (hibaüzenetek)|

A `stdout` tehát **line-bufferelt**, ezért ha `\n` nélkül írsz, az adat sokszor csak akkor jelenik meg, amikor a program befejeződik vagy manuálisan `fflush(stdout)`-ot hívsz.

---

## 💡 **4. Átirányítható**

A `stdout` ugyanúgy, mint a `stdin`, **átirányítható** fájlba vagy más eszközre.  
Példa parancssorban:

`./program > output.txt`

Ilyenkor a `printf()` már **nem a képernyőre ír**, hanem az `output.txt` fájlba.  
Ez a shellben történő **I/O redirection**.

---

## 🧩 **5. `stdout` és `stderr` különbsége**

Mindkettő kimeneti adatfolyam, de:

- `stdout` → normál kimenet (pufferelt)
    
- `stderr` → hibakimenet (nem pufferelt)
    

Ezért ha ezt írod:

`fprintf(stdout, "Hello\n"); fprintf(stderr, "Error!\n");`

akkor még akkor is megjelenik a hibaüzenet azonnal, ha a `stdout` puffere tele van vagy fájlba van irányítva.