---
title: Decorator pattern
tags:
  - informatika
  - pattern
  - design_pattern
  - decorator
  - programming
  - programozás
  - architecture
  - dev
status: complete
created: 2026-01-17
related: "[[Design patterns]]"
cover: "[[ddo.png]]"
---
# Decorator Pattern – „felöltöztetjük az objektumot”

**Cél:**  
Objektumokhoz **dinamikusan**, futásidőben adunk hozzá új viselkedést **anélkül**, hogy módosítanánk az eredeti osztályukat.

> **Kulcsötlet:**  
> nem öröklünk, hanem **becsomagolunk**.

---

## Mikor használd?

> [!info]
> 
> - Ha futásidőben akarsz új funkciót hozzáadni.
>     
> - Ha az öröklési hierarchia már kezd **szétcsúszni**.
>     
> - Ha több kombinálható extra viselkedés van (A + B + C).
>     

Ha ilyet látsz:

```text
Coffee
 ├─ MilkCoffee
 ├─ SugarCoffee
 ├─ MilkSugarCoffee
 ├─ MilkSugarCaramelCoffee
```

👉 Decorator kell.

---

## A probléma, amit megold

### ❌ Öröklési robbanás

- minden új extra = új subclass
    
- kombinációk száma elszáll
    
- merev struktúra
    

---

## A Decorator alapötlete

```text
Component
 ├─ ConcreteComponent
 └─ Decorator -> becsomagol egy Componentet
```

- a Decorator **ugyanazt az interfészt** valósítja meg
    
- belül tartalmaz egy másik Componentet
    
- delegál + hozzáad
    

---

## Példa – Coffee

### Közös interfész

```python
from abc import ABC, abstractmethod

class Coffee(ABC):
    @abstractmethod
    def cost(self) -> int:
        pass
```

### Alap objektum

```python
class SimpleCoffee(Coffee):
    def cost(self) -> int:
        return 5
```

### Absztrakt Decorator

```python
class CoffeeDecorator(Coffee):
    def __init__(self, coffee: Coffee):
        self._coffee = coffee
```

### Konkrét Decoratorok

```python
class MilkDecorator(CoffeeDecorator):
    def cost(self) -> int:
        return self._coffee.cost() + 2

class SugarDecorator(CoffeeDecorator):
    def cost(self) -> int:
        return self._coffee.cost() + 1
```

### Használat

```python
coffee = SimpleCoffee()
coffee = MilkDecorator(coffee)
coffee = SugarDecorator(coffee)

print(coffee.cost())  # 8
```

👉 sorrendtől függetlenül **kombinálható**.

---

## Láncolás természetesen jön

> [!info]  
> Minden Decorator ugyanaz az interfész, ezért egymásra pakolhatók.

```text
Sugar(
  Milk(
    SimpleCoffee
  )
)
```

---

## Való élet példák

> [!info]
> 
> - GUI komponensek (scroll, border, shadow)
>     
> - Logger-ek (timestamp, level, file, remote)
>     
> - HTTP middleware-ek
>     
> - I/O stream-ek (Java klasszikus példa)
>     

---

## Decorator vs Composite (fontos különbség)

|Decorator|Composite|
|---|---|
|Lánc|Fa|
|Funkció hozzáadás|Struktúra|
|Viselkedés|Részek-egész|

---

## Előnyök

> [!info]
> 
> - Nagyon rugalmas
>     
> - Futásidőben bővíthető
>     
> - Elkerüli az öröklési robbanást
>     

---

## Hátrányok

> [!warning]
> 
> - Sok kis osztály
>     
> - Debug nehezebb (több wrapper)
>     

---

## Tipikus hiba

```python
class MilkCoffee(SimpleCoffee):
    ...
```

👉 ez visszalépés öröklésbe.

---

## Mentális modell

```mermaid
graph LR
    Client --> Decorator
    Decorator --> Component
```

---

## Egy mondatos összefoglaló

> **Decorator = adj hozzá funkciót csomagolással, ne újabb subclass-szal.**