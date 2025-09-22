# Iterator pattern

Objektum elemeinek bejárása anélkül, hogy felfednénk a belső reprezentációt.

## Mikor használd?

- Ha szeretnél egységes módon végigmenni egy gyűjteményen.

## Példa

```python
class MyList:
    def __init__(self):
        self.items = [1, 2, 3]

    def __iter__(self):
        return iter(self.items)

# Használat
for item in MyList():
    print(item)
```

## Előnyök

- Egységes iterációs API
- Kód újrahasználható

## Hátrányok

- Több osztály kis kollekcióknál fölösleges
