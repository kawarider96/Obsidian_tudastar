# L1 Instruction Cache (L1I)

**Méret:** 32–64 KB  
**Cache line méret:** 64 bájt  
> Az L1I cache az **utasításokat (gépi kódokat)** tárolja, amelyeket a CPU végrehajt.

**Hozzáférési idő:** 1–4 CPU ciklus  
**Hozzáférés típusa:** minden maghoz **külön privát L1I cache** tartozik

---

## Feladata
Az **L1 Instruction Cache (L1I)** tárolja azokat az **utasításokat**, amelyeket az adott mag végrehajtani készül.  
Amikor a program fut, az utasításokat a RAM-ból az L1I cache-be tölti a CPU, hogy gyorsabban elérje őket.

---

## Példák
- Egy függvény gépi kódja (pl. `main()`) az L1I-ben lehet.  
- Ciklusokban ismétlődő utasításokat a CPU itt tárolja a gyorsabb elérés érdekében.  
- Branch prediction (elágazásbecslés) során a valószínűleg végrehajtandó kódblokkokat is az L1I-be tölti elő.

---

## Kapcsolata az L1D-vel
- Az **L1I** az **utasításokat**, az **L1D** az **adatokat** tartalmazza.  
- Mindkettő **privát cache** minden mag számára.  
- Az L1I és L1D együtt alkotja az adott mag **L1 cache szintjét**.

---

## Összefoglalás

| Szint | Tartalom | Méret | Hozzáférési idő | Privát / Osztott |
|-------|-----------|--------|------------------|------------------|
| **L1I** | Utasítások | 32–64 KB | 1–4 ciklus | Privát |
| **L1D** | Adatok | 32–64 KB | 1–4 ciklus | Privát |
