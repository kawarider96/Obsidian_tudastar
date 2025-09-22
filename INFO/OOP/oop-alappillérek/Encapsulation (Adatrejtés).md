# Encapsulation (Adatrejtés)

Az adatrejtés célja, hogy az objektum belső állapotát elrejtsük a külvilág elől, és csak ellenőrzött módon engedjük hozzáférni.

## Lényege

- A változók és metódusok **összefogása** egy osztályban
- Adatok elrejtése és **getter/setter** metódusokon keresztüli elérés

## Példa

```python
class BankSzamla:
    def __init__(self, egyenleg):
        self.__egyenleg = egyenleg  # privát attribútum

    def leker(self):
        return self.__egyenleg

    def betesz(self, osszeg):
        if osszeg > 0:
            self.__egyenleg += osszeg
```

## Megjegyzés

- `__` (dupla aláhúzás): "name mangling", nem valódi védelem, de konvenció
- **Védi az érvénytelen használat ellen**
