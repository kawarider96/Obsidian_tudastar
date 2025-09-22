# TRIGGER és trigger function

Automatikus művelet adott eseményre.

```sql
CREATE FUNCTION set_created_at()
RETURNS TRIGGER AS $$
BEGIN
  NEW.created_at := NOW();
  RETURN NEW;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER trg_users_created
BEFORE INSERT ON users
FOR EACH ROW
EXECUTE FUNCTION set_created_at();
```
