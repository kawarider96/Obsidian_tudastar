# Git Flow Ábra

A Git Flow egy jól bevált ágazási modell, amit főleg közepes és nagyobb fejlesztési csapatok használnak. Az alábbi szöveges leírás bemutatja, hogyan néz ki ez a modell.

## 🌳 Főbb ágak:

- **main**: az éles, kiadott kód található itt. Csak stabil, tesztelt kód kerülhet ide.
- **develop**: aktív fejlesztési ág, ide kerülnek a feature branch-ek merge után.

## 🌿 Ágak típusai és szerepük:

### 1. `feature/*`
- Fejlesztők ezen dolgoznak új funkciókon
- Kiindulás: `develop`
- Cél: `develop`
- Példa: `feature/CU-1234-export-pdf`

### 2. `release/*`
- Kiadás előtt stabilizálásra szolgál
- Kiindulás: `develop`
- Cél: `main` + visszamerge `develop`-be
- Példa: `release/1.2.0`

### 3. `hotfix/*`
- Éles hibák gyors javítására
- Kiindulás: `main`
- Cél: `main` + visszamerge `develop`-be
- Példa: `hotfix/CU-1234-fix-login-bug`

## 🔁 Tipikus workflow:

1. **Új fejlesztés**:
   - `git checkout develop`
   - `git checkout -b feature/CU-1234-login-form`

2. **Kész fejlesztés merge**:
   - PR vagy merge `feature/CU-1234-login-form` → `develop`

3. **Kiadás előkészítése**:
   - `git checkout develop`
   - `git checkout -b release/1.0.0`
   - Bugfixek, meta dolgok

4. **Kiadás**:
   - Merge `release/1.0.0` → `main`
   - Merge `release/1.0.0` → `develop`
   - `git tag 1.0.0`

5. **Hotfix**:
   - `git checkout main`
   - `git checkout -b hotfix/CU-1234-fix-bug`
   - Javítás
   - Merge `hotfix` → `main` + `develop`