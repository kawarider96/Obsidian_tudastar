# CTE – Common Table Expression (WITH)

Ideiglenes névvel ellátott lekérdezés, amit később újra felhasználhatsz.

```sql
WITH active AS (
  SELECT * FROM users WHERE is_active = true
)
SELECT * FROM active WHERE email LIKE '%@gmail.com';
```
