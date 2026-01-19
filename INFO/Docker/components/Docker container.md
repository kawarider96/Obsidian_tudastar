---
title: Docker container
tags:
  - informatika
  - docker
  - container
  - programming
  - programozás
  - dev
status: complete
created: 2026-01-17
---
# Mi az a Docker Container?

## 1️⃣ Mi ez? (nagyon egyszerűen)

A **Docker Container** egy **futó példány** egy Docker Image-ből.

> Ha nagyon leegyszerűsítjük:  
> **Container = elindított image**

- fut
    
- processzek vannak benne
    
- van saját állapota
    

---

## 2️⃣ Miért létezik?

Azért, hogy az image:

- **életre keljen**
    
- izolált környezetben fusson
    
- ne piszkítsa össze a host rendszert
    

> Image nélkül nincs container.  
> Container nélkül az image csak egy fájlhalmaz.

---

## 3️⃣ Mentális modell (ezt jegyezd meg)

> **Dockerfile = recept**  
> **Docker Image = kész étel (hideg)**  
> **Docker Container = evés közben az étel**

Másik hasonlat:

> **Image = játék telepítő**  
> **Container = futó játék egy konkrét mentéssel**

---

## 4️⃣ Hogyan jön létre egy container?

### 1️⃣ Van egy image-ed

```bash
docker images
```

### 2️⃣ Elindítod

```bash
docker run my-app
```

Ekkor a Docker:

1. fogja az image-et
    
2. rátesz egy **írható réteget**
    
3. elindítja a `CMD` / `ENTRYPOINT`-ot
    

👉 megszületik a **container**

---

## 5️⃣ Mi fut egy containerben?

Egy containerben:

- **processzek futnak** (pl. node, nginx)
    
- van saját PID namespace
    
- van saját filesystem (image + írható layer)
    

⚠️ Nem egy mini VM!

- nincs saját kernel
    
- a host kernelét használja
    

---

## 6️⃣ Mi az az írható réteg?

A container:

- az image **read-only** rétegeire épül
    
- kap egy **writable layer**-t
    

Minden, ami futás közben történik:

- log fájl
    
- ideiglenes fájl
    
- cache
    

👉 ebbe az írható rétegbe kerül

Ha a container leáll:

- ez az állapot **eldobható**
    

---

## 7️⃣ Container életciklus

```text
IMAGE
  ↓ docker run
CONTAINER (running)
  ↓ docker stop
CONTAINER (stopped)
  ↓ docker rm
TÖRÖLVE
```

Az image **érintetlen marad** végig.

---

## 8️⃣ Mi történik, ha leáll a container?

- a processzek megállnak
    
- az írható réteg megmarad (amíg nem törlöd)
    

```bash
docker stop my-container
docker start my-container
```

De:

- ha **törlöd** (`docker rm`)
    
- minden futás közbeni adat **elveszik**
    

👉 ezért vannak a **volume-ok**.

---

## 9️⃣ Egy image → több container

Ugyanabból az image-ből:

```bash
docker run my-app
docker run my-app
docker run my-app
```

👉 három **független** container indul

- külön processzek
    
- külön állapot
    
- az image közös
    

---

## 🔟 Container vs Virtual Machine

|Container|VM|
|---|---|
|gyors indulás|lassú indulás|
|közös kernel|saját kernel|
|könnyű|nehéz|
|app szintű izoláció|OS szintű izoláció|

---

## Gyakori félreértések

- **„A container egy VM.”** → nem.
    
- **„Ha kilépek, minden megmarad.”** → nem (volume nélkül).
    
- **„A containerben módosított fájl az image-ben is megváltozik.”** → nem.
    

---

## 🧠 Gondolkodj el rajta:

- Miért jó, hogy a container írható, de az image nem?
    
- Mi történne, ha egy container soha nem állna le?
    
- Miért nem jó adatbázist volume nélkül futtatni?