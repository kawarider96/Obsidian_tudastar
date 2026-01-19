# Python Magic Methods

A Pythonban a "magic methods" (vagy dunder methods – double underscore) speciális metódusok, amelyeket a Python interpreter automatikusan hív meg bizonyos műveletek során.

## Alap metódusok

### `__init__(self, ...)`
Az osztály példányosításakor hívódik meg.

```python
class Dog:
    def __init__(self, name):
        self.name = name
```

### `__str__(self)`
A `str(obj)` vagy `print(obj)` meghívásakor.

### `__repr__(self)`
A hivatalos reprezentáció – pl. debuggerhez.

### `__len__(self)`
A `len(obj)` hívásakor.

### `__getitem__(self, key)`
Indexelés (`obj[key]`) során hívódik meg.

### `__setitem__(self, key, value)`
Indexelt érték beállításánál.

### `__delitem__(self, key)`
Indexelt érték törlésénél.

## Operátor overload metódusok

| Operátor | Metódus |
|----------|---------|
| `+`      | `__add__` |
| `-`      | `__sub__` |
| `*`      | `__mul__` |
| `/`      | `__truediv__` |
| `==`     | `__eq__` |
| `!=`     | `__ne__` |
| `<`      | `__lt__` |
| `<=`     | `__le__` |
| `>`      | `__gt__` |
| `>=`     | `__ge__` |

## Kontextuskezelés

### `__enter__(self)` és `__exit__(self, exc_type, exc_val, exc_tb)`
`with` blokkoknál használatos.

```python
class MyResource:
    def __enter__(self):
        print("Entering")
        return self
    def __exit__(self, exc_type, exc_val, exc_tb):
        print("Exiting")
```

## Callable objektumok

### `__call__(self, *args, **kwargs)`
Példány úgy viselkedik, mint egy függvény.

## Egyéb érdekesek

- `__contains__` – `in` operátor.
- `__iter__`, `__next__` – iterátor protokoll.
- `__bool__` – logikai értékre konvertálás.
