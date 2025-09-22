# Idő és dátumfüggvények

| Függvény            | Jelentés                            | Példa                                               | Megjegyzés                       |
|--------------------|-------------------------------------|-----------------------------------------------------|----------------------------------|
| `NOW()`             | Jelenlegi idő (időzónával)          | `NOW()`                                             | Alapértelmezett érték is lehet  |
| `CURRENT_DATE`      | Mai nap                             | `CURRENT_DATE` → `'2025-06-22'`                     |                                  |
| `CURRENT_TIME`      | Aktuális idő                        | `CURRENT_TIME`                                      |                                  |
| `CURRENT_TIMESTAMP` | Dátum + idő                         | `CURRENT_TIMESTAMP`                                 | Ugyanaz, mint `NOW()`            |
| `LOCALTIMESTAMP`    | Időzóna nélküli timestamp           | `LOCALTIMESTAMP`                                    |                                  |
| `AGE(ts)`           | Különbség `ts` és most között       | `AGE(created_at)`                                   | Emberbarát szöveg                |
| `EXTRACT(EPOCH ...)`| Időbélyeg másodpercben              | `EXTRACT(EPOCH FROM NOW())`                         | Unix timestamp                   |
| `EXTRACT(...)`      | Év, hónap stb. kibontása            | `EXTRACT(YEAR FROM NOW())` → `2025`                 | `DOW`: 0=vasárnap, 6=szombat     |
| `DATE_PART('x', d)` | Részelemek kinyerése                | `DATE_PART('month', created_at)`                    |                                  |
| `INTERVAL` művelet  | Időtartam hozzáadás/kivonás         | `NOW() - INTERVAL '1 week'`                         |                                  |
| `JUSTIFY_INTERVAL`  | Nagy intervallum formázása          | `JUSTIFY_INTERVAL(INTERVAL '1000 days')`            | → `2 years 270 days`             |
