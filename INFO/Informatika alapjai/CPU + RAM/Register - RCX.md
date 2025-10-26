# RCX – Counter Register

A **RCX** (Count Register) tipikusan **számlálóként** használatos ciklusokban és ismétlő műveletekben.

---

## 🧠 Fő szerepe
- Ciklusvezérlés: `LOOP`, `REP MOVS` stb.  
- Paraméterátadás: a 4. argumentumot tárolja Windows x64 hívási konvencióban.  
- Aritmetikai műveleteknél általános operandus.

---

## ⚙️ Példák
```asm
mov rcx, 10
loop_start:
    dec rcx
    jnz loop_start
```

---

## 📎 Összefoglalás
| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Counter Register |
| **Fő szerep** | Számláló, ciklusvezérlés |
| **Szélesség** | 64 bit |
| **Részei** | ECX, CX, CH/CL |
| **Kapcsolódik** | CU, ALU |
