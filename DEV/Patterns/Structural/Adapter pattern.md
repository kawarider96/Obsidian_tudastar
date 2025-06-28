# Adapter pattern

Az Adapter minta átalakítja egy osztály interfészét, hogy egy másik rendszer elvárásainak megfeleljen.

## Mikor használd?

- Ha egy meglévő osztály nem kompatibilis a kívánt interfésszel.
- Ha harmadik féltől származó könyvtárat akarsz integrálni saját rendszeredbe.

## Példa

```python
class OldPrinter:
    def print_text(self):
        return "nyomtatás elindítva"

class NewPrinterInterface:
    def print(self): pass

class PrinterAdapter(NewPrinterInterface):
    def __init__(self, old_printer):
        self.old = old_printer

    def print(self):
        return self.old.print_text()

# Használat
printer = PrinterAdapter(OldPrinter())
print(printer.print())  # nyomtatás elindítva
```

## Előnyök

- Kompatibilitás biztosítása
- Kód újrafelhasználása

## Hátrányok

- Extra réteg bonyolítja a struktúrát
