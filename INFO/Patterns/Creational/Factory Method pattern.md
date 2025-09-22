# Factory Method pattern

Ez a minta lehetővé teszi, hogy példányosítást alosztályokra bízzunk, anélkül, hogy konkrét osztályokat neveznénk meg.

## Mikor használd?

- Ha egy interfészt szeretnél, de a konkrét példány típusát alosztályokra bíznád.
- Ha bővíthető példányosítást szeretnél (pl. plugin rendszerek).

## Példa
Vizuális ábra: [[FactoryMethod.canvas|FactoryMethod]]

```php
interface Vehicle {
    public function Drive(): string;
}

Class Car Implements Vehicle
{
    public function Drive(): string
    {
        return "Driving a car!";
    }
}

Class Bike Implements Vehicle
{
    public function Drive(): string
    {
        return "Drive a bike!";
    }
}

abstract Class VehicleFactory
{
    abstract public function createVehicle(): Vehicle;
  
    public function move(): string
    {
        $vehicle = $this->createVehicle();
        return $vehicle->drive();
    }
}

Class CarFactory extends VehicleFactory
{
    public function CreateVehicle(): Vehicle
    {
        return new Car();
    }
}

class BikeFactory extends VehicleFactory
{
    public function CreateVehicle(): Vehicle

    {
        return new Bike();
    }
}

$carFactory = new CarFactory();
echo $carFactory->move();

$carFactory = new BikeFactory();
echo $carFactory->move();

```

## Előnyök

- Nyitott-zárt elv (Open/Closed Principle)
- Egyszerűbb bővítés új típusokkal

## Hátrányok

- Több osztály és absztrakció bevezetése

Bónusz: Példa Pythonban

```python
from abc import ABC, abstractmethod

class Vehicle(ABC):
    @abstractmethod
    def drive(self) -> str:
        pass
  
class Car(Vehicle):
    def drive(self) -> str:
        return "Driving a car"

class Bike(Vehicle):
    def drive(self) -> str:
        return "Riding a bike"
        
class VehicleFactory(ABC):
    @abstractmethod
    def create_vehicle(self) -> Vehicle:
        pass
  
    def move (self) -> str:
        vehicle = self.create_vehicle()
        return vehicle.drive()
  
class CarFactory(VehicleFactory):
    def create_vehicle(self) -> Vehicle:
        return Car()
        
class BikeFactory(VehicleFactory):
    def create_vehicle(self) -> Vehicle:
        return Bike()

# Example usage

car_factory = CarFactory()
print(car_factory.move())

bike_factory = BikeFactory()
print(bike_factory.move())
```