# LSU – Load Store Unit (Memória-műveleti egység)

Az **LSU (Load Store Unit)** a CPU azon egysége, amely a **memóriából történő olvasást és írást** kezeli.
Amikor a program adatot tölt be vagy tárol a RAM-ban, az LSU végzi el a tényleges adatmozgatást.

---

## 🧮 Fő feladatai

| Művelet | Példa | Leírás |
|----------|--------|--------|
| **Load** | `MOV RAX, [RBX]` | Betölti az adatot a memóriából a regiszterbe |
| **Store** | `MOV [RCX], RAX` | Kiírja az adatot a regiszterből a memóriába |
| **Prefetch / Write-back** | Automatikus cache-kezelés | Az L1D cache és RAM szinkronizálása |

---

## ⚙️ Működés

- Az **AGU** kiszámítja a címet, az **LSU** végzi a tényleges olvasást/írást.  
- Az **L1D cache** az első szint, ahol az LSU adatot keres.  
- Ha az adat nincs az L1-ben, az LSU a **L2 / L3 cache** felé vagy RAM-ba fordul.

---

## 🧠 Összefoglalás

| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Load Store Unit |
| **Fő funkció** | Memória olvasás/írás (load/store) |
| **Bemenet** | Cím az AGU-tól |
| **Kimenet** | Adat a regiszterekbe vagy a memóriába |
| **Kapcsolódik** | AGU, L1D Cache, CU, Register File |
