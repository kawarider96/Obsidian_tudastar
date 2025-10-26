# AGU – Address Generation Unit (Címképző egység)

Az **AGU (Address Generation Unit)** a CPU-ban a **memóriacímek kiszámításáért** felelős.
Amikor egy utasítás memóriát érint (pl. `MOV`, `LOAD`, `STORE`), az AGU számolja ki a pontos fizikai címet.

---

## 🧮 Feladata

A címzés formátuma általában:
```
Cím = Base + (Index × Scale) + Offset
```

Példa:
```asm
MOV RAX, [RBX + RCX*4 + 8]
```
➡️ Itt az **AGU** kiszámítja: `Cím = RBX + (RCX × 4) + 8`

---

## ⚙️ Működés

- A CU utasításából az AGU megkapja a címzési módot.  
- A **base**, **index** és **offset** regiszterek értékeiből kiszámítja a memória címet.  
- Az eredményt átadja a **Load/Store Unitnak (LSU)**, amely végrehajtja a tényleges memóriaműveletet.

---

## 🧠 Összefoglalás

| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Address Generation Unit |
| **Fő funkció** | Memóriacímek kiszámítása |
| **Bemenet** | Base, Index, Offset regiszterek |
| **Kimenet** | Cím a memóriaművelethez |
| **Kapcsolódik** | CU, LSU, L1D Cache |
