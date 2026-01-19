---
title: Docker YML
tags:
  - docker
  - informatika
  - programming
  - programozás
  - yml
status: complete
created: 2026-01-17
---
# Mi az a `docker-compose.yml`?

## 1️⃣ Mi ez? (nagyon egyszerűen)

A **`docker-compose.yml`** egy fájl, ami **több konténert egyszerre** ír le és indít el.

> Ha nagyon leegyszerűsítjük:  
> **docker-compose = több `docker run` egy fájlban**

Nem buildel magától (kivéve ha mondod neki).  
Nem futtat appot önmagában.  
Csak **leírja**, mi hogyan induljon.

---

## 2️⃣ Miért létezik?

Mert a valós appok **nem egy konténerből állnak**.

Egy tipikus web app:

- frontend
    
- backend
    
- adatbázis
    
- cache
    

Docker nélkül:

- 5 terminál
    
- 10 parancs
    
- káosz
    

Docker Compose-szal:

```bash
docker compose up
```

👉 minden elindul **egyben**.

---

## 3️⃣ Mentális modell (EZ A LÉNYEG)

> **docker-compose.yml = rendszer tervrajz**
> 
> Nem konténer,  
> nem image,  
> hanem **kapcsolatok + szabályok** leírása.

Másképp:

> **Compose = mini-orchestrátor** (lokálra)

---

## 4️⃣ Mit ír le a compose?

Egy `docker-compose.yml` tipikusan ezt:

- milyen service-ek vannak
    
- melyik milyen image-ből indul
    
- buildel-e vagy csak futtat
    
- milyen portokon érhető el
    
- milyen volume-okat használ
    
- hogyan látják egymást hálózaton
    

---

## 5️⃣ Alap szerkezet

```yaml
services:
  app:
    image: node:20
    ports:
      - "3000:3000"
```

- `services` = futó komponensek
    
- **1 service ≈ 1 konténer**
    

---

## 6️⃣ `image` vs `build`

### `image`

```yaml
image: node:20
```

- meglévő image
    
- nem buildel

> [!tip]
> Ez akkor kell ha olyan image-et azaz programot akarsz amit nem te programozol hanem csak használsz PL: Adatbázisok

### `build`

```yaml
build:
  context: .
  dockerfile: Dockerfile.dev
```

A `context` az a **könyvtár**, amit a Docker:

- **becsomagol**
    
- **elküld** a Docker daemonnek
    
- és **CSAK ebből** a csomagból dolgozhat a build során
    

> A Docker **nem látja a teljes gépedet**.  
> Csak azt, amit a contextbe beteszel.

- Dockerfile-ból buildel
    
- majd abból indít konténert
    

👉 A kettő **nem ugyanaz**, de választható.

> [!tip]
> Ez akkor kell ha olyan image-et azaz programot akarsz amit te készítesz pl egy backend vagy frontend vagy akármi amiben majd programozol.

---

## 7️⃣ `ports` – hogyan éred el a hostról?

```yaml
ports:
  - "5173:5173"
```

Bal oldal: **host port**  
Jobb oldal: **container port**

> Ha nincs `ports`, a konténer fut, de kívülről nem éred el.

---

## 8️⃣ `volumes` – adat és kód kezelése

```yaml
volumes:
  - .:/app
  - db_data:/var/lib/postgresql/data
```

- bind mount → fejlesztés
    
- named volume → adat
    

👉 Compose nélkül ezeket külön kéne kézzel összedrótozni.

---

## 9️⃣ Service-ek közti hálózat

Compose automatikusan:

- csinál egy hálózatot
    
- minden service lát minden mást **név alapján**
    

```yaml
backend:
frontend:
```

Frontend eléri a backendet így:

```
http://backend:3000
```

👉 **NEM localhost**.

---

## 🔟 `depends_on` – indítási sorrend

```yaml
depends_on:
  - db
```

- csak az indítás sorrendjét garantálja
    
- **nem** várja meg, hogy az app készen legyen
    

---

## 11️⃣ DEV vs PROD Compose

### DEV

- volume mount
    
- hot reload
    
- debug
    

### PROD

- nincs mount
    
- kész image-ek
    
- read-only
    

👉 Gyakran **külön compose fájl**.

---

## 12️⃣ Tipikus példa (full stack dev)

```yaml
services:
  frontend:
    build:
      context: ./frontend
      dockerfile: Dockerfile.dev
    ports:
      - "5173:5173"
    volumes:
      - ./frontend:/app

  backend:
    build:
      context: ./backend
    ports:
      - "8000:8000"

  db:
    image: postgres:16
    volumes:
      - db_data:/var/lib/postgresql/data

volumes:
  db_data:
```

---

## Gyakori félreértések

- „A compose build tool” → nem
    
- „A service = image” → nem
    
- „localhost-tal elérem a másik service-t” → nem
    
- „Prodra ugyanígy jó” → nem mindig
    

---

## 🧠 Gondolkodj el rajta:

- Miért service névvel kommunikálnak a konténerek?
    
- Mi történik, ha két service ugyanazt a portot akarja publikálni?
    
- Miért veszélyes prod-ban bind mountot használni?
    

---

> **Ha a compose-t érted, akkor rendszerekben gondolkodsz, nem konténerekben.**