# Composition vs Inheritance

## Öröklés

Egy osztály egy másikból származik → fix, hierarchikus kapcsolat

## Kompozíció

Egy osztály **másik osztály példányát tartalmazza** → rugalmas, újrahasznosítható

## Példa

```python
class Motor:
    def indit(self): return "Motor indul"

class Auto:
    def __init__(self):
        self.motor = Motor()

    def indul(self):
        return self.motor.indit()
```

## Mikor melyiket?

- **Öröklés**: "is-a" kapcsolat
- **Kompozíció**: "has-a" kapcsolat

## Megjegyzés

- Kompozíció gyakran **rugalmasabb**
- Preferáld kompozíciót, ha nem kell viselkedést örökölni
