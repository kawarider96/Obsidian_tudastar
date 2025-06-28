# Lekérdezés – SELECT

Adatok lekérdezése táblából.

```sql
-- Összes oszlop
SELECT * FROM users;

-- Csak néhány mező, szűrve és rendezve
SELECT name, email FROM users
WHERE is_active = true
ORDER BY created_at DESC
LIMIT 10;
```
