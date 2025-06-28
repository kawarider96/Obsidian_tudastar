# Magic methods (__str__, __repr__, __eq__ stb.)

A mágikus vagy dunder metódusok speciális funkciókat vezérelnek Pythonban.

## Gyakori példák

| Név        | Funkció                    |
|------------|----------------------------|
| `__init__` | Konstruktor                 |
| `__str__`  | `str(obj)` → emberi kiírás |
| `__repr__` | Debug-reprezentáció        |
| `__eq__`   | `==` összehasonlítás       |
| `__lt__`   | `<` kisebb összehasonlítás |
| `__len__`  | `len(obj)`                 |

## Példa

```python
class Ember:
    def __init__(self, nev):
        self.nev = nev

    def __str__(self):
        return f"{self.nev} vagyok"

print(str(Ember("Krisz")))  # Krisz vagyok
```
