# RSI – Source Index Register

A **RSI** (Source Index) a forrásmutató regiszter tömb- vagy karakterlánc műveleteknél.

---

## 🧠 Fő szerepe
- String műveleteknél a **forrás** címe (`MOVS`, `LODS`).  
- Paraméterátadás: Windows x64 alatt az 1. argumentum.  
- Címzéshez és adatmozgatáshoz is használható.

---

## ⚙️ Példák
```asm
mov rsi, array
mov rdi, buffer
rep movsb     ; másolja az array-t bufferbe
```

---

## 📎 Összefoglalás
| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Source Index |
| **Fő szerep** | Forrás cím (string és tömbműveletek) |
| **Szélesség** | 64 bit |
| **Részei** | ESI, SI, SIL |
| **Kapcsolódik** | AGU, LSU, CU |
