# Singleton pattern

Gondoskodik arról, hogy egy osztálynak csak egy példánya legyen, és globálisan elérhető maradjon.

## Mikor használd?

- Ha egyetlen központi vezérlőt vagy adatforrást használsz (pl. konfiguráció, logger).

## Példa

```python
class Singleton:
    _instance = None

    @staticmethod
    def get_instance():
        if Singleton._instance is None:
            Singleton._instance = Singleton()
        return Singleton._instance
```

## Előnyök

- Egységes hozzáférés
- Erőforrás-takarékos lehet

## Hátrányok

- Nehezen tesztelhető (globális állapot)
- Időzített inicializálás problémás lehet
