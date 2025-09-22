# Parancssoros monitorozás (psql)

Néhány parancs, amivel gyorsan ellenőrizheted az adatbázis állapotát.

## Aktív kapcsolatok

```sql
SELECT * FROM pg_stat_activity;
```

## Futtatott lekérdezések

```sql
SELECT pid, now() - pg_stat_activity.query_start AS duration, query 
FROM pg_stat_activity 
WHERE state != 'idle';
```

## Táblaméret

```sql
SELECT relname, pg_size_pretty(pg_total_relation_size(relid)) 
FROM pg_catalog.pg_statio_user_tables 
ORDER BY pg_total_relation_size(relid) DESC;
```
