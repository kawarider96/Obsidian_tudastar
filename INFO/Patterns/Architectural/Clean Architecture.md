# Clean Architecture

Robert C. Martin (Uncle Bob) koncepciója, amely szerint a rendszer logikáját koncentrikus rétegek mentén szervezzük.

## Rétegek

```
Entities           → üzleti szabályok
Use Cases          → alkalmazás logika
Interface Adapters → controller, presenter
Frameworks/Drivers → UI, adatbázis, web
```

## Szabály

- A függőség **kifelé mutat**: belső réteg sosem ismerheti a külsőt
- Minden külső eszköz cserélhető (pl. DB, UI)

## Előnyök

- Nagyon jól tesztelhető
- Magas újrahasználhatóság
- Függőségek kezelhetősége kiváló

## Hátrányok

- Sok interfész és absztrakció
- Komplexitás kisebb projekteknél túlzás lehet
