# Domain-Driven Organization (DDO)

A projektstruktúrát a domain szerint szervezzük, nem technikai rétegek szerint. Ez egy "szervezési elv", ami gyakran kapcsolódik Domain-Driven Designhoz (DDD).

## Mikor használd?

- Ha moduláris, jól elkülönített komponenseket akarsz.
- Ha a domain logika a fejlesztés középpontjában áll.
- Mikroservice vagy moduláris monolit építésekor.

## Példa struktúra

```
orders/
  ├── domain/
  ├── application/
  ├── infrastructure/
users/
payments/
```

## Előnyök

- Könnyebb karbantartás
- Kódösszefüggések egy helyen maradnak
- Skálázható – akár külön deployolható modulokká

## Hátrányok

- Kezdőknek szokatlan
- Refaktorálás során következetesség kell
