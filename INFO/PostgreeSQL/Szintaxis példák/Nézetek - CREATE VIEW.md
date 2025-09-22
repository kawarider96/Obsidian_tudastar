# Nézetek – CREATE VIEW

Mentett lekérdezések, mint "virtuális táblák".

```sql
CREATE VIEW active_users AS
SELECT * FROM users WHERE is_active = true;

-- Használata
SELECT * FROM active_users;
```
