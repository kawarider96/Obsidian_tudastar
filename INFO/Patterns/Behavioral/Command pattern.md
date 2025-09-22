# Command pattern

Parancsokat objektumként kezel, így támogatja a visszavonást, naplózást és késleltetést.

## Mikor használd?

- Ha akarsz `undo`, `redo`, `queue`, vagy napló funkciót.
- Ha különválasztanád a kérést a végrehajtástól.

## Példa

```python
class Command:
    def execute(self): pass

class LightOn(Command):
    def execute(self): return "Fény bekapcsolva"

class Remote:
    def submit(self, command):
        return command.execute()

# Használat
remote = Remote()
print(remote.submit(LightOn()))  # Fény bekapcsolva
```

## Előnyök

- Undo/Redo alap
- Kérés-végrehajtás szétválasztása

## Hátrányok

- Sok osztály
