# Dinamikus programozás (Dynamic Programming, DP)

A dinamikus programozás olyan módszer, amely **részproblémák megoldását újrahasznosítja**, hogy elkerülje az ismételt számításokat.

---

## 📌 Mikor használd?

- Ha a probléma **átfedő részproblémákra** bontható
- Ha van **optimális részprobléma tulajdonság** (optimalizálható darabokból)

---

## 🧠 Két fő megközelítés

### 1. Top-down (memoization)

Rekurzív megoldás, ami elmenti az eredményeket.

```python
def fib(n, memo={}):
    if n in memo:
        return memo[n]
    if n <= 2:
        return 1
    memo[n] = fib(n-1, memo) + fib(n-2, memo)
    return memo[n]
```

### 2. Bottom-up (táblázatos)

Iteratív, táblázatos megoldás – gyorsabb, kevesebb memória.

```python
def fib(n):
    if n <= 2:
        return 1
    dp = [0, 1, 1]
    for i in range(3, n+1):
        dp.append(dp[i-1] + dp[i-2])
    return dp[n]
```

---

## 🎯 Klasszikus DP feladatok

| Probléma              | Leírás                                      |
|------------------------|---------------------------------------------|
| Fibonacci számok       | Egyszerű példa                              |
| Knapsack probléma      | Maximális érték súlykorlát mellett          |
| Longest Common Subsequence (LCS) | Két sztring közös részlete          |
| Coin Change            | Minimum pénzérmék száma adott összegre      |
| Matrix Chain Multiplication | Szorzási sorrend optimalizálása     |

---

## 💡 Tippek

- Gondold végig: hogyan bontható kisebb problémákra?
- Top-down: könnyebb kódolni, de lassabb lehet
- Bottom-up: gyorsabb, de nehezebb átlátni

---

## ⚠️ Figyelem

- Mindig szükség van **alapesetre**
- DP ≠ minden optimalizáció – csak ha van ismétlődés a részmegoldásokban

