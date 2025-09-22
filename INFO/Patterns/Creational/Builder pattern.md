# Builder pattern

A Builder minta lehetővé teszi, hogy összetett objektumokat lépésről lépésre, kontrollált módon hozzunk létre.

## Mikor használd?

- Ha sokféle paraméterrel rendelkező objektumot kell létrehozni.
- Ha ugyanazt az objektumot többféleképpen kell „összerakni”.
- Ha olvashatóbb, láncolható szintaxist akarsz (pl. `withX().withY()`).

## Példa (pszeudokód)

```python
class UserBuilder:
    def __init__(self):
        self.name = ""
        self.email = ""

    def with_name(self, name):
        self.name = name
        return self

    def with_email(self, email):
        self.email = email
        return self

    def build(self):
        return User(self.name, self.email)

# Használat
user = UserBuilder().with_name("Krisz").with_email("kris@example.com").build()
```

## Előnyök

- Olvashatóság
- Testreszabhatóság
- Immutabilitás támogatása

## Hátrányok

- Több osztály létrehozása
- Bonyolultabb kezdőknek
