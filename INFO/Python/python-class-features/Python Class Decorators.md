# Python Class Decorators

A Python osztályszintű dekorátorai különleges szerepet töltenek be, és az `@` szintaxissal használjuk őket.

## `@staticmethod`

Statikus metódus – nem kap sem `self`, sem `cls` paramétert.
Gyakorlatilag megkerüli az osztály viselkedést. Semmi köze semmihez csak sima function-ként hivható. Nem kell neki példány, self semmi.
```python
class Math:
    def __init__(self, base):
        self.base = base  # példányhoz kötött érték

    # 🔹 Sima példánymetódus: használja self-et
    def add_to_base(self, value):
        return self.base + value

    # 🔹 Osztálymetódus: osztályszinten dolgozik
    class_variable = 100

    @classmethod
    def show_class_variable(cls):
        return cls.class_variable

    # 🔹 Statikus metódus: teljesen független
    @staticmethod
    def add(a, b):
        return a + b


# ✅ Sima példánymetódus
m = Math(10)
print("Sima példánymetódus:", m.add_to_base(5))  # self.base = 10 → 10 + 5 = 15

# ✅ Osztálymetódus
print("Osztálymetódus:", Math.show_class_variable())  # → 100

# ✅ Statikus metódus (nem kell példány)
print("Statikus metódus:", Math.add(2, 3))  # → 5
```

## `@classmethod`

Osztálymetódus – az első paraméter `cls`, nem példány, hanem osztályszinten hívható.
- **Minden példány ugyanazt látja** alapból
- A `@classmethod` segítségével a metódus az **osztályon** dolgozik (nem a példányon)

```python
class Person:
    def __init__(self, name):
        self.name = name

    @classmethod
    def default_person(cls):
        return cls("Névtelen")

p = Person.default_person()
print(p.name)  # → Névtelen
```

Az osztály szintjén bármi módosíthatja:
```python
Person.class_variable = "Kati"
print(Person.show_class_variable())  # → Kati
```

Egy példány viszont **árnyékolhatja**:
```python
p = Person()
p.class_variable = "Józsi"  # ez új példányváltozó, NEM módosítja az osztályszintűt

print(p.class_variable)          # → Józsi
print(Person.class_variable)     # → Kati (vagy amit az osztály szintjén állítottunk)
```
## `@property`

Tulajdonságként viselkedő metódus, amit úgy hívsz, mint egy attribútumot.

```python
class Celsius:
    def __init__(self, temp):
        self._temp = temp

    @property
    def fahrenheit(self):
        return self._temp * 1.8 + 32
```

## `@<property>.setter` és `@<property>.deleter`

A property attribútumhoz tartozó setter és deleter.

```python
class Celsius:
    @fahrenheit.setter
    def fahrenheit(self, value):
        self._temp = (value - 32) / 1.8
```

## `@abstractmethod`

Lásd: [[Python Abstract Classes]]

## Saját dekorátor osztályban

```python
def log_method(func):
    def wrapper(*args, **kwargs):
        print(f"Hívás: {func.__name__}")
        return func(*args, **kwargs)
    return wrapper

class MyClass:
    @log_method
    def do_something(self):
        print("Valami történik")
```
