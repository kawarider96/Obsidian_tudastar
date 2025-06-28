# Fa (Tree)

A fa egy hierarchikus adatszerkezet, amely csúcsokból (node) áll, és minden csúcs pontosan egy szülőhöz kapcsolódik (a gyökér kivételével).

---

## 📌 Jellemzők

- Gyökércsúcs (root)
- Gyerekcsúcsok (children)
- Levélcsúcsok (nincs gyermekük)
- Mélység (gyökértől való távolság)

---

## 📊 Tipikus alkalmazás

- Fájl- és könyvtárszerkezetek
- Hierarchikus jogosultságok
- XML/HTML dokumentum struktúra
- AI döntési fák

---

## 🔁 Bejárások

### Inorder (bal → gyökér → jobb)

```python
def inorder(csucs):
    if csucs:
        inorder(csucs.bal)
        print(csucs.ertek)
        inorder(csucs.jobb)
```

### Preorder (gyökér → bal → jobb)  
### Postorder (bal → jobb → gyökér)

---

## 💡 További fa típusok

- Bináris fa (max. 2 gyerek)
- Bináris keresőfa (BST)
- AVL / Red-Black fa (kiegyensúlyozott fák)
