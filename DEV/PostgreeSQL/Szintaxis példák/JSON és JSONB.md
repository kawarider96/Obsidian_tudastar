# JSON és JSONB mezők

Strukturált adat tárolása szövegként vagy binárisan.

```sql
-- Kiolvasás JSONB mezőből
SELECT meta->>'ip' FROM logs;

-- Beszúrás
INSERT INTO logs (meta) VALUES ('{"ip": "127.0.0.1"}');
```
