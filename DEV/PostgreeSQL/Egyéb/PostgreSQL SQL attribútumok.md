# PostgreSQL SQL attribútumok

Adattáblák mezőihez rendelhető attribútumok.

| Attribútum                       | Jelentés                           | Példa                                             |
|----------------------------------|------------------------------------|----------------------------------------------------|
| `NOT NULL`                       | Nem lehet `NULL`                   | `name TEXT NOT NULL`                               |
| `NULL`                           | Lehet `NULL` (alapértelmezett)     | `middle_name TEXT`                                 |
| `UNIQUE`                         | Egyedi érték                       | `email TEXT UNIQUE`                                |
| `PRIMARY KEY`                    | Egyedi kulcs, `NOT NULL + UNIQUE`  | `id SERIAL PRIMARY KEY`                            |
| `FOREIGN KEY`                    | Hivatkozás másik tábla kulcsára    | `user_id INT REFERENCES users(id)`                 |
| `DEFAULT`                        | Alapértelmezett érték              | `created_at TIMESTAMP DEFAULT NOW()`               |
| `CHECK (...)`                    | Értékellenőrző feltétel            | `CHECK (age >= 18)`                                |
| `SERIAL`                         | Auto-increment egész szám          | `id SERIAL`                                        |
| `GENERATED ALWAYS AS IDENTITY`   | Modern auto-increment megoldás     | `id INT GENERATED ALWAYS AS IDENTITY`              |
| `ON DELETE ...`                  | Törlési szabály                    | `ON DELETE CASCADE`                                |
| `ON UPDATE ...`                  | Módosítási szabály                 | `ON UPDATE CASCADE`                                |
| `COMMENT ON COLUMN`              | Dokumentációs megjegyzés           | `COMMENT ON COLUMN users.name IS 'Felhasználónév'` |
| `INDEX`                          | Lekérdezés gyorsító index          | `CREATE INDEX ON users(name);`                     |
| `UNIQUE INDEX`                   | Egyediség + gyors keresés          | `CREATE UNIQUE INDEX ON users(email);`             |

> ℹ️ A `PRIMARY KEY` automatikusan tartalmazza a `NOT NULL` és `UNIQUE` szabályokat.
>  
> ℹ️ A `SERIAL` csak shortcut, valójában `SEQUENCE` mögötte.
>  
> ℹ️ Az `ON DELETE CASCADE` pl. user törlésével együtt törli a hozzátartozó rekordokat is.
