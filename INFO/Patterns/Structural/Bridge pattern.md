# Bridge pattern

A Bridge minta leválasztja az absztrakciót a megvalósításról, hogy külön is fejleszthetők legyenek.

## Mikor használd?

- Ha egy osztálynak több dimenziója van (pl. forma + platform).
- Ha el akarod kerülni az öröklési robbanást.

## Példa

```python
class Renderer:
    def render(self): pass

class VectorRenderer(Renderer):
    def render(self): return "Vector"

class RasterRenderer(Renderer):
    def render(self): return "Raster"

class Shape:
    def __init__(self, renderer):
        self.renderer = renderer

class Circle(Shape):
    def draw(self): return f"{self.renderer.render()} Circle"

# Használat
shape = Circle(VectorRenderer())
print(shape.draw())  # Vector Circle
```

## Előnyök

- Függetlenség az absztrakció és implementáció között
- Kombinálható dimenziók

## Hátrányok

- Több osztály és bonyolultabb struktúra
