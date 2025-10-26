# L2 Cache

**Méret:** 256 KB – 1 MB  
**Cache line méret:** 64 bájt  
**Hozzáférési idő:** ~10 CPU ciklus  
**Hozzáférés típusa:** általában **magonként privát**, de egyes CPU-knál **megosztott lehet több mag között**.

---

## Feladata
Az **L2 cache** az **L1I és L1D** szintek kiterjesztése, nagyobb, de lassabb memória.  
Feladata az, hogy **adatokat és utasításokat egyaránt** tároljon, ha azok már kikerültek az L1 cache-ből, de még nem kellett visszaírni őket a RAM-ba.

---

## Fő jellemzők
- **Unifikált cache:** utasításokat és adatokat is tárol.  
- **Közvetítő réteg** az L1 és az L3 között.  
- Gyorsabb, mint a RAM, de lassabb, mint az L1.  
- **„Inclusive” vagy „exclusive”** működésű lehet (gyártófüggő).

---

## Összefoglalás

| Szint | Méret | Hozzáférési idő | Privát / Osztott | Tartalom |
|-------|--------|------------------|------------------|-----------|
| **L2** | 256 KB – 1 MB | ~10 ciklus | Többnyire privát | Adat + utasítás |
