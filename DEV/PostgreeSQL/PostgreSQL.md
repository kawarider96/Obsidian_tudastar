# PostgreSQL

#postgresql #db #database #relációs_adatbázis #adatbázis #sql

Nyílt forráskódú, objektum-relációs adatbázis-kezelő rendszer (ORDBMS), amely megbízható, ACID-kompatibilis és enterprise-grade funkciókat kínál.

## Telepítés

- Weboldal: [https://www.postgresql.org/download/](https://www.postgresql.org/download/)
- GUI: **pgAdmin**, **DBeaver**, **TablePlus**
- Docker példa:
```bash
docker run --name postgres -e POSTGRES_PASSWORD=admin -p 5432:5432 -d postgres
```

## Alapfogalmak

| Fogalom       | Jelentés                                      |
| ------------- | --------------------------------------------- |
| Database      | Az egész adatbázis (konténer)                 |
| Table         | Tábla, adatokat tárol                         |
| Row (record)  | Egy sor adat                                  |
| Column        | Egy mező (mezőnév és adattípus)               |
| Primary Key   | Egyedi azonosító                              |
| Foreign Key   | Másik tábla mezőjére mutató kapcsolat         |
| Schema        | Logikai egység: táblák, függvények csoportja  |

## Tartalomjegyzék
# [[PostgreSQL függvények]]

# [[PostgreSQL szintaxis példák]]

# [[Postgre SQL Egyéb tudás]]

# [[PostgreSQL optimalizálás]]
