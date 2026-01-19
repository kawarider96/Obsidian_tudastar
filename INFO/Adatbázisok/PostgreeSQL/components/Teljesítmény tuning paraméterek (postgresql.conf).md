# Teljesítmény tuning – postgresql.conf

Fontosabb beállítások a teljesítmény finomhangolásához.

## Memória

 ## **shared_buffers:** 
 Ez a PostgreSQL által **belső cache-ként** fenntartott memória. Itt tárolja a gyakran elért adatblokkokat. Minél nagyobb, annál kevesebbszer kell a diszkhez nyúlnia.
- Általános szabály: a gép memóriájának ~25–40%-a ideális.
- Példa: ha van 8 GB RAM, akkor 2 GB körül már erősen érdemes adni neki.

### **work_mem:**
Ez a **munkamemória egy lekérdezés művelethez** (pl. `ORDER BY`, `JOIN`, `HASH`, `AGGREGATE`). Ha túl alacsony, akkor ideiglenes fájlokat ír diszkre → lassulás.
- Fontos: ez _nem globális_, hanem **műveletenként**, lekérdezésenként értendő.
- Nagyobb `work_mem` = kevesebb diszkírás → gyorsabb JOIN/ORDER.

**maintenance_work_mem:**
Ez a memória használatos **karbantartási műveletekhez**, pl. `VACUUM`, `CREATE INDEX`, `ALTER TABLE`.
- Nagy érték gyorsítja ezeket, de csak ritkán használódik.
- Növeld, ha gyakran csinálsz tömeges indexelést vagy sok `VACUUM`-ot futtatsz.
```conf
shared_buffers = 512MB
work_mem = 4MB
maintenance_work_mem = 64MB
```

## Párhuzamosítás

**max_parallel_workers:**
Ez a lekérdezéseken belüli **párhuzamos feldolgozó szálak maximális száma**.
- Hasznos nagy tábláknál, `JOIN`, `AGGREGATE`, `CTE` esetén.
- Több magos CPU esetén érdemes 4–8 közé állítani.

**parallel_setup_cost:**
Ez egy belső becslési súly a párhuzamosítás aktiválásához. Minél **kisebb** ez az érték, annál **gyakrabban** engedi be a párhuzamos feldolgozást.
- Csökkentsd pl. `200`-ra, ha biztosan szeretnél több lekérdezést párhuzamosítani.
- Alapértelmezett: `1000`, ami gyakran túlságosan konzervatív.

```conf
max_parallel_workers = 4
parallel_setup_cost = 1000
```

## Checkpoint beállítás

**checkpoint_completion_target:**
Megadja, hogy egy checkpoint ciklus (lemezre írás) **milyen lassan történjen meg** az időintervallumon belül.
- 0.9 = 90%-áig teríti szét → kevesebb hirtelen IO-tüske.
- Javasolt érték: `0.7–0.9` – minél közelebb 1-hez, annál simább az írás.

**checkpoint_timeout:**
Ez a **checkpoint gyakoriságának időalapja** – azaz mennyi időnként írja ki kötelezően a RAM-ban lévő változásokat lemezre.
- Túl gyakori = sok írás, lassulás
- Túl ritka = sok adat elveszhet hiba esetén (log-alapú helyreállításig)
```conf
checkpoint_completion_target = 0.9
checkpoint_timeout = 10min
```

## Autovacuum

**autovacuum:**
Ez kapcsolja be az **automatikus `VACUUM` és `ANALYZE`** folyamatokat, amik tisztítják és frissítik a táblákat.
- Alapértelmezetten be van kapcsolva, ne kapcsold ki!

**autovacuum_naptime:**
Ez határozza meg, hogy **milyen időközönként** vizsgálja meg a rendszer, hogy szükséges-e `VACUUM` vagy `ANALYZE`.
- Alapérték: `1min` → teljesen jó a legtöbb esetben
- Túl alacsony érték = túl sok futás
- Túl magas = halmozódó „szemét” rekordok → lassulás
```conf
autovacuum = on
autovacuum_naptime = 1min
```
