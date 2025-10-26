# RDX – Data Register

A **RDX** (Data Register) az egyik fő adatregiszter az ALU számára, gyakran **második operandus** szorzásnál, osztásnál.

---

## 🧠 Fő szerepe
- Szorzás és osztás második operandusa (`MUL`, `DIV`).  
- Paraméterátadás: a 2. argumentum tárolására szolgál Windows x64 alatt.  
- Általános célú adatregiszter.

---

## ⚙️ Példák
```asm
mov rax, 5
mov rdx, 2
mul rdx          ; RAX = 10
```

---

## 📎 Összefoglalás
| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Data Register |
| **Fő szerep** | Szorzás/osztás második operandusa |
| **Szélesség** | 64 bit |
| **Részei** | EDX, DX, DH/DL |
| **Kapcsolódik** | ALU, CU |
