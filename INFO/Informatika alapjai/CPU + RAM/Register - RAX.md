# RAX – Accumulator Register

A **RAX** az egyik legfontosabb általános célú regiszter az x86-64 architektúrában.  
Eredetileg az **AX (Accumulator)** 16 bites elődje volt, innen a neve.

---

## 🧠 Fő szerepe
- Az **ALU fő operandusregisztere** aritmetikai műveleteknél (`ADD`, `SUB`, `MUL`, `DIV`).
- A **függvények visszatérési értéke** mindig az `RAX` regiszterbe kerül (ABI szabvány szerint).

---

## ⚙️ Példák
```asm
mov rax, 5
mov rbx, 10
add rax, rbx    ; RAX = 15
```

---

## 📎 Összefoglalás
| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Accumulator Register |
| **Fő szerep** | Aritmetikai műveletek és visszatérési érték |
| **Szélesség** | 64 bit |
| **Részei** | EAX (32 bit), AX (16 bit), AH/AL (8 bit) |
| **Kapcsolódik** | ALU, CU |
