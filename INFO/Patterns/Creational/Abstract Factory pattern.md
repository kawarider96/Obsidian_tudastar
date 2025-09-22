---
cover: "[[abstract_factory_cover.png]]"
---

Több kapcsolódó objektumcsalád létrehozása úgy, hogy ne kelljen konkrét osztályokra hivatkoznod

## Mikor használd?

- Ha különböző „termékcsaládokat” (pl. GUI elemek) szeretnél támogatni.
- Ha az objektumokat együtt kell használni (pl. WindowsButton + WindowsCheckbox).

## Példa

```python
class Button: pass
class WindowsButton(Button): pass
class MacButton(Button): pass

class GUIFactory:
    def create_button(self): pass

class WindowsFactory(GUIFactory):
    def create_button(self): return WindowsButton()

class MacFactory(GUIFactory):
    def create_button(self): return MacButton()
```

## Előnyök

- Egyszerre több objektum kompatibilitását biztosítja
- Jó moduláris architektúra alapja

## Hátrányok

- Komplexitás nő
