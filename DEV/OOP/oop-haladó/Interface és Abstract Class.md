# Interface és Abstract Class

## Különbség

- **Abstract Class**: részben megvalósított viselkedés (lehet benne konkrét metódus)
- **Interface** (Pythonban absztrakt osztály + csak absztrakt metódusok): teljesen elvont, csak szerződés

## Példa (Python)

```python
from abc import ABC, abstractmethod

class Jarmu(ABC):
    @abstractmethod
    def halad(self): pass

class Auto(Jarmu):
    def halad(self): return "Autó halad"

print(Auto().halad())  # Autó halad
```

## Mikor használd?

- **Abstract Class**: ha van közös működés is
- **Interface**: ha csak struktúrát akarsz definiálni
