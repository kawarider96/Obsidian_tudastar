# Connection pool – PgBouncer

A PostgreSQL kapcsolatok drágák – a PgBouncer egy könnyűsúlyú connection pooler, ami újrahasznosítja őket.

## Telepítés

Linuxon:

```bash
sudo apt install pgbouncer
```

## Konfiguráció (pgbouncer.ini)

```ini
[databases]
mydb = host=localhost port=5432 dbname=mydb

[pgbouncer]
listen_port = 6432
auth_type = md5
```

## Használat

Az alkalmazás a PgBouncerhez csatlakozik, az pedig továbbítja a kapcsolatokat a PostgreSQL felé.
