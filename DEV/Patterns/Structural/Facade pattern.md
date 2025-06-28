# Facade pattern

Egyszerűsített interfészt biztosít egy bonyolult rendszerhez.

## Mikor használd?

- Ha szeretnél elrejteni bonyolult logikát.
- Ha egységes belépési pontot akarsz biztosítani.

## Példa

```python
class CPU:
    def freeze(self): pass
    def execute(self): pass

class Memory:
    def load(self): pass

class Computer:
    def __init__(self):
        self.cpu = CPU()
        self.memory = Memory()

    def start(self):
        self.cpu.freeze()
        self.memory.load()
        self.cpu.execute()
```

## Előnyök

- Egyszerűség
- Modularitás

## Hátrányok

- Rejtett komplexitás
