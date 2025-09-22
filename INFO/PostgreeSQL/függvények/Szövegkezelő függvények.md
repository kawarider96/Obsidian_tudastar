# Szövegkezelő függvények

| Függvény                   | Jelentés                     | Példa                                       |
|----------------------------|------------------------------|---------------------------------------------|
| `LENGTH(text)`             | Szöveg hossza                | `LENGTH('hello')` → `5`                     |
| `LOWER(text)`              | Kisbetűsítés                 | `LOWER('Krisz')` → `krisz`                  |
| `UPPER(text)`              | Nagybetűsítés                | `UPPER('Krisz')` → `KRISZ`                  |
| `TRIM(text)`               | Whitespace eltávolítása      | `TRIM(' hello ')` → `'hello'`               |
| `CONCAT(a, b)`             | Összefűzés                   | `CONCAT('a', 'b')` → `'ab'`                 |
| `SUBSTRING(text FROM x FOR y)` | Részszöveg kivágás     | `SUBSTRING('Krisztián' FROM 1 FOR 5)` → `'Krisz'` |
| `REPLACE(text, from, to)`  | Szövegrész cseréje           | `REPLACE('faszom', 'asz', '**')` → `'f**om'` |
| `POSITION(substr IN str)`  | Részszöveg helye             | `POSITION('s' IN 'Krisz')` → `4`            |
