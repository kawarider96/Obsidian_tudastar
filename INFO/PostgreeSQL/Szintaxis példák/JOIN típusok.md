# JOIN típusok

Adatok összekapcsolása több táblából.

```sql
SELECT users.name, posts.title
FROM users
JOIN posts ON users.id = posts.user_id;
```

## Típusok

- `JOIN` / `INNER JOIN`: csak a közös rekordokat adja vissza
- `LEFT JOIN`: minden bal oldali + illeszkedő jobb
- `RIGHT JOIN`: minden jobb oldali + illeszkedő bal
- `FULL JOIN`: minden mindenhonnan
- `CROSS JOIN`: minden sor minden másikkal (ritka)
