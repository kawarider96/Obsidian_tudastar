# JSON/JSONB függvények

| Függvény        | Jelentés                          | Példa                                    |
|-----------------|-----------------------------------|------------------------------------------|
| `jsonb->'key'`  | JSON objektum olvasás             | `meta->'ip'`                             |
| `jsonb->>'key'` | JSON érték szövegként             | `meta->>'ip'`                            |
| `jsonb_set()`   | JSON érték módosítása             | `jsonb_set(meta, '{ip}', '"8.8.8.8"')`   |
| `jsonb_each()`  | Iterálás JSON objektum elemein    | pl. CTE-ben használható                  |
