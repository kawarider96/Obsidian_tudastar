# FPU – Floating Point Unit (Lebegőpontos egység)

Az **FPU (Floating Point Unit)** a CPU azon része, amely **lebegőpontos (valós szám) műveleteket** hajt végre.
Ezek a műveletek sokkal bonyolultabbak, mint az egész számokon végzettek, ezért külön egység kezeli őket.

---

## 🧮 Fő feladatai

| Művelet | Példa | Leírás |
|----------|--------|--------|
| **Összeadás / kivonás** | `ADDSS`, `SUBSD` | Valós számok aritmetikája |
| **Szorzás / osztás** | `MULSS`, `DIVSD` | Lebegőpontos számítások |
| **Négyzetgyök, trigonometria** | `SQRT`, `SIN`, `COS` | Speciális matematikai műveletek |
| **Típuskonverzió** | `CVTSI2SD`, `CVTSD2SI` | Egész ↔ lebegőpontos konverzió |

---

## 💾 Használt regiszterek

- **x87 FPU stack**: `ST0–ST7` (80 bites lebegőpontos regiszterek)
- **SSE/AVX**: `XMM0–XMM15`, `YMM0–YMM15`, `ZMM0–ZMM31` (SIMD műveletek)

---

## ⚙️ Kapcsolat más egységekkel

- A CU (Control Unit) az FPU-nak továbbítja a lebegőpontos utasításokat.  
- Az adatok a **regisztertömbből** vagy **L1D cache-ből** érkeznek.  
- Az FPU az eredményt a **lebegőpontos regiszterekbe** írja vissza.  

---

## 🧠 Összefoglalás

| Tulajdonság | Leírás |
|--------------|--------|
| **Teljes név** | Floating Point Unit |
| **Fő funkció** | Lebegőpontos műveletek végrehajtása |
| **Bemenet** | FPU / SIMD regiszterek |
| **Kimenet** | Lebegőpontos regiszter / Cache |
| **Vezérli** | CU (Control Unit) |
| **Kapcsolódik** | ALU, SIMD, Register File |
