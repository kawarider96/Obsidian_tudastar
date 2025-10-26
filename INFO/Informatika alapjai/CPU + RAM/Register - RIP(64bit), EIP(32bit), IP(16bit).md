# RIP – Instruction Pointer Register

A **RIP (Instruction Pointer)** regiszter az x86-64 architektúrában a **következő végrehajtandó utasítás memória-címét** tárolja.  
Ez az egyik legfontosabb **speciális vezérlő- és állapotregiszter**, amely a CPU **vezérlési folyamatát** irányítja.

---

## 🧠 Fő funkció
- **Mindig a következő utasítás címét** tartalmazza, amit a **CU (Control Unit)** be fog olvasni az **L1I cache-ből**.
- Minden utasítás végrehajtása után a CPU automatikusan **megnöveli a RIP értékét** az utasítás hosszával.  
  (pl. ha egy utasítás 5 bájt, akkor `RIP = RIP + 5`)
- **Ugrásoknál (JMP, CALL, RET)** a RIP értékét manuálisan módosítják — így a vezérlés másik címre kerül.

---

## ⚙️ Példa

```asm
mov rax, 5
add rax, 7
jmp done
mov rax, 10
done:
```
- A `jmp done` módosítja a **RIP** értékét → a CPU a `done` címre ugrik.
- A köztes utasításokat már nem hajtja végre, mert a **RIP** új címet kapott.

---

## 🧩 Kapcsolata más egységekkel

| Kapcsolat | Leírás |
|------------|---------|
| **CU (Control Unit)** | A CU a RIP alapján olvassa be a következő utasítást. |
| **CS (Code Segment)** | A 16/32 bites módban a CS + RIP együtt adta meg a teljes címet. 64 biten a RIP önálló. |
| **ALU / FPU** | Ezek a végrehajtó egységek a CU által kijelölt utasítást hajtják végre; a RIP után frissül. |
| **OS / Scheduler** | A Windows loader és kernel a folyamat indításakor beállítja a RIP-et a program belépési pontjára. |

---

## 💾 A Windows indítási folyamatban

1. A Windows loader betölti a program kódját a virtuális címterületre.  
2. A loader beállítja a folyamat **thread context-jében** a kezdő **RIP**-et az entry point címére.  
3. Amikor a kernel ütemezi a szálat, a context switch során a **RIP** értéke betöltődik a CPU-ba.  
4. A CU innen kezd fetch-elni az utasításokat.

---

## 🧮 Hasonló regiszterek más módokban

| Architektúra | Regiszter | Szélesség |
|---------------|------------|-----------|
| 8086 / 80286 | IP | 16 bit |
| 80386 – Pentium | EIP | 32 bit |
| x86-64 | RIP | 64 bit |

---

## 🧠 Összefoglalás

| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Instruction Pointer |
| **Fő funkció** | Következő végrehajtandó utasítás címe |
| **Szélesség** | 64 bit |
| **Csoport** | Speciális vezérlő- és állapotregiszter |
| **Kapcsolódik** | CU, CS, ALU, OS loader |
| **Frissül** | Automatikusan minden utasítás után vagy ugráskor |
