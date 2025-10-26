# CPU Mag (Core)

Egy **CPU mag** a processzor legkisebb önálló végrehajtó egysége, amely **utasításokat hajt végre**.

---

## Fő részei
- **ALU (Arithmetic Logic Unit):** aritmetikai és logikai műveletek végrehajtása  
- **FPU (Floating Point Unit):** lebegőpontos számításokhoz  
- **CU (Control Unit):** vezérli az utasítások sorrendjét és az adatáramlást  
- **Regiszterek:** ultra gyors, kis méretű tárolók a műveletekhez szükséges adatoknak  
- **Cache-ek:** L1I, L1D, L2 (és közösen L3)

---

## Működési folyamat (fetch → decode → execute → write-back)
1. **Fetch:** a mag beolvassa az utasítást az L1I cache-ből.  
2. **Decode:** az utasítás gépi kódját értelmezi.  
3. **Execute:** az ALU/FPU végrehajtja a műveletet.  
4. **Write-back:** az eredményt visszaírja a regiszterekbe vagy a cache-be.

---

## Többmagos rendszerek
- Minden mag **önállóan képes programokat futtatni**.  
- A magok **párhuzamosan dolgoznak**, így több feladatot egyszerre képesek kezelni.  
- Az L3 cache általában **közös**, hogy megosszák az adatokat.

---

## Összefoglalás

| Összetevő | Funkció |
|------------|----------|
| **ALU** | Egész műveletek végrehajtása |
| **FPU** | Lebegőpontos számítások |
| **CU** | Utasításvezérlés |
| **Regiszterek** | Ultra gyors adat-elérés |
| **Cache** | Gyorsítótár (L1, L2, L3) |
