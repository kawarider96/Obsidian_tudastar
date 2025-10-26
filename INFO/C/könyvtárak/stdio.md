az `stdio.h` a **C standard input/output könyvtára**, vagyis minden, ami **beolvasás, kiírás, fájlkezelés, formázott szöveg**: mind innen jön.

# Az `stdio.h` fő tartalmai
### 1. **Standard input/output függvények**

Ezek kezelik a képernyőre írást és billentyűzetről olvasást.

| Függvény                        | Leírás                                                        |
| ------------------------------- | ------------------------------------------------------------- |
| `printf()`                      | Formázott szöveg kiírása a standard kimenetre (képernyőre).   |
| `scanf()`                       | Formázott adatbeolvasás a standard bemenetről (billentyűzet). |
| `puts()`                        | Egy teljes sztring kiírása, automatikus `\n`-nal.             |
| `gets()` _(elavult, veszélyes)_ | Egy sor beolvasása (nem ellenőrzi a hosszát).                 |
| `putchar()`                     | Egyetlen karakter kiírása.                                    |
| `getchar()`                     | Egyetlen karakter beolvasása.                                 |
### 2. **Fájlkezelő függvények**

A fájlok olvasását/írását végzik.

| Függvény    | Leírás                                           |
| ----------- | ------------------------------------------------ |
| `fopen()`   | Fájl megnyitása (olvasásra, írásra, stb.).       |
| `fclose()`  | Fájl lezárása.                                   |
| `fread()`   | Tömbnyi adat beolvasása fájlból (bináris).       |
| `fwrite()`  | Tömbnyi adat kiírása fájlba (bináris).           |
| `fgetc()`   | Egy karakter olvasása fájlból.                   |
| `fputc()`   | Egy karakter írása fájlba.                       |
| `fgets()`   | Egy sor beolvasása fájlból.                      |
| `fputs()`   | Egy sztring kiírása fájlba.                      |
| `fprintf()` | Formázott írás fájlba.                           |
| `fscanf()`  | Formázott olvasás fájlból.                       |
| `feof()`    | Ellenőrzi, elértük-e a fájl végét (End Of File). |
| `fseek()`   | Fájlon belüli pozíció beállítása.                |
| `ftell()`   | Megadja az aktuális pozíciót a fájlban.          |
| `rewind()`  | Visszaállítja a fájlmutatót a fájl elejére.      |
### 3. **Hibakezelés és állapot**

|Függvény / Makró|Leírás|
|---|---|
|`perror()`|Kiírja az utolsó rendszerhibát szövegesen.|
|`clearerr()`|Törli a fájlhibákat.|
|`ferror()`|Ellenőrzi, volt-e I/O hiba.|
|`EOF`|Konstans, a fájl vége jelzésére (értéke általában `-1`).|

---

### 4. **Standard adatfolyamok (streamek)**

|Név|Jelentés|
|---|---|
|`stdin`|Standard input (billentyűzet)|
|`stdout`|Standard output (képernyő)|
|`stderr`|Standard error (hibaüzenetek)|

Ezek mind `FILE*` típusú pointerek.

---

### 5. **Típusdefiníciók**

|Típus|Leírás|
|---|---|
|`FILE`|Fájlleíró struktúra.|
|`fpos_t`|Fájlon belüli pozíció tárolására alkalmas típus.|
|`size_t`|Méretet leíró, platformfüggő egész típus.|

---

### 6. **Makrók**

|Makró|Jelentés|
|---|---|
|`NULL`|Null pointer.|
|`EOF`|Fájl vége (End Of File).|
|`BUFSIZ`|Ajánlott buffer méret.|
|`FILENAME_MAX`|Maximális fájlnévhossz.|
|`TMP_MAX`|Ideiglenes fájlnevek maximális száma.|
|`SEEK_SET`, `SEEK_CUR`, `SEEK_END`|A `fseek()`-hez használt pozíciójelölők.|

---

### 7. **Ideiglenes fájlkezelés**

|Függvény|Leírás|
|---|---|
|`tmpfile()`|Ideiglenes fájl létrehozása.|
|`tmpnam()`|Ideiglenes fájlnév generálása.|