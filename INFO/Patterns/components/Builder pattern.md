---
title: Builder pattern
tags:
  - informatika
  - pattern
  - design_pattern
  - programming
  - programozás
  - builder
  - architecture
status: complete
created: 2026-01-17
cover: "[[event-driven.png]]"
related: "[[Design patterns]]"
---
# Builder Pattern – „összerakjuk, nem összekeverjük”

**Cél:**  
Összetett objektumokat **lépésről lépésre**, kontrollált módon hozunk létre úgy, hogy az objektum konstrukciója **ne legyen kaotikus**.

> **Kulcsötlet:**  
> az objektum _felépítése_ legyen különválasztva attól, _mi_ az objektum.

---

## Mikor használd?

> [!info]
> 
> - Ha egy objektumnak **sok paramétere** van (különösen opcionálisak).
>     
> - Ha többféleképpen lehet ugyanazt az objektumot „összerakni”.
>     
> - Ha el akarod kerülni a 10 paraméteres konstruktort.
>     
> - Ha **láncolható, olvasható API-t** akarsz (`withX().withY()` stílus).
>     

Ha ilyet látsz:

```python
User(name, email, phone, address, age, role, status, created_at)
```

👉 Builder kell.

---

## A probléma, amit megold

### ❌ Konstruktor-hell

```python
user = User("Krisz", "kris@example.com", None, None, 28, "admin", True, datetime.now())
```

- olvashatatlan
    
- sorrendérzékeny
    
- hibára csábít
    

---

## A Builder alapötlete

```text
Builder -> lépésenként konfigurál -> build() -> kész objektum
```

- minden lépés **explicit**
    
- minden lépés **olvasható**
    
- a végén egy **kész, konzisztens objektum** jön létre
    

---

## Példa – egyszerű User Builder

### Domain objektum

```python
class User:
    def __init__(self, name: str, email: str):
        self.name = name
        self.email = email
```

### Builder

```python
class UserBuilder:
    def __init__(self):
        self._name = None
        self._email = None

    def with_name(self, name: str):
        self._name = name
        return self

    def with_email(self, email: str):
        self._email = email
        return self

    def build(self) -> User:
        return User(self._name, self._email)
```

### Használat

```python
user = (
    UserBuilder()
    .with_name("Krisz")
    .with_email("kris@example.com")
    .build()
)
```

👉 **önmagyarázó**, sorrendtől független, tiszta.

---

## Validáció a build() fázisban

> [!info]  
> A Builder egyik nagy ereje, hogy **a végén ellenőriz**.

```python
class UserBuilder:
    def build(self) -> User:
        if not self._name:
            raise ValueError("name kötelező")
        if not self._email:
            raise ValueError("email kötelező")
        return User(self._name, self._email)
```

👉 az objektum **soha nem lehet félkész**.

---

## Immutabilitás támogatása

> [!info]  
> A létrehozott objektum lehet teljesen immutábilis.

```python
class User:
    def __init__(self, name, email):
        self._name = name
        self._email = email

    @property
    def name(self): return self._name

    @property
    def email(self): return self._email
```

👉 módosítás csak **Builderen keresztül**.

---

## Builder vs Factory (gyakori kérdés)

|Builder|Factory|
|---|---|
|Lépésenként épít|Egy lépésben hoz létre|
|Sok paraméter|Kevés variáns|
|Konfiguráció fókusz|Példányosítás fókusz|

> **Builder = hogyan rakjuk össze**  
> **Factory = miből készül**

---

## Előnyök

> [!info]
> 
> - Nagyon olvasható kód
>     
> - Elkerüli a hosszú konstruktorokat
>     
> - Könnyű bővíteni új opciókkal
>     
> - Validáció egy helyen
>     

---

## Hátrányok

> [!warning]
> 
> - Több kód, több osztály
>     
> - Egyszerű objektumokra túlzás
>     

---

## Tipikus hiba

```python
user = UserBuilder()
user.with_name("Krisz")
user.with_email("kris@example.com")
user.build()
```

👉 ha **nem láncolsz**, elveszik az API előnye.

---

## Mentális modell

```mermaid
graph LR
    Client --> Builder
    Builder -->|build()| Object
```

---

## Egy mondatos összefoglaló

> **Builder = hagyd, hogy az objektum lépésről lépésre álljon össze, ne egy kaotikus konstruktorban szülessen meg.**