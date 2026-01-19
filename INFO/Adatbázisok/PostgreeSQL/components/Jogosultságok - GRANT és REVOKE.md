# Jogosultságok – GRANT és REVOKE

Felhasználók jogosultságainak kezelése.

```sql
CREATE ROLE readonly_user LOGIN PASSWORD 'valami';
GRANT CONNECT ON DATABASE mydb TO readonly_user;
GRANT SELECT ON ALL TABLES IN SCHEMA public TO readonly_user;
```
