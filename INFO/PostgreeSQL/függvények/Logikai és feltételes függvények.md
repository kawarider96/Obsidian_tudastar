# Logikai és feltételes függvények

| Függvény / szerkezet                 | Jelentés                 | Példa                                                  |
|--------------------------------------|--------------------------|---------------------------------------------------------|
| `COALESCE(a, b, ...)`                | Első nem-NULL érték      | `COALESCE(name, 'Névtelen')`                           |
| `NULLIF(a, b)`                       | Ha egyenlő, akkor NULL   | `NULLIF(a, 0)`                                         |
| `CASE WHEN ... THEN ... ELSE ... END`| If-else logika           | `CASE WHEN age < 18 THEN 'gyerek' ELSE 'felnőtt' END` |
