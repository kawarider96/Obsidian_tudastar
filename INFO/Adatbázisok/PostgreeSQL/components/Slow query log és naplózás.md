# Slow query log és naplózás

A lassú lekérdezések naplózása segít feltárni a teljesítményproblémákat.

## Aktiválás (postgresql.conf)

```conf
log_min_duration_statement = 500
log_statement = 'none'
```

Ez minden 500ms-nál lassabb lekérdezést naplózni fog.

## Naplóhely

Alapesetben: `/var/log/postgresql/postgresql-<verzió>-main.log`

## Tippek

- Kerüld a `SELECT *`-ot
- Használj szelektív `WHERE` feltételeket
- Indexeld, amit kell
