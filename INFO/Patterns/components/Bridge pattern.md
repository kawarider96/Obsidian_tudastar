---
title: Bridge pattern
status: complete
tags:
  - informatika
  - programming
  - programozás
  - architecture
  - pattern
  - design_pattern
  - bridge
created: 2026-01-17
related: "[[Design patterns]]"
cover: "[[ddo.png]]"
---
# Bridge Pattern – „ne az öröklés robbanjon, hanem a kombináció”

**Cél:**  
Az **absztrakciót** (amit a kliens használ) leválasztjuk a **megvalósítástól** (ami ténylegesen elvégzi a munkát), hogy **külön fejlődhessenek**.

> **Kulcsötlet:** nem örökléssel kombinálunk, hanem **kompozícióval**.

---

## Mikor használd?

> [!info]
> 
> - Ha egy osztálynak **több, egymástól független dimenziója** van (pl. _Shape × Renderer_, _UI × Platform_).
>     
> - Ha az öröklési hierarchia kezd **szétrobbanni**.
>     
> - Ha új variánsokat akarsz hozzáadni **régi kód módosítása nélkül**.
>     

Ha ilyet látsz a fejedben:

```text
CircleVector
CircleRaster
SquareVector
SquareRaster
```

👉 Bridge kell.

---

## A minta felépítése (mentális modell)

```
Abstraction  ----has-a---->  Implementation
```

- **Abstraction**: amit a kliens használ (`Shape`)
    
- **Implementation**: amit cserélhetsz (`Renderer`)
    

---

## Példa – Shape + Renderer

### Implementációs hierarchia

```python
from abc import ABC, abstractmethod

class Renderer(ABC):
    @abstractmethod
    def render_circle(self) -> str:
        pass

class VectorRenderer(Renderer):
    def render_circle(self) -> str:
        return "Drawing circle as vectors"

class RasterRenderer(Renderer):
    def render_circle(self) -> str:
        return "Drawing circle as pixels"
```

### Absztrakciós hierarchia

```python
class Shape(ABC):
    def __init__(self, renderer: Renderer):
        self.renderer = renderer

    @abstractmethod
    def draw(self) -> str:
        pass

class Circle(Shape):
    def draw(self) -> str:
        return self.renderer.render_circle()
```

### Használat

```python
vector_circle = Circle(VectorRenderer())
raster_circle = Circle(RasterRenderer())

print(vector_circle.draw())
print(raster_circle.draw())
```

---

## Miért működik jól?

> [!info]
> 
> - Az absztrakció **nem tudja**, hogyan történik a megvalósítás.
>     
> - A megvalósítás **nem tudja**, mit reprezentál az absztrakció.
>     
> - Együtt mégis rugalmas rendszert adnak.
>     

---

## Öröklés vs Bridge

### ❌ Öröklés

```text
CircleVectorRenderer
CircleRasterRenderer
SquareVectorRenderer
SquareRasterRenderer
```

- kombinatorikus robbanás
    
- merev struktúra
    

### ✅ Bridge

```text
Shape -> Circle, Square
Renderer -> Vector, Raster
```

👉 n × m kombináció, de csak n + m osztály.

---

## Előnyök

> [!info]
> 
> - Megszünteti az öröklési robbanást
>     
> - Nyitott bővítésre (OCP)
>     
> - Implementáció cserélhető futásidőben
>     

---

## Hátrányok

> [!warning]
> 
> - Több absztrakció
>     
> - Kis projektnél overkill
>     

---

## Bridge vs Strategy (röviden)

|Bridge|Strategy|
|---|---|
|Strukturális minta|Viselkedési minta|
|Architektúra szint|Algoritmus szint|
|Mit × hogyan|Hogyan|

---

## Egy mondatos összefoglaló

> **Bridge = válaszd szét azt, amit csinálsz attól, ahogyan csinálod, különben az öröklés megesz.**