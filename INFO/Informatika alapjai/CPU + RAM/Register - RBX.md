# RBX – Base Register

A **RBX** egy általános célú regiszter, amit gyakran **báziscím tárolására** használnak.  
Nevének eredete: **BX = Base Index**.

---

## 🧠 Fő szerepe
- Címzéshez és adatok tárolásához használható.  
- Egyes hívási konvenciókban **megőrzendő regiszter** (callee-saved).

---

## ⚙️ Példák
```asm
mov rbx, array
mov rax, [rbx+8]    ; betölti a 8. bájtot az array-ből
```

---

## 📎 Összefoglalás
| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Base Register |
| **Fő szerep** | Báziscím / adatregiszter |
| **Szélesség** | 64 bit |
| **Részei** | EBX, BX, BH/BL |
| **Kapcsolódik** | AGU, LSU, CU |
