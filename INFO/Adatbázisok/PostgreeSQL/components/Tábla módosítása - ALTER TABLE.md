# Tábla módosítása – ALTER TABLE

```sql
ALTER TABLE users ADD COLUMN is_active BOOLEAN DEFAULT true;
ALTER TABLE users DROP COLUMN age;
ALTER TABLE users RENAME COLUMN name TO full_name;
ALTER TABLE users ALTER COLUMN email SET NOT NULL;
```
