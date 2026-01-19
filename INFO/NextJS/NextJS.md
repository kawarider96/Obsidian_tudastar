---
title: NextJS
tags:
  - programming
  - programozás
  - dev
  - informatika
  - javascript
  - frontend
  - nextjs
  - library
  - framework
status: progress
created: 2026-01-17
---
# Next.js

## 1) Mi ez? (1 mondatban)

A **Next.js** egy **React-re épülő keretrendszer**, ami segít **valódi webalkalmazást** csinálni: oldalankénti útvonalak (routing), szerveroldali renderelés, API-k, build, optimalizálás – mind egyben.

> [!info]  
> Ha a React „LEGO kocka”, akkor a Next.js a „kész LEGO készlet dobozzal, útmutatóval és rendszerezővel”.

---

## 2) Miért létezik? (milyen problémát old meg)

A sima React (pl. Vite/CRA) nagyon jó UI-hoz, de egy komplett webappnál jönnek a kérdések:

- **Hogyan legyenek oldalak?** (routing)
    
- **Hogy legyen gyors a betöltés?** (SEO + performance)
    
- **Honnan jöjjön az adat?** (szerver, API)
    
- **Képek, fontok, cache, build?**
    

A Next.js ezekre ad egy **rendszer-szintű választ**, hogy ne neked kelljen mindent 20 libből összerakni.

> [!tip]  
> Next.js akkor a legjobb, ha nem csak „egy SPA UI-t” akarsz, hanem **teljes webalkalmazást**.

---

## 3) Hogyan működik? (lépésről lépésre)

A Next.js lényege: **a React komponenseidből oldalak lesznek**, és a rendszer eldönti, hogy mi fusson **a böngészőben**, és mi fusson **a szerveren**.

### 3.1. File-based routing (az útvonalak fájlokból jönnek)

Next-ben az appod útvonalai mappastruktúrából állnak.

- `app/page.tsx` → `/`
    
- `app/about/page.tsx` → `/about`
    
- `app/blog/[slug]/page.tsx` → dinamikus útvonal: `/blog/valami`
    

> [!info]  
> **Nem te írod kézzel a route táblát.** A fájlnevek/mappák jelentik az útvonalat.

### 3.2. Két „világ”: Server Components vs Client Components

Next (App Router) alapból **szerveren renderel**.

- **Server Component** (alapértelmezett): gyors, mehet adatbázis/API hívás, nem kerül a JS bundle-be úgy, mint a kliens logika.
    
- **Client Component**: ha kell interaktivitás (state, onClick, useEffect), akkor a fájl tetejére: `"use client"`.
    

> [!warning]  
> Ha mindent kliensre raksz (`use client` mindenhol), akkor Next-ből csinálsz egy nehezebb SPA-t, és elveszted az egyik legnagyobb előnyét.

### 3.3. Adatbetöltés

Server oldalon simán tudsz adatot kérni (fetch, DB, stb.), és a komponens a kész UI-t adja vissza.

Példa mentális modell:

- oldalt megnyitod → Next a szerveren összerakja a HTML-t → böngésző gyorsan megkapja → ahol kell, ott jön a kliens JS az interaktivitáshoz.
    

### 3.4. Rendering módok (SSG / SSR / ISR – emberi nyelven)

A Next többféleképp tud oldalt „legyártani”:

- **SSG (Static)**: buildkor legenerálja. Szuper gyors.
    
- **SSR (Server)**: minden kérésnél szerver számolja. Friss adat, de drágább.
    
- **ISR (Incremental Static Regeneration)**: statikus, de időnként újragenerálja (okos kompromisszum).
    

> [!tip]  
> Mentális szabály:
> 
> - Ha ritkán változik → **Static/ISR**
>     
> - Ha mindig friss kell → **SSR**
>     

### 3.5. API és „backend” a Next-ben

Next-ben csinálhatsz **API endpointokat** is.

- `app/api/hello/route.ts` → `/api/hello`
    

Ez akkor király, ha:

- kis backend kell a frontend mellé,
    
- vagy BFF (Backend For Frontend) stílusban akarsz a kliensnek „könnyen emészthető” API-t adni.
    

> [!warning]  
> Nagy rendszernél sokszor jobb külön backend (pl. Laravel / Node / Go), és a Next csak frontend. De prototípushoz / kisebb apphoz a Next API tök jó.

---

## 4) Mire jó a valóságban?

Tipikus Next.js use-case-ek:

- **Marketing site + blog + landingek** (SEO fontos)
    
- **Dashboardok** (auth, role-ok, sok adat)
    
- **E-commerce** (termékoldalak, gyors betöltés)
    
- **SaaS appok** (login, fizetés, admin felület)
    

> [!info]  
> Next erőssége: _tud SEO-kompatibilis és gyors lenni_, miközben React marad a UI.

---

## 5) Hol találkozol vele programozásban / rendszerekben?

- **React ökoszisztéma**: komponensek, state, props, stb.
    
- **Node.js futtatókörnyezet**: a szerveroldali részeknél.
    
- **Deploy platformok**: Vercel (klasszik), de mehet Docker/Kubernetes, VPS is.
    
- **Auth**: NextAuth, saját JWT/cookie session, vagy külső provider.
    
- **Adat**: REST/GraphQL, Prisma, Drizzle, saját backend API.
    

---

## Gyakori félreértések

- **„A Next.js = React?”**
    
    - Nem. A Next React-re épül, de **keretrendszer**: routing, rendering stratégiák, build, optimalizáció.
        
- **„A Next mindig SSR?”**
    
    - Nem. Tud static/ISR/SSR/kevert módot is.
        
- **„A szerver = külön backend?”**
    
    - Nem feltétlen. Next-ben is lehet szerver logika, de nagy appnál sokan külön backendet használnak.
        
- **„Ha van Next, nem kell API?”**
    
    - De kellhet. Next API route-ok kényelmesek, de nem csodaszer.
        

---

## Mini cheat sheet (nagyon röviden)

- **Oldalak**: `app/.../page.tsx`
    
- **Dinamikus route**: `app/blog/[slug]/page.tsx`
    
- **API route**: `app/api/.../route.ts`
    
- **Interaktív komponens**: fájl teteje: `"use client"`
    

---

## 🧠 Gondolkodj el rajta:

- Ha egy oldalad adatát **5 percenként** elég frissíteni, melyik rendering módot választanád (Static / ISR / SSR), és miért?
    
- Melyik részt tennéd **kliensre**, és melyiket **szerverre**, ha az a cél, hogy gyors legyen, de interaktív is?