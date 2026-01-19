---
title: Flyweight pattern
tags:
  - informatika
  - pattern
  - architecture
  - programming
  - programozás
  - dev
  - flyweight
status: complete
created: 2026-01-17
related: "[[Design patterns]]"
cover: "[[client-server.png]]"
---
# Flyweight Pattern – „ne ugyanazt tárold ezerszer”

**Cél:**  
Nagy mennyiségű, hasonló objektum esetén a **közös (intrinsic) állapotot megosztjuk**, hogy **memóriát spóroljunk**.

> **Kulcsötlet:**  
> válaszd szét az **állandó (megosztható)** és a **változó (külső)** állapotot.

---

## Mikor használd?

> [!info]
> 
> - Ha **nagyon sok** azonos vagy hasonló objektumod van.
>     
> - Ha a memóriahasználat valódi probléma.
>     
> - Ha az objektum állapotának egy része **minden példányban ugyanaz**.
>     

Tipikus helyzet:

```text
10 000 karakter
10 000 fa a játékban
10 000 ikon a UI-ban
```

👉 Flyweight jöhet szóba.

---

## A probléma, amit megold

### ❌ Naiv megoldás

```python
letters = [Letter('a') for _ in range(10000)]
```

- ugyanaz az adat ezerszer tárolva
    
- felesleges memóriahasználat
    

---

## Intrinsic vs Extrinsic állapot

> [!info]  
> Ez a minta **lelke**.

|Állapot típusa|Jelentés|Hol van?|
|---|---|---|
|Intrinsic|megosztható, állandó|Flyweight objektumban|
|Extrinsic|példányonként változó|kliens adja át|

Példa:

- **betű alakja** → intrinsic
    
- **pozíció a képernyőn** → extrinsic
    

---

## Flyweight alapötlet

```text
FlyweightFactory
 └─ visszaad meglévő példányt vagy létrehoz újat
```

- objektumok cache-elése
    
- új példány csak akkor, ha még nincs
    

---

## Egyszerű példa – Letter

```python
class Letter:
    _instances = {}

    def __new__(cls, char: str):
        if char not in cls._instances:
            cls._instances[char] = super().__new__(cls)
            cls._instances[char].char = char
        return cls._instances[char]
```

### Használat

```python
a1 = Letter('a')
a2 = Letter('a')

print(a1 is a2)  # True
```

👉 ugyanaz a példány, ugyanarra az állapotra.

---

## Teljesebb példa – extrinsic állapottal

```python
class Letter:
    def __init__(self, char):
        self.char = char

    def draw(self, x: int, y: int):
        print(f"{self.char} at ({x},{y})")

class LetterFactory:
    _cache = {}

    @classmethod
    def get(cls, char: str) -> Letter:
        if char not in cls._cache:
            cls._cache[char] = Letter(char)
        return cls._cache[char]
```

```python
letter = LetterFactory.get('a')
letter.draw(10, 20)
letter.draw(30, 40)
```

👉 a pozíció **nem** a flyweight része.

---

## Való élet példák

> [!info]
> 
> - karakterek renderelése (font engine)
>     
> - game engine objektumok (fák, kövek)
>     
> - string interning
>     
> - cache-elt konfigurációk
>     

---

## Flyweight vs Singleton (fontos!)

|Flyweight|Singleton|
|---|---|
|Sok megosztott példány|Egyetlen példány|
|Kulcs alapján|Globális|
|Memóriaoptimalizálás|Hozzáférés kontroll|

---

## Előnyök

> [!info]
> 
> - Jelentős memória-megtakarítás
>     
> - Gyorsabb példányosítás
>     

---

## Hátrányok

> [!warning]
> 
> - Bonyolultabb logika
>     
> - Kliensnek kezelnie kell az extrinsic állapotot
>     

---

## Tipikus hiba

```python
class Letter:
    def __init__(self, char, x, y):
        self.char = char
        self.x = x
        self.y = y
```

👉 ha az extrinsic állapot bent van, **nem Flyweight**.

---

## Mentális modell

```mermaid
graph LR
    Client --> FlyweightFactory
    FlyweightFactory --> Flyweight
```

---

## Egy mondatos összefoglaló

> **Flyweight = oszd meg, ami közös, és add át kívülről, ami változik.**