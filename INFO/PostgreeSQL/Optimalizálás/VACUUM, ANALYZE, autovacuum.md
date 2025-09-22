# VACUUM, ANALYZE, autovacuum

PostgreSQL nem töröl fizikailag sorokat, hanem „holttestként” tárolja azokat – ezt a VACUUM takarítja ki.

## Kézi használat

```sql
VACUUM;
VACUUM ANALYZE;
```

## ANALYZE

Frissíti a statisztikákat a lekérdezéstervező számára.

```sql
ANALYZE;
```

## Autovacuum

Alapértelmezetten fut, de hangolható a `postgresql.conf` fájlban:

```conf
autovacuum_vacuum_threshold = 50
autovacuum_vacuum_cost_limit = 200
```
