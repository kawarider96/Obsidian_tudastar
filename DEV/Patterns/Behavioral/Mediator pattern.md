# Mediator pattern

Egy központi objektum szabályozza az osztályok közötti kommunikációt, így azok nem kommunikálnak közvetlenül.

## Mikor használd?

- Ha sok komponens közvetlenül hívogatja egymást.
- Ha laza csatolásra van szükség.

## Példa

```python
class Mediator:
    def notify(self, sender, msg): pass

class ConcreteMediator(Mediator):
    def notify(self, sender, msg):
        print(f"Mediator kapott: {msg} ({sender})")

class Component:
    def __init__(self, mediator):
        self.mediator = mediator

    def do_something(self):
        self.mediator.notify(self, "történt valami")
```

## Előnyök

- Csatolás csökken
- Központi kontroll

## Hátrányok

- Mediátor túl nagy lehet
