---
cover: "[[abstract_factory_cover.png]]"
---

Több kapcsolódó objektumcsalád létrehozása úgy, hogy ne kelljen konkrét osztályokra hivatkoznod

## Mikor használd?

- Ha különböző „termékcsaládokat” (pl. GUI elemek) szeretnél támogatni.
- Ha az objektumokat együtt kell használni (pl. WindowsButton + WindowsCheckbox).

## Példa
- Absztrakt import és interface-ek. Nem tartalmaz semmiféle logikát ez csak egy szerződés.
```python
from abc import ABC, abstractmethod

class Button(ABC):
    @abstractmethod
    def render(self):
        pass

class Checkbox(ABC):
    @abstractmethod
    def render(self):
        pass
```

Átadjuk a Button és Checkbox classokat ezért a konkrét WindowsButton class tudja hogy kell neki egy render metódus
```python
class WindowsButton(Button):
    def render(self):
        return "Windows Button"

class WindowsCheckbox(Checkbox):
    def render(self):
        return "Windows Checkbox"

class LinuxButton(Button):
    def render(self):
        return "Linux Button"

class LinuxCheckbox(Checkbox):
    def render(self):
        return "Linux Checkbox"
```

```python
class UIFactory(ABC):
    @abstractmethod
    def create_button(self) -> Button:
        pass

    @abstractmethod
    def create_checkbox(self) -> Checkbox:
        pass
```

```python
class WindowsFactory(UIFactory):
    def create_button(self):
        return WindowsButton()

    def create_checkbox(self):
        return WindowsCheckbox()

class LinuxFactory(UIFactory):
    def create_button(self):
        return LinuxButton()

    def create_checkbox(self):
        return LinuxCheckbox()
```

```python
def render_ui(factory: UIFactory):
    button = factory.create_button()
    checkbox = factory.create_checkbox()

    print(button.render())
    print(checkbox.render())

factory = WindowsFactory()
render_ui(factory)

print("----")

factory = LinuxFactory()
render_ui(factory)

```
## Előnyök

- Egyszerre több objektum kompatibilitását biztosítja
- Jó moduláris architektúra alapja

## Hátrányok

- Komplexitás nő
