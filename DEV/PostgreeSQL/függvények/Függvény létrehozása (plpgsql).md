# Függvény létrehozása (plpgsql)

Egyszerű SQL függvény definiálása PostgreSQL-ben.

```sql
CREATE OR REPLACE FUNCTION get_user_email(uid INT)
RETURNS TEXT AS $$
BEGIN
  RETURN (SELECT email FROM users WHERE id = uid);
END;
$$ LANGUAGE plpgsql;
```
