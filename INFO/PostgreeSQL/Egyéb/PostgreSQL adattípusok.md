# PostgreSQL adattípusok

Részletes lista a leggyakoribb adattípusokról, példákkal és megjegyzésekkel.

| Típus 📦       | Jelentés 📖          | Példa               | Megjegyzés 🧠                                  |
| ------------- | ------------------- | ------------------- | ---------------------------------------------- |
| `INTEGER`     | Egész szám          | `42`                | ±2 milliárd (4 bájt)                           |
| `SMALLINT`    | Kis egész szám      | `32000`             | 2 bájt                                          |
| `BIGINT`      | Nagy egész szám     | `9223372036854775807` | 8 bájt                                          |
| `SERIAL`      | Auto-increment INT  | –                   | INT + SEQUENCE                                 |
| `BIGSERIAL`   | Auto-increment BIGINT | –                 | Hatalmas ID tartomány                          |
| `DECIMAL(x,y)`| Fixpontos szám      | `123.45`            | Pontos pénzügyi számítás                       |
| `REAL`        | Approx. float       | `3.14`              | 4 bájt                                          |
| `DOUBLE PRECISION` | Nagyobb pontosság | `3.1415`        | 8 bájt                                          |
| `BOOLEAN`     | Igaz / hamis        | `true`              | `false` is lehet                               |
| `TEXT`        | Hosszú szöveg       | `'hello'`           | Hossz korlátlan                                |
| `VARCHAR(n)`  | Max `n` hossz       | `'abc'`             | PostgreSQL-ben alig különbözik `TEXT`-től      |
| `CHAR(n)`     | Fix hosszú szöveg   | `'a '`              | Ritkán használt                                |
| `DATE`        | Dátum               | `'2025-06-22'`      | Csak nap                                       |
| `TIMESTAMP`   | Dátum + idő         | `'2025-06-22 14:00'`| Nincs időzóna                                  |
| `TIMESTAMPTZ` | Időzónás timestamp  | `'2025-06-22 14:00+02'` | Mindig ezt használd több időzóna esetén |
| `INTERVAL`    | Időtartam           | `'2 days'`          | Különbség időpontok között                     |
| `UUID`        | Egyedi azonosító    | `'550e...'`         | Globálisan egyedi                              |
| `JSON`        | Nyers JSON          | `'{"key": "val"}'`  | Nem indexelhető                                |
| `JSONB`       | Bináris JSON        | Ugyanaz             | Indexelhető, mindig ezt használd               |
| `BYTEA`       | Bináris adat        | `\xDEADBEEF`       | Fájlok tárolása                                |
| `ARRAY[]`     | Tömb                | `ARRAY[1,2,3]`      | PostgreSQL sajátosság                          |
| `ENUM`        | Meghatározott értékek | `'active'`        | Létre kell hozni előre                         |
| `GEOMETRY`    | Térinformatika      | –                   | PostGIS bővítménnyel                           |
