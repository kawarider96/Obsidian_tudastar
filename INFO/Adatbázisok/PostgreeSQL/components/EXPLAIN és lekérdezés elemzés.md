# EXPLAIN és lekérdezés elemzés

Az `EXPLAIN` kulcsszó segítségével elemezhetjük, hogyan hajtja végre a PostgreSQL az adott lekérdezést.

## Alap használat

```sql
EXPLAIN SELECT * FROM users WHERE email = 'test@example.com';
```

## EXPLAIN ANALYZE

Valós futtatást is végez, így pontos időket mutat:

```sql
EXPLAIN ANALYZE SELECT * FROM users WHERE email = 'test@example.com';
```

## Mire figyelj?

- `Seq Scan` → teljes tábla bejárása (index hiánya)
- `Index Scan` vagy `Bitmap Index Scan` → jó!
- `Rows`, `Loops` → becsült vs. valós értékek

