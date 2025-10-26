A polimorfizmus lehetővé teszi, hogy különböző objektumok **ugyanazt a metódust** hívják meg, és a saját implementációjuk fusson le.

## Példa

```python
class Allat:
    def hang(self):
        pass

class Kutya(Allat):
    def hang(self): return "Vau!"

class Macska(Allat):
    def hang(self): return "Miau!"

def hangol(allat):
    print(allat.hang())

hangol(Kutya())   # Vau!
hangol(Macska())  # Miau!
```

## Típusai

- Statikus (pl. metódus túlterhelés – nem jellemző Pythonban)
- Dinamikus (pl. felülírás)

## Előnyök

- Egységes interfész
- Rugalmas, bővíthető kód
