# Backup és Restore (parancssor)

Adatbázis mentése és visszatöltése parancssorból.

## Mentés

```bash
pg_dump -U postgres mydb > backup.sql
```

## Visszaállítás

```bash
psql -U postgres -d mydb < backup.sql
```
