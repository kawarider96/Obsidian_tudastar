# L1 Data Cache (L1D)

**Méret:** 32–64 KB  
**Cache line méret:** 64 bájt  
> A processzor mindig **64 bájtos blokkokat (cache line)** tölt be a memóriából.  
> Ha egy változóra hivatkozol, a CPU a körülötte lévő 64 bájtos adatblokkot is előtölti.

**Hozzáférési idő:** 1–4 CPU ciklus  
**Hozzáférés típusa:** minden maghoz **külön privát L1D cache** tartozik

---

## Feladata
Az **L1 data cache (L1D)** tárolja azokat az adatokat, amelyekkel az adott mag éppen dolgozik — például:
- változók, tömbök, pointerek,
- stack és heap memóriaterületek,
- gyakran elért memória-címek (pl. ciklusban használt tömb-elemek).

---

## Példák

```c
int x = 5;
```
➡️ Az `x` értéke az L1D-ben tárolódhat, így a mag nagyon gyorsan hozzáfér.

```c
sum += array[i];
```
➡️ Az `array[i]` elem jellemzően L1D-ből kerül kiolvasásra (ha korábban betöltődött).

```c
scanf("%d", &x);
```
➡️ A bemeneti érték először a RAM-ból érkezik, majd az L1D cache-be kerül feldolgozás céljából.

**További példák:**
- Stack változók: `int a` egy függvényen belül  
- Globális változók (ha aktívan használtak)  
- Heap memória: `malloc()` / `new` által lefoglalt adatok

---

## Kapcsolat az L1I-vel
- Az **L1I cache** (Instruction cache) az utasításokat (kódot) tárolja.  
- Az **L1D cache** az adatokat (változókat) tárolja.  
- Mindkettő az adott maghoz tartozik, de **külön memóriaterület**.

---

## Működési logika

1. A CPU **először az L1D cache-ben keres** adatot.  
2. Ha nincs ott → **L2 cache**, majd **L3 cache**, végül **RAM**.  
3. Ha egy adat megváltozik, a **cache line „piszkossá” (dirty) válik**, és később visszaíródik a következő szintre.

---

## Összefoglalás

| Szint | Méret | Hozzáférési idő | Osztott / Privát | Tartalom |
|-------|--------|------------------|------------------|-----------|
| **L1D** | 32–64 KB | 1–4 ciklus | Privát | Adatok (változók, tömbök, stack) |
| **L1I** | 32–64 KB | 1–4 ciklus | Privát | Utasítások (kód) |
| **L2** | 256 KB – 1 MB | ~10 ciklus | Privát | Adat + utasítás |
| **L3** | 2–64 MB | ~30–50 ciklus | Osztott | Adat + utasítás |
