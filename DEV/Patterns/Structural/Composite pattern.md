# Composite pattern

Lehetővé teszi, hogy az egyes objektumokat és azok csoportjait ugyanúgy kezeljük.

## Mikor használd?

- Ha hierarchikus szerkezetet akarsz létrehozni (pl. fájlrendszer).
- Ha szeretnéd egységesen kezelni a „leveleket” és az „ágakat”.

## Példa

```python
class Graphic:
    def draw(self): pass

class Circle(Graphic):
    def draw(self): return "Circle"

class Group(Graphic):
    def __init__(self):
        self.children = []

    def add(self, g):
        self.children.append(g)

    def draw(self):
        return [child.draw() for child in self.children]

# Használat
group = Group()
group.add(Circle())
print(group.draw())  # ['Circle']
```

## Előnyök

- Egységes kezelés
- Rekurzív struktúrákhoz ideális

## Hátrányok

- Bonyolultabb debugolás és karbantartás
