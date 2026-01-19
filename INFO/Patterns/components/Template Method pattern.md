---
related: "[[Design patterns]]"
cover: "[[clean_arch.png]]"
---
# Template Method pattern

Egy algoritmus vázát definiálja egy metódusban, a részlépések delegálhatók alosztályokra.

## Mikor használd?

- Ha több algoritmus szerkezete hasonló, de néhány lépés különböző.

## Példa

```python
class Game:
    def play(self):
        self.start()
        self.run()
        self.end()

    def start(self): pass
    def run(self): pass
    def end(self): pass

class Chess(Game):
    def start(self): print("Sakk kezdődik")
    def run(self): print("Lépések")
    def end(self): print("Vége")
```

## Előnyök

- Közös algoritmus újrahasználata
- Stabil váz + rugalmas részletek

## Hátrányok

- Erős öröklési kötés
