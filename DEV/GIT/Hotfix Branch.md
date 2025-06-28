# Hotfix Branch

Gyors javítás éles hibákra `main`-ről.

## Jellemzők

- `main` ágból indul
- Bugfix után merge: `main` + `develop`
- Cél: gyors patch

## Példa

```
git checkout main
git checkout -b hotfix/CU-1234-pdf-crash-fix
```