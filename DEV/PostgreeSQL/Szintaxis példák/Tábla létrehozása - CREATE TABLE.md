# Tábla létrehozása – CREATE TABLE

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name TEXT NOT NULL,
    email TEXT UNIQUE,
    age INT CHECK (age >= 18),
    created_at TIMESTAMPTZ DEFAULT NOW()
);
```

- `SERIAL` → auto-increment
- `CHECK` → értékellenőrzés
- `DEFAULT` → alapértelmezett érték
- `TIMESTAMPTZ` → időzónás timestamp
