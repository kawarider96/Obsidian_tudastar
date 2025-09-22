# Release Branch

A `release/ticket_number-x.y.z` ágakat a kiadásra kész verzió stabilizálására használjuk.

## Jellemzők

- `develop`-ból ágazik le
- Ide csak bugfix, dokumentáció, meta dolgok jönnek
- Ha kész: merge `main` + `develop` + tag

## Példa

```
git checkout develop
git checkout -b release/1.0.0
```