# Control Unit (CU) – Vezérlőegység

A **Control Unit (CU)** a CPU egyik legfontosabb alrendszere:  
ez **irányítja a teljes utasítás-végrehajtási folyamatot** a processzoron belül.  
Feladata, hogy **összehangolja** az aritmetikai (ALU), lebegőpontos (FPU), memóriakezelő és vezérlőegységek működését.

---

## 🧠 Fő feladatai

1. **Utasítások beolvasása (Fetch):**
   - A CU a **RIP (Instruction Pointer)** alapján beolvassa a következő utasítást az **L1I cache-ből** vagy RAM-ból.

2. **Utasítás dekódolása (Decode):**
   - Az utasítás bináris kódját **értelmezhető mikroutasításokká** bontja.
   - A dekódoló logika felismeri, hogy melyik egység (ALU, FPU, stb.) fogja végrehajtani a műveletet.

3. **Végrehajtás vezérlése (Execute Control):**
   - A CU **jelez** az ALU-nak, FPU-nak, és memóriavezérlőnek, hogy mit hajtsanak végre.
   - Irányítja az adatáramlást a **regiszterek**, **cache-ek** és **végrehajtó egységek** között.

4. **Időzítés és szinkronizáció:**
   - Gondoskodik róla, hogy az utasítások a **megfelelő sorrendben és ütemben** fussanak.
   - A **pipelining** és **superscalar** architektúrákban több műveletet futtat egyszerre, párhuzamosítva.

5. **Elágazásbecslés és vezérlésátvétel:**
   - A **branch predictor** segítségével megpróbálja **előre kitalálni**, merre fog futni a program (pl. if/else esetén).

6. **Hibakezelés és megszakításkezelés (Interrupt Control):**
   - A CU figyeli a megszakítási jeleket (IRQ, exceptions).
   - Ha megszakítás történik, **menti a CPU állapotát**, majd **ugrik** az IDT-ben meghatározott handlerhez.

---

## 🧩 A CU fő alkomponensei

| Alrendszer | Feladata |
|-------------|-----------|
| **Instruction Fetch Unit (IFU)** | Utasítások beolvasása a memóriából |
| **Instruction Decoder** | Bináris utasítás → mikroutasítások |
| **Scheduler (ütemező)** | Meghatározza, mely végrehajtó egység mikor dolgozik |
| **Branch Predictor** | Elágazások előrejelzése |
| **Control Logic / Sequencer** | Az összes egység összehangolása |
| **Interrupt Controller** | Megszakítások és kivételek kezelése |

---

## ⚙️ Kapcsolata más egységekkel

```
          +------------------------+
          |        CU (vezérlő)    |
          +------------------------+
           |  ↑    ↑     ↑     ↑
           |  |    |     |     |
           v  v    v     v     v
       [ ALU ] [ FPU ] [ AGU ] [ LSU ]
           |                    v          v
        [ Regiszterek ] → [ Cache hierarchia ]
```

A CU tehát a **„CPU agya”** – minden adatmozgást és számítást ő koordinál.

---

## 🧠 Összefoglalás

| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Control Unit |
| **Fő funkció** | A CPU egységeinek vezérlése és összehangolása |
| **Kapcsolódik** | ALU, FPU, AGU, LSU, Regiszterek, Cache |
| **Részei** | Fetch, Decode, Scheduler, Branch Predictor, Interrupt Controller |
| **Szint** | A CPU-mag logikai vezérlőrétege |
