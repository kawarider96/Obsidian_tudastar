---
title: routing
created: 2026-01-17
tags:
  - informatika
  - nextjs
  - programming
  - programozás
  - javascript
  - react
  - routing
status: complete
---
## Hogyan működik? (mentális modell)

Képzeld el úgy, mintha az URL egy mappastruktúra lenne:

- `app/` = a webapp gyökere
    
- **mappa** = route szegmens (segment)
    
- `page.tsx` = „ez a szegmens egy oldal”
    
- `layout.tsx` = „ez a szegmens köré UI váz” (shell)
    
- `loading.tsx` = „amíg ez a szegmens tölt, ezt mutasd”
    

> [!info] 
> A kulcs: **a route nem 1 komponens**, hanem egy **fa** (layout-ok + page + egyéb speciális fájlok).

## Alap routing: `page.tsx`

**Struktúra → URL**

```
app/
  page.tsx              -> /
  about/
    page.tsx            -> /about
  blog/
    page.tsx            -> /blog
```

- Ha van egy mappában `page.tsx`, az egy navigálható oldal.
    
- Ha nincs `page.tsx`, de van pl. `layout.tsx`, akkor az a mappa „csak szervezés / shell”, önmagában nem oldal.

## Dinamikus route-ok: `[param]`

```
app/
  blog/
    [slug]/
      page.tsx          -> /blog/akarmi
```

A `page.tsx` megkapja a paramétereket (server componentként):

```ts
export default async function Page({ params }: { params: { slug: string } }) {
  return <div>Slug: {params.slug}</div>
}
```

### Catch-all: `[...param]`

```
app/
  docs/
    [...parts]/
      page.tsx          -> /docs/a/b/c
```

- `parts` tömb lesz: `['a','b','c']`

példa: 
```tsx
import Login from './_views/login'
import Auth from './_views/auth'
import Register from './_views/register'
import { notFound } from 'next/navigation'

export default function Page({ params }: { params: { parts?: string[] } }) {
  const parts = params.parts ?? []
  const first = parts[0] ?? 'index'

  if (first === 'login') return <Login />
  if (first === 'auth') return <Auth />
  if (first === 'register') return <Register />

  notFound()
}
```

> [!tip]
> Szó szerint ezt a mappa nevet kell neki adni `[...parts]`
> Majd a docs/ utvonal után bármilyen nested utvonalat megadhatok pl docs/install és a page.tsx ben ez kinyerhető
### Optional catch-all: `[[...param]]`

```
app/
  docs/
    [[...parts]]/
      page.tsx          -> /docs  és  /docs/a/b
```

## Route Groups: `(group)`

Ha szeretnél mappát csak szervezésre, URL nélkül:

```
app/
  (marketing)/
    landing/
      page.tsx          -> /landing
  (app)/
    dashboard/
      page.tsx          -> /dashboard
```

- A `(marketing)` és `(app)` **nem jelenik meg** az URL-ben.
    
- Olyan, mint egy „mappaszintű kategória”, ami nem lesz része a linknek.
    

---

# Layout: a „komponens váz” (component layout)
## Hogyan épül fel?

```
app/
  layout.tsx            -> root layout (mindenre érvényes)
  (app)/
    layout.tsx          -> csak az (app) group alá
    dashboard/
      layout.tsx        -> csak a /dashboard alá
      page.tsx
```

### Root layout minimál példa

```tsx
// app/layout.tsx
export default function RootLayout({ children }: { children: React.ReactNode }) {
  return (
    <html lang="hu">
      <body>
        <header>Globál header</header>
        <main>{children}</main>
      </body>
    </html>
  )
}
```


---

# Loading: globális, szegmens és komponens szint

## 1) Global loading (route-szintű, a gyökérben)

### Mit jelent itt a „global”?

Hogy **az egész app legfelső route-szegmensére** (a root-ra) van egy `loading.tsx`.

```
app/
  layout.tsx
  loading.tsx          -> „globális” route-loading
  page.tsx
```

### Mire jó?

- Ha akarsz egy **központi loading UI-t**, ami akkor látszik, amikor a root szegmens még streamel.
    
- Tipikus: teljes oldalas skeleton / spinner.
    

### Példa

```tsx
// app/loading.tsx
export default function Loading() {
  return (
    <div style={{ padding: 24 }}>
      <p>Betöltés…</p>
    </div>
  )
}
```

> Fontos: ez **nem ugyanaz**, mint „route change event listener spinner”.  
> Ez Suspense + streaming alapú „route segment fallback”.

## 2) Komponens / szegmens loading: `loading.tsx` mappán belül

Ha csak a dashboard részhez akarsz fallbacket:

```
app/
  (app)/
    dashboard/
      loading.tsx      -> csak /dashboard és alatta
      page.tsx
```

## 3) Component loading (komponens szint, nem route szint)

A route `loading.tsx` szuper, de néha egy oldalon belül is akarsz részleges töltést:

- egy nagy táblázat késik
    
- egy grafikon API-ra vár
    
- egy kliens komponens „nehéz”
    

### A) React Suspense fallback (komponens köré)

```tsx
import { Suspense } from 'react'

function SlowWidget() {
  // pl. server component data fetch
  return <div>Valós tartalom</div>
}

export default function Page() {
  return (
    <div>
      <h1>Dashboard</h1>

      <Suspense fallback={<div>Widget tölt…</div>}>
        {/* itt jön a lassú rész */}
        <SlowWidget />
      </Suspense>
    </div>
  )
}
```

### B) Dinamikus import + saját loading (kliens oldali „lusta betöltés”)

```tsx
import dynamic from 'next/dynamic'

const HeavyChart = dynamic(() => import('./HeavyChart'), {
  loading: () => <div>Chart tölt…</div>,
  ssr: false,
})

export default function Page() {
  return <HeavyChart />
}
```

> Mentális modell:
> 
> - `loading.tsx` = **routing szintű fallback**
>     
> - `Suspense/dynamic` = **komponens szintű fallback**
>     

---

# Extra (hasznos rokon speciális fájlok)

- `error.tsx` – hiba boundary egy route szegmenshez
    
- `not-found.tsx` – 404 UI (szegmens szint)
    
- `template.tsx` – mint a layout, de navigációnál **újra renderelődik** (ritkább, de néha kell)
    
- `route.ts` – API endpoint (Route Handler) az App Routerben
    

---

## Mire használjuk a valóságban?

- Tiszta, skálázható app struktúra (a mappák tényleg „térképek”)
    
- Per-rész UI shell (layout) → gyors, stabil UX
    
- Streaming + loading fallback → nem „white screen of death”
    
- Izolált hibakezelés szegmensenként
    
