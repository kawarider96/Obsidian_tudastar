# Inheritance (Öröklés)

Az öröklés lehetővé teszi, hogy egy osztály átvegye egy másik osztály viselkedését és attribútumait.

## Példa

```python
class Allat:
    def mozog(self):
        return "Mozgás"

class Kutya(Allat):
    def ugat(self):
        return "Vau!"
```

## Használat

```python
k = Kutya()
print(k.mozog())  # örökölt metódus
print(k.ugat())   # saját metódus
```

## Előnyök

- Kód újrahasználása
- Egyszerűbb bővíthetőség

## Hátrányok

- Túlzott öröklés → merev struktúra
- Néha a **kompozíció** jobb megoldás
