Az **osztály** (class) egy sablon, amely leírja, hogyan nézzen ki és viselkedjen egy adott típusú objektum. A **példány** (instance) az osztály alapján létrehozott konkrét objektum.

## Példa

```python
class Auto:
    def __init__(self, szin):
        self.szin = szin

# Példány létrehozása
a1 = Auto("piros")
a2 = Auto("kék")
```

- `Auto` → osztály (sablon)
- `a1`, `a2` → példányok (objektumok)
- `szin` → példányhoz tartozó attribútum

## Ellenőrzés

```python
print(type(a1))        # <class '__main__.Auto'>
print(isinstance(a1, Auto))  # True
```

## Lényeg

- Egy osztály: definíció (szerkezet + viselkedés)
- Egy példány: konkrét objektum az osztály alapján
