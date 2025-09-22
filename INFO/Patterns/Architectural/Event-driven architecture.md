# Event-driven architecture

A komponensek események (eventek) mentén kommunikálnak – nincs direkt hívás, csak válasz egy eseményre.

## Mikor használd?

- Ha aszinkron működésre van szükség
- Ha skálázható, laza csatolású rendszert akarsz

## Példa

- Felhasználó regisztrál → `user_registered` event → több rendszer reagál rá

## Előnyök

- Laza csatolás
- Jó skálázhatóság

## Hátrányok

- Hibakezelés komplex
- Nehéz követni a folyamatokat (debug, trace)
