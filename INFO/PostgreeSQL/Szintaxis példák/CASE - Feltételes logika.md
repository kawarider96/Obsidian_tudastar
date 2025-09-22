# CASE – Feltételes logika

If-else logikát lehet megvalósítani SQL-ben.

```sql
SELECT 
  name,
  CASE 
    WHEN age < 18 THEN 'kiskorú'
    WHEN age >= 18 AND age < 65 THEN 'felnőtt'
    ELSE 'nyugdíjas'
  END AS korosztaly
FROM users;
```
