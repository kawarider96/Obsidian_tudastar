# GROUP BY és aggregáció

Sorok csoportosítása és összesítése.

```sql
SELECT is_active, COUNT(*) 
FROM users
GROUP BY is_active;
```
