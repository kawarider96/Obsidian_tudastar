---
title: Install
status: complete
created: 2026-01-17
tags:
  - informatika
  - nextjs
  - framework
  - install
  - javascript
  - frontend
---
## Új Next.js projekt létrehozása (EZ A LÉNYEG)

A hivatalos, ajánlott módszer:

`npx create-next-app@latest my-app`

Ez **nem telepít globálisan semmit**, csak elindít egy varázslót.

> [!tip] ha teljes telepités kell használd a `--yes` flaget

---

## 4) A varázsló kérdései – mit válaszolj?

A telepítő kérdez pár dolgot. Emberi nyelven:

- **TypeScript?** → IGEN
    
- **ESLint?** → IGEN
    
- **Tailwind CSS?** → IGEN (ha UI-t csinálsz)
    
- **App Router?** → **IGEN (kötelező)**
    
- **src/ mappa?** → ízlés kérdése
    

> [!info] 2025-ben nincs értelme App Router nélkül kezdeni.

Ha nem tudsz dönteni:

> [!tip] Nyomj Entert mindenre. A default setup korrekt.

---

## 5) Projekt indítása (feeling the magic)

Belépsz a projekt mappájába:

cd projekt-neve

Majd:

npm run dev

Ha ezt látod:

- `http://localhost:3000`
    

akkor:

> [!success] 🎉 A Next.js fut. Kész.