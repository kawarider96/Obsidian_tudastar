# Mi az a Dockerfile?
A **Dockerfile** egy *build script*, amely lépésről lépésre leírja:
- milyen alap image-ből indulunk
- milyen fájlokat másolunk be
- milyen parancsokat futtatunk
- hogyan induljon el a konténer

👉 A Dockerfile **nem futásidő**, hanem **image-építési idő**.

---
# Mentális modell
> **Dockerfile = recept**  
> **Image = kész étel**  
> **Container = futó alkalmazás**

---

# Dockerfile alap utasítások (instructions)

## `FROM`
Alap image kiválasztása (kötelező, kivéve scratch).
```dockerfile
FROM node:20-alpine
```

Extra: [[Image]], 

### `WORKDIR`
Beállítja a munkakönyvtárat a konténeren belül.
```dockerfile
WORKDIR /app
```
Minden `RUN`, `COPY`, `CMD` innen számol.

### `COPY`
Fájlok másolása a hostról a konténerbe.
```dockerfile
COPY package.json .
COPY . .
```
✔️ Mindig `COPY`, nem `ADD` (kivéve speciális esetben).

### `RUN`
Build időben lefutó parancs.

```dockerfile
RUN npm install
```
⚠️ Minden `RUN` **új réteget** hoz létre.

### `CMD`
A konténer **alapértelmezett indítóparancsa**.
```dockerfile
CMD ["npm", "run", "start"]
```
✔️ Felülírható `docker run`-nal.

### `ENTRYPOINT`
„Ez maga az alkalmazás”.
```dockerfile
ENTRYPOINT ["node", "server.js"]
```
⚠️ Nehéz felülírni – ritkábban használd.

### `EXPOSE`
Dokumentációs jellegű port.
```dockerfile
EXPOSE 3000
```
❗ Nem nyit portot, csak jelzi.

### `ENV`
Futásidő környezeti változó.
```dockerfile
ENV NODE_ENV=production
```

### `ARG`
Build időben használt változó.
```dockerfile
ARG NODE_VERSION=20
```
⚠️ Futáskor már nem létezik.

### `USER`
Ne root-ként fusson az app.
```dockerfile
USER node
```
Biztonsági best practice.

### `HEALTHCHECK`
Konténer állapot ellenőrzés.
```dockerfile
HEALTHCHECK CMD curl -f http://localhost:3000 || exit 1
```

Teljes alap Dockerfile példa (Node.js)
```dockerfile
FROM node:20-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "run", "dev"]
```

## Multi-stage build (haladó, de fontos)

Cél:
- kisebb image
- build eszközök nélkül

```dockerfile
FROM node:20 AS builder
WORKDIR /app
COPY . .
RUN npm run build

FROM node:20-alpine
WORKDIR /app
COPY --from=builder /app/dist ./dist
CMD ["node", "dist/main.js"]
```

### .dockerignore (KÖTELEZŐ)
```dockerignore
node_modules
.git
.env
Dockerfile
```
👉 Olyan, mint a `.gitignore`, csak Docker buildhez.