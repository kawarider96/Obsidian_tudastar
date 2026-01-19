---
related: "[[Design patterns]]"
cover: "[[clean_arch.png]]"
---
# Visitor pattern

Új műveletek hozzáadása objektumstruktúrához az osztályok módosítása nélkül.

## Mikor használd?

- Ha gyakran kell új műveleteket végezni egy objektumcsoporton.
- Ha el akarod különíteni az adatszerkezetet és a logikát.

## Példa

```python
class Animal:
    def accept(self, visitor):
        visitor.visit(self)

class Dog(Animal): pass

class Visitor:
    def visit(self, obj):
        print(f"Látogatás: {type(obj).__name__}")
```

## Előnyök

- Műveletek tiszta szétválasztása
- Könnyen bővíthető viselkedés

## Hátrányok

- Nehézkes új osztályokkal bővíteni
