# Chain of Responsibility pattern

Egymás után fűzött objektumok, amelyek eldöntik, hogy kezelik-e a kérést.

## Mikor használd?

- Ha több handler van, de nem tudod előre, melyik kezeli majd a kérést.

## Példa

```python
class Handler:
    def __init__(self, next_handler=None):
        self.next = next_handler

    def handle(self, req):
        if self.next:
            return self.next.handle(req)

class AuthHandler(Handler):
    def handle(self, req):
        if req == "auth":
            return "Auth OK"
        return super().handle(req)
```

## Előnyök

- Rugalmas
- Handler logika szétválasztható

## Hátrányok

- Nehéz debugolni
