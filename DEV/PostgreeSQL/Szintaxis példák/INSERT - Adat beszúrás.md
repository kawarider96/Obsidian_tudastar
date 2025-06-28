# INSERT – Adat beszúrás

Új rekord(ok) beszúrása táblába.

## Egy rekord

```sql
INSERT INTO users (name, email)
VALUES ('Krisz', 'krisztian@example.com');
```

## Több rekord

```sql
INSERT INTO users (name, email)
VALUES 
  ('Jani', 'jani@example.com'),
  ('Peti', 'peti@example.com');
```
