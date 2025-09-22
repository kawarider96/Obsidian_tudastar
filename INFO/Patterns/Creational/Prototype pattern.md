# Prototype pattern

Objektumok klónozására szolgál anélkül, hogy új példányokat hoznál létre a `new` kulcsszóval.

## Mikor használd?

- Ha drága az objektum létrehozása.
- Ha gyakran előfordul hasonló példányok másolása.

## Példa

```python
import copy

class Sheep:
    def __init__(self, name):
        self.name = name

    def clone(self):
        return copy.deepcopy(self)

# Használat
dolly = Sheep("Dolly")
klon = dolly.clone()
```

## Előnyök

- Gyors példányosítás
- Konfigurált objektum újrahasznosítása

## Hátrányok

- Mély klónozás bonyolult lehet
- Objektum összetettségétől függ
