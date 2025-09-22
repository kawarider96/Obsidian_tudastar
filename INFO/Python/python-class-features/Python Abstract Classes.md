# Python Abstract Classes

A Python `abc` modul segítségével absztrakt osztályokat hozhatunk létre.

## Alapok

Az absztrakt osztályok sablont biztosítanak a leszármazott osztályoknak.

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def speak(self):
        pass
```

## Fontos elemek

- `ABC`: Az absztrakt bázisosztály.
- `@abstractmethod`: Kötelezően implementálandó metódus.
- Nem lehet példányosítani az absztrakt osztályt, ha van benne implementálatlan `@abstractmethod`.

## Többszörös öröklés kombináció

```python
class Flyer(ABC):
    @abstractmethod
    def fly(self):
        pass

class Bird(Animal, Flyer):
    def speak(self):
        print("csirip")

    def fly(self):
        print("repül")
```

## Használat

Absztrakt osztályokat gyakran használnak interfészek szimulálására vagy plug-in rendszerekben.
