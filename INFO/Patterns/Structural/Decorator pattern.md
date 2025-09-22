# Decorator pattern

Funkciók dinamikus hozzáadása objektumokhoz anélkül, hogy megváltoztatnád azok osztályát.

## Mikor használd?

- Ha futásidőben szeretnél viselkedést hozzáadni.
- Ha el akarod kerülni az öröklésből származó komplexitást.

## Példa

```python
class Coffee:
    def cost(self): return 5

class MilkDecorator:
    def __init__(self, coffee): self.coffee = coffee
    def cost(self): return self.coffee.cost() + 2

# Használat
coffee = Coffee()
milk_coffee = MilkDecorator(coffee)
print(milk_coffee.cost())  # 7
```

## Előnyök

- Rugalmasság
- Futásidőben változtatható viselkedés

## Hátrányok

- Sok kis osztály
