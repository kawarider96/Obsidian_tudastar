# Mixin és többes öröklés

## Mixin

Olyan kiegészítő osztály, amely **extra funkcionalitást** ad hozzá öröklés révén.

## Példa

```python
class LoggerMixin:
    def log(self, msg):
        print(f"LOG: {msg}")

class Szolgaltatas(LoggerMixin):
    def fut(self):
        self.log("Elindult")
```

## Többes öröklés

Python támogatja → egy osztály több ősosztályból is örökölhet.

## Megjegyzés

- Hasznos, de körültekintően használd
- Különösen figyelj az öröklési sorrendre (MRO)
