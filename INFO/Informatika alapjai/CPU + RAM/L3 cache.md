# L3 Cache

**Méret:** 2–64 MB (processzortól függően)  
**Cache line méret:** 64 bájt  
**Hozzáférési idő:** 30–50 CPU ciklus  
**Hozzáférés típusa:** **osztott cache**, a magok közösen használják.

---

## Feladata
Az **L3 cache** egy **nagy, közös gyorsítótár**, amely az összes mag között megosztott.  
Célja, hogy csökkentse a fő memória (RAM) elérésének gyakoriságát, és **összehangolja a magok közötti adatkommunikációt**.

---

## Fő jellemzők
- **Megosztott cache** az összes CPU-mag között.  
- **Konzisztencia fenntartása:** biztosítja, hogy minden mag ugyanazt az adatverziót lássa.  
- **Késleltetettebb**, de nagy kapacitású.  
- Kritikus szerepe van a **multithread** (többszálú) programok teljesítményében.

---

## Összefoglalás

| Szint | Méret | Hozzáférési idő | Privát / Osztott | Tartalom |
|-------|--------|------------------|------------------|-----------|
| **L3** | 2–64 MB | 30–50 ciklus | Osztott | Adat + utasítás |
