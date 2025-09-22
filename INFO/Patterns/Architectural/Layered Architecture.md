# Layered Architecture

A rendszer logikáját rétegekre bontja (pl. presentation, service, persistence), ahol minden réteg csak a közvetlen alatta lévővel kommunikál.

## Mikor használd?

- Ha jól elválasztott felelősségi köröket akarsz.
- Ha egyszerű, strukturált rendszert építesz.

## Tipikus rétegek

1. Presentation (UI)
2. Application / Service
3. Domain / Business Logic
4. Persistence / Infrastructure

## Előnyök

- Könnyen karbantartható
- Jó újrahasznosíthatóság

## Hátrányok

- Sok réteg → lassabb válaszidő
- Túl merev lehet dinamikus igényekhez
