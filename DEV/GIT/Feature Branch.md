# Feature Branch

Az új funkciókat külön `feature/ticket_number-xyz` ágban fejlesztjük.

## Jellemzők

- A `develop` ágból ágazik le
- Egy konkrét feladatot/funkciót fed le
- Miután kész, PR (Pull Request) készül vissza `develop`-ba

## Példa

```
git checkout develop
git checkout -b feature/CU-1234-export-pdf
```