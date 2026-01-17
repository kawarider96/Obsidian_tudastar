# Mi az a `scratch`?

> **A `scratch` egy teljesen üres image.**  
> Nem Linux. Nem Ubuntu. Nem Alpine.  
> **Semmi. Nulla. 0 byte.**

```dockerfile
FROM scratch
```

---

Ez azt jelenti:
- nincs shell (`/bin/sh`)
- nincs libc
- nincs package manager
- nincs OS
- nincs semmi

Csak az, amit **te bemásolsz**.

---
## Mire használják a `scratch`-et?

🔥 Nagyon speciális esetekre

Például:
- statikusan fordított Go bináris
- ultra-minimal microservice
- security-critical container

Példa (Go):
```dockerfile
FROM scratch
COPY myapp /
CMD ["/myapp"]
```

---

Ez az image:
- pár MB
- nincs attack surface
- brutál gyorsan indul

---
## miért „kivétel”?

Mert normálisan a Dockerfile így indul:
```dockerfile
FROM node:20-alpine
```

A Docker ezt mondja:
> „Oké, tudom mire építesz.”

De `scratch` esetén:
- **nincs mire építeni**
- te szó szerint **a nulláról** kezdesz

Ezért mondják:

> `FROM` kötelező — **kivéve scratch**,  
> mert scratch **maga a semmi**.

