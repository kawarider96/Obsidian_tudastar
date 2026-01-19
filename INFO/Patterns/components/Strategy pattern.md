---
related: "[[Design patterns]]"
cover: "[[event-driven.png]]"
---
# Strategy pattern

Egy algoritmuscsaládot reprezentál, amit futásidőben válthatsz.

## Mikor használd?

- Ha különböző változatai vannak egy viselkedésnek.
- Ha el akarod kerülni az `if-else`/`switch` logikát.

## Példa

```python
class Strategy:
    def execute(self): pass

class StrategyA(Strategy):
    def execute(self): return "A stratégia"

class StrategyB(Strategy):
    def execute(self): return "B stratégia"

class Context:
    def __init__(self, strategy):
        self.strategy = strategy

    def run(self):
        return self.strategy.execute()

# Használat
ctx = Context(StrategyA())
print(ctx.run())  # A stratégia
```

## Előnyök

- Cserélhető logika
- Egyszerűbb karbantartás

## Hátrányok

- Több osztály
