# Flyweight pattern

Olyan minta, amely osztja a közös állapotot az objektumok között a memória megtakarítása érdekében.

## Mikor használd?

- Ha sok azonos típusú objektumot hozol létre.
- Ha memóriát akarsz optimalizálni.

## Példa

```python
class Letter:
    _instances = {}

    def __new__(cls, char):
        if char not in cls._instances:
            cls._instances[char] = super().__new__(cls)
        return cls._instances[char]

# Használat
a1 = Letter('a')
a2 = Letter('a')
print(a1 is a2)  # True
```

## Előnyök

- Memóriatakarékos
- Közös állapot megosztása

## Hátrányok

- Bonyolult kezelés
