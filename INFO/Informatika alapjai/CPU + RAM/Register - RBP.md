# RBP – Base Pointer (Stack Frame Pointer)

A **RBP** (Base Pointer) a veremkeret (stack frame) **alapmutatója**.  
A függvények helyi változóinak és paramétereinek címzéséhez használják.

---

## 🧠 Fő szerepe
- A **stack frame** kezdőcímének tárolása.  
- A függvény belépéskor elmenti az előző RBP értéket (`PUSH RBP`).  
- Segít a lokális változók és paraméterek címzésében.

---

## ⚙️ Példák
```asm
push rbp
mov rbp, rsp
sub rsp, 32     ; hely foglalás a stacken
mov rax, [rbp+16] ; paraméter olvasása
```

---

## 📎 Összefoglalás
| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Base Pointer |
| **Fő szerep** | Stack frame báziscíme |
| **Szélesség** | 64 bit |
| **Részei** | EBP, BP, BPL |
| **Kapcsolódik** | Stack, RSP, CU |
