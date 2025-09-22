# Indexek optimalizálása

Az indexek gyorsítják a lekérdezéseket, de memóriát és írási teljesítményt fogyasztanak.

## Létrehozás

```sql
CREATE INDEX idx_users_email ON users(email);
```

## Használat ellenőrzése

```sql
EXPLAIN SELECT * FROM users WHERE email = 'a@example.com';
```

## Típusok

- `BTREE` (alapértelmezett) – egyenlőség és rendezettség
- `GIN` – JSONB típushoz
- `GiST`, `SP-GiST` – térbeli adatokhoz
- `HASH` – csak egyenlőséghez (ritkán jobb, mint BTREE)

## Felesleges index törlése

```sql
DROP INDEX IF EXISTS idx_nev;
```
