# 🧩 Oszthatóság – Alapfogalom

Azt mondjuk, hogy egy **a** szám **osztható b-vel**, ha  
**b ∣ a ⇔ a = b ⋅ k** valamilyen egész *k*-ra.  
Ilyenkor az osztás maradéka 0.

---

## ⚙️ Klasszikus oszthatósági szabályok

### 1️⃣ 2-vel oszthatóság
Egy szám osztható 2-vel, ha **páros**, tehát az utolsó számjegye 0, 2, 4, 6 vagy 8.

**Miért?**  
Mert a tízes számrendszerben minden 10, 100, 1000… többszöröse 2-nek, így csak az utolsó jegy számít.

---

### 2️⃣ 3-mal oszthatóság
Osztható 3-mal, ha **a számjegyek összege osztható 3-mal**.  
Pl. 372 → 3 + 7 + 2 = 12 → osztható 3-mal.

**Miért?**  
Mert 10 ≡ 1 (mod 3), így minden helyiérték „úgy viselkedik”, mintha csak a számjegyek összege lenne.

---

### 3️⃣ 4-gyel oszthatóság
Ha **az utolsó két számjegy** osztható 4-gyel.  
Pl. 212 → 12 ÷ 4 = 3 → osztható.

**Miért?**  
100 ≡ 0 (mod 4), így csak az utolsó két számjegy számít.

---

### 4️⃣ 5-tel oszthatóság
Ha **0-ra vagy 5-re végződik**, akkor osztható 5-tel.

---

### 5️⃣ 6-tal oszthatóság
Ha **egyszerre osztható 2-vel és 3-mal**.

---

### 6️⃣ 8-cal oszthatóság
Ha **az utolsó három számjegy** osztható 8-cal (mert 1000 = 8 × 125).

---

### 7️⃣ 9-cel oszthatóság
Ugyanaz, mint a 3-as eset, csak 9-re:  
Ha a számjegyek összege osztható 9-cel.

---

### 8️⃣ 10-zel oszthatóság
Ha **0-ra végződik**.

---

### 9️⃣ 11-gyel oszthatóság
Ha a számjegyek **váltakozó előjelű összege** osztható 11-gyel.  
Példa: 528 → 5 − 2 + 8 = 11 → osztható 11-gyel.

**Miért?**  
Mert 10 ≡ −1 (mod 11), így minden második számjegy előjele megfordul.

---

### 🔟 25-tel oszthatóság
Utolsó két számjegy osztható 25-tel (00, 25, 50, 75).

---

## 💡 Általános trükk: maradékos gondolkodás
Minden ilyen szabály **moduláris aritmetikából** jön.  
Ha érted, hogy pl. 10 ≡ 1 (mod 3) vagy 10 ≡ −1 (mod 11), akkor bármilyen új szabályt le tudsz vezetni magadtól.
