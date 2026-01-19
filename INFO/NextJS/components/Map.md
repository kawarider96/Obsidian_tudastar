---
title: map
tags:
  - frontend
  - nextjs
  - react
  - library
  - programming
  - programozás
  - javascript
  - map
status: complete
created: 2026-01-17
---
Tömb mapolása tsx-ben

```tsx
export default function Page() {
  const fruits = ["alma", "banán", "körte"];

  return (
    <div>
      {fruits.map((fruit) => (
        <p key={fruit}>{fruit}</p>
      ))}
    </div>
  );
}
```