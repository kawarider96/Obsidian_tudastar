# RSP – Stack Pointer

A **RSP (Stack Pointer)** mindig a **verem (stack)** tetejére mutat.  
A verem LIFO (Last In, First Out) elven működik, így a RSP-t minden `PUSH` és `POP` művelet módosítja.

---

## 🧠 Fő szerepe
- A **stack tetejének címe**.  
- A függvényhívások és visszatérések alapja (`CALL`, `RET`).  
- A `PUSH` és `POP` automatikusan növeli/csökkenti a RSP értékét.

---

## ⚙️ Példák
```asm
push rax    ; RSP -= 8
pop rbx     ; RSP += 8
call func   ; RSP -= 8 (visszatérési cím)
ret         ; RSP += 8
```

---

## 📎 Összefoglalás
| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Stack Pointer |
| **Fő szerep** | Stack tetejének címe |
| **Szélesség** | 64 bit |
| **Részei** | ESP, SP, SPL |
| **Kapcsolódik** | Stack, RBP, CU |
