# ENUM típus létrehozása

Előre meghatározott értékkészletű típus létrehozása.

```sql
CREATE TYPE user_status AS ENUM ('active', 'inactive', 'banned');

CREATE TABLE members (
    id SERIAL,
    status user_status NOT NULL
);
```
