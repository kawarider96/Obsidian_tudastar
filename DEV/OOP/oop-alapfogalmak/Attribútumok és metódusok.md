# Attribútumok és metódusok

Az **attribútumok** adatok (mezők), amelyeket egy objektum tárol. A **metódusok** olyan függvények, amelyek egy osztályon belül vannak definiálva.

## Példa

```python
class Ember:
    def __init__(self, nev):
        self.nev = nev  # attribútum

    def koszon(self):   # metódus
        return f"Szia, {self.nev}!"
```

- `nev`: attribútum
- `koszon()`: metódus

## Hozzáférés

```python
e = Ember("Krisz")
print(e.nev)        # Krisz
print(e.koszon())   # Szia, Krisz!
```

## Összegzés

- **Attribútum**: adattag, pl. `nev`, `kor`, `cim`
- **Metódus**: viselkedés, pl. `mozog()`, `beszel()`
