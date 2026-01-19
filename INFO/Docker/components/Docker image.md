---
title: Docker image
tags:
  - docker
  - informatika
  - dev
  - programming
  - programozás
  - image
status: complete
created: 2026-01-17
---
# Mi az a Docker Image?

## 1️⃣ Mi ez? (nagyon egyszerűen)

A **Docker Image** egy **read-only sablon**, amiből **konténerek indulnak**.

> Ha nagyon le akarjuk butítani:  
> **Docker Image = előre összerakott alkalmazás + környezete**

Nem fut.  
Nem él.  
Nem csinál semmit.

Csak **létezik**, mint egy lefagyasztott állapot.

---

## 2️⃣ Miért létezik?

Azért, hogy:

- ne kelljen minden gépen újra telepíteni mindent
    
- az alkalmazás **ugyanúgy fusson mindenhol**
    
- a környezet is verziózható legyen, ne csak a kód
    

> [!info]
>  Docker Image nélkül minden app olyan lenne, mint:  
> „nálam megy, nálad nem”

---

## 3️⃣ Mentális modell (ezt érdemes megjegyezni)

> **Dockerfile = recept**  
> **Docker Image = kész étel (hidegen, becsomagolva)**  
> **Docker Container = amikor megeszed**

Vagy másképp:

> **Image = játék telepítő**  
> **Container = futó játék**

---

## 4️⃣ Mit TARTALMAZ egy Docker Image?

Egy image-ben tipikusan benne van:

- egy alap OS réteg (pl. Alpine, Debian)
    
- runtime (pl. Node, Python, PHP)
    
- telepített csomagok
    
- az alkalmazás fájljai
    
- alapértelmezett indítóparancs (`CMD` / `ENTRYPOINT`)
    

⚠️ Ami **nincs** benne:

- futó folyamat
    
- memória
    
- aktuális állapot
    

---

## 5️⃣ Hogyan jön létre egy Docker Image?

### 1️⃣ Van egy Dockerfile-od

```dockerfile
FROM node:20-alpine
WORKDIR /app
COPY . .
RUN npm install
CMD ["npm","run","start"]
```

### 2️⃣ Buildelsz

```bash
docker build -t my-app .
```

### 3️⃣ Eredmény

👉 létrejön egy **image**, neve:

```
my-app:latest
```

Ez még mindig **nem fut**.

---

## 6️⃣ Rétegek (layers) – a Docker Image lelke

Egy Docker Image **rétegekből áll**.

Minden Dockerfile sor kb. egy új réteg:

```dockerfile
FROM node:20-alpine   # layer 1
WORKDIR /app          # layer 2
COPY . .              # layer 3
RUN npm install       # layer 4
```

Ezek:

- egymásra pakolódnak
    
- cache-elhetők
    
- megoszthatók más image-ekkel
    

> Ezért gyors a Docker.

---

## 7️⃣ Miért read-only az Image?

Az image **soha nem változik**.

Amikor futtatod:

```bash
docker run my-app
```

akkor a Docker:

- fogja az image-et
    
- rátesz egy **írható réteget**
    
- ebből lesz a **container**
    

> Az image érintetlen marad.

---

## 8️⃣ Docker Image vs Container (nagyon fontos különbség)

|Docker Image|Docker Container|
|---|---|
|sablon|futó példány|
|read-only|írható|
|nem fut|fut|
|újrahasznosítható|ideiglenes|

Egy image-ből:

- 0
    
- 1
    
- vagy 1000 konténer is indulhat
    

---

## 9️⃣ Hol tárolódnak az Image-ek?

- lokálisan a gépeden
    
- vagy registry-ben
    

Példák:

- Docker Hub
    
- GitHub Container Registry
    
- saját privát registry
    

```bash
docker pull node:20-alpine
```

---

## 🔟 Miért fontos a KICSINY image?

Minél kisebb az image:

- gyorsabb build
    
- gyorsabb deploy
    
- kisebb támadási felület
    

Ezért:

- `alpine`
    
- multi-stage build
    
- felesleges fájlok kizárása
    

---

## Gyakori félreértések

- **„Az image fut.”** → nem, a container fut.
    
- **„Ha leállítom a konténert, elveszik az image.”** → nem.
    
- **„Az image-ben vannak az adatok.”** → nem, az adatok konténer/volume szintűek.
    

---

## 🧠 Gondolkodj el rajta:

- Miért jó, hogy egy image-ből több konténer is indulhat?
    
- Mi történne, ha az image írható lenne futás közben?
    
- Miért baj, ha egy prod image-ben benne van az npm és a forráskód?