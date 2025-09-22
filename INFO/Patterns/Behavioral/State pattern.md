# State pattern

Az objektum viselkedése megváltozik annak aktuális állapotától függően.

## Mikor használd?

- Ha egy objektum több állapotban viselkedik eltérően.
- Ha el akarod kerülni a bonyolult `if-else` vagy `switch` logikát.

## Példa

```python
class State:
    def handle(self): pass

class OnState(State):
    def handle(self): return "Be van kapcsolva"

class OffState(State):
    def handle(self): return "Ki van kapcsolva"

class Switch:
    def __init__(self):
        self.state = OffState()

    def toggle(self):
        self.state = OnState() if isinstance(self.state, OffState) else OffState()

    def status(self):
        return self.state.handle()
```

## Előnyök

- Állapotalapú logika tiszta kezelése
- Bővíthető állapotok

## Hátrányok

- Sok kis osztály
