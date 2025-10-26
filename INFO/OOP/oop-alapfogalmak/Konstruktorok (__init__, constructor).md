A konstruktor egy speciális metódus, amely automatikusan lefut, amikor egy objektum példányosításra kerül.

## Pythonban: `__init__`

```python
class Kutya:
    def __init__(self, nev):
        self.nev = nev
```

## Használat

```python
k = Kutya("Bodri")
print(k.nev)  # Bodri
```

- `__init__` automatikusan meghívódik
- `self` mindig az aktuális példányra mutat

## Megjegyzés

Más nyelvekben:
- **Java**: az osztály nevével megegyező nevű metódus a konstruktor
- **C#**: szintén az osztály nevével megegyező, túlterhelhető

## Tippek

- Lehetnek opcionális paraméterek
- Használható validációra is
