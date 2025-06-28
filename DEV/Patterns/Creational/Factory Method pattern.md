# Factory Method pattern

Ez a minta lehetővé teszi, hogy példányosítást alosztályokra bízzunk, anélkül, hogy konkrét osztályokat neveznénk meg.

## Mikor használd?

- Ha egy interfészt szeretnél, de a konkrét példány típusát alosztályokra bíznád.
- Ha bővíthető példányosítást szeretnél (pl. plugin rendszerek).

## Példa

```python
class Animal:
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        return "Vau!"

class Cat(Animal):
    def speak(self):
        return "Miau!"

# Factory
class AnimalFactory:
    def create_animal(self):
        pass

class DogFactory(AnimalFactory):
    def create_animal(self):
        return Dog()

class CatFactory(AnimalFactory):
    def create_animal(self):
        return Cat()

# Klienskód
def get_pet(factory: AnimalFactory):
    pet = factory.create_animal()
    return pet.speak()

print(get_pet(DogFactory()))  # → Vau!
print(get_pet(CatFactory()))  # → Miau!

```

## Előnyök

- Nyitott-zárt elv (Open/Closed Principle)
- Egyszerűbb bővítés új típusokkal

## Hátrányok

- Több osztály és absztrakció bevezetése
