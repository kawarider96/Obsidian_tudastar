# Microservices pattern

A rendszer sok apró, független szolgáltatásból áll, amelyek külön fejleszthetők, deployolhatók és skálázhatók.

## Mikor használd?

- Ha komplex, nagy rendszert építesz
- Ha külön fejlesztőcsapatok dolgoznak külön modulokon

## Előnyök

- Független fejleszthetőség
- Technológiai diverzitás (minden szolgáltatás más stack lehet)

## Hátrányok

- Komplex deployment
- Inter-service kommunikáció nehézkes (pl. hibakezelés)
