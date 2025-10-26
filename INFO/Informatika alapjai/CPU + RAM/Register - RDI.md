# RDI – Destination Index Register

A **RDI** (Destination Index) a célmutató regiszter tömb- és karakterlánc műveleteknél.

---

## 🧠 Fő szerepe
- A **string műveletek célcíme** (`MOVS`, `STOS`).  
- Paraméterátadás: a 0. argumentumot tárolja Windows x64 alatt.  
- Memóriamásolás és adatmozgatás műveletekben fontos.

---

## ⚙️ Példák
```asm
mov rsi, array
mov rdi, buffer
rep movsb     ; forrás = RSI, cél = RDI
```

---

## 📎 Összefoglalás
| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Destination Index |
| **Fő szerep** | Cél cím (string műveletek) |
| **Szélesség** | 64 bit |
| **Részei** | EDI, DI, DIL |
| **Kapcsolódik** | AGU, LSU, CU |
