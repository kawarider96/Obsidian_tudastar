# Observer pattern

Ez a minta lehetővé teszi, hogy egy objektum értesítse a „figyelőit” (observer-eket), ha valami megváltozik benne.

## Mikor használd?

- Ha több objektumot szeretnél automatikusan értesíteni egy állapotváltozásról.
- Ha lazán csatolt eseménykezelést akarsz.

## Példa

```python
class Subject:
    def __init__(self):
        self.observers = []

    def attach(self, obs):
        self.observers.append(obs)

    def notify(self):
        for obs in self.observers:
            obs.update()

class Observer:
    def update(self):
        print("Értesítve lettem!")

# Használat
s = Subject()
s.attach(Observer())
s.notify()  # Értesítve lettem!
```

## Előnyök

- Eseményvezérelt rendszerek alapja
- Lazán csatolt

## Hátrányok

- Nehéz debuggolni, ha sok observer van
