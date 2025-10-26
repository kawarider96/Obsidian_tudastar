# ALU – Arithmetic Logic Unit (Aritmetikai-logikai egység)

Az **ALU (Arithmetic Logic Unit)** a CPU azon komponense, amely **az aritmetikai és logikai műveleteket** végzi.
Ez a központi számítóegység a **regiszterekben tárolt adatokkal** dolgozik, és az eredményt visszaírja a regiszterekbe vagy a cache-be.

---

## 🧮 Fő feladatai

| Művelettípus | Példa | Leírás |
|---------------|--------|---------|
| **Aritmetikai műveletek** | `ADD`, `SUB`, `MUL`, `DIV` | Összeadás, kivonás, szorzás, osztás |
| **Logikai műveletek** | `AND`, `OR`, `XOR`, `NOT` | Bitműveletek, logikai vizsgálatok |
| **Shift műveletek** | `SHL`, `SHR`, `SAR`, `ROL` | Bitelemek eltolása, rotálása |
| **Összehasonlítások** | `CMP`, `TEST` | Eredmény alapján módosítja a FLAGS biteket |

---

## ⚙️ Kapcsolat más egységekkel

- Az **ALU** a **Control Unit (CU)** utasításait hajtja végre.  
- Az operandusokat az **általános célú regiszterekből (GPR)** olvassa.  
- Az eredményt visszaírja a regiszterbe vagy az **L1D cache-be**.  
- Minden ALU művelet után a **FLAGS (RFLAGS)** frissül (pl. ZF, SF, CF, OF bitek).

---

## 🧠 Összefoglalás

| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Arithmetic Logic Unit |
| **Fő funkció** | Aritmetikai és logikai műveletek végrehajtása |
| **Bemenet** | Regiszterek (RAX–R15) |
| **Kimenet** | Regiszter / Cache |
| **Vezérli** | CU (Control Unit) |
| **Frissíti** | FLAGS / RFLAGS |
