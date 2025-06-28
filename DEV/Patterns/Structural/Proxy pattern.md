# Proxy pattern

Másik objektum helyettesítésére szolgál, hogy kontrollálja annak elérését.

## Mikor használd?

- Ha hozzáférésvezérlésre van szükség.
- Ha késleltetett betöltést vagy logolást akarsz.

## Példa

```python
class RealImage:
    def display(self): return "Kép betöltve"

class ImageProxy:
    def __init__(self):
        self.real = None

    def display(self):
        if not self.real:
            self.real = RealImage()
        return self.real.display()

# Használat
proxy = ImageProxy()
print(proxy.display())  # Kép betöltve
```

## Előnyök

- Hozzáférés szabályozása
- Késleltetett inicializálás

## Hátrányok

- Extra réteg és komplexitás
