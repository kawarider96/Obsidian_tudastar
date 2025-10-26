Az absztrakció lényege, hogy a **lényeges részleteket megtartjuk**, a többit elrejtjük.

## Példa

```python
from abc import ABC, abstractmethod

class Allat(ABC):
    @abstractmethod
    def hang(self): pass

class Kutya(Allat):
    def hang(self): return "Vau!"

class Macska(Allat):
    def hang(self): return "Miau!"
```

## Mikor hasznos?

- Ha több hasonló entitás van, de viselkedésük eltér
- Ha csak egy interfészt akarsz láttatni

## Előnyök

- Tisztább architektúra
- Könnyebb bővíthetőség
