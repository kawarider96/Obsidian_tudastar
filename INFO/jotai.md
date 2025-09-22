| Cél                 | Hook / API                    | Mikor használd                |
| ------------------- | ----------------------------- | ----------------------------- |
| Olvasás + írás      | `useAtom(atom)`               | 90%-ban ezt                   |
| Csak olvasás        | `useAtomValue(atom)`          | ha nem módosítasz             |
| Csak írás           | `useSetAtom(atom)`            | pl. gomb vagy form            |
| Nem React kódból    | `getDefaultStore().get(atom)` | API wrapper, config fájl      |
| Async atom olvasása | `store.asyncGet(atom)`        | async derived vagy fetch atom |
| Atom mező figyelése | `selectAtom + useAtomValue`   | optimalizált mező figyelés    |

1. Alap: `useAtom` (olvasás + írás)
```jsx
import { useAtom } from 'jotai';
import { userAtom } from '@/store/userAtom';

const [user, setUser] = useAtom(userAtom);
```
- `user`: az aktuális érték
- `setUser`: setter függvény

2. Csak olvasás: `useAtomValue`
```jsx
import { useAtomValue } from 'jotai';

const user = useAtomValue(userAtom);
```
A **leggyorsabb és legtisztább** módszer, ha **csak olvasod az értéket**.

3. Csak írás: `useSetAtom`
```jsx
import { useSetAtom } from 'jotai';

const setUser = useSetAtom(userAtom);
```

4. Külső lekérés: `getDefaultStore()` + `store.get(atom)`
```jsx
import { getDefaultStore } from 'jotai';
import { userAtom } from '@/store/userAtom';

const store = getDefaultStore();
const user = store.get(userAtom); // nem React komponensből is működik
```
Használható pl. API wrapper vagy middleware fájlban, ahol nincs React komponens.

5. Async vagy derived atom esetén: `await store.asyncGet(atom)`
```jsx
const user = await store.asyncGet(userAtom); // async atomnál!
```

6. Select atom értéke: `selectAtom` (ha atom objektum, de csak egy mezőt akarsz figyelni)
```jsx
import { selectAtom } from 'jotai/utils';
const emailAtom = selectAtom(userAtom, user => user?.email);
const email = useAtomValue(emailAtom);
```
Optimalizált újrarenderelés, csak az `email` mező változására frissít.

példa mutation TanStackQuery-re
```jsx
import { Configuration, OrganizationsApi } from "@/api/generated";
import { useMutation, useQueryClient } from "@tanstack/react-query";
import { useAtomValue } from "jotai";
import { tokenAtom } from "@/state";
import type { Organization } from "@/api/generated";

export const useEditOrganization = () => {

  const token = useAtomValue(tokenAtom);
  const queryClient = useQueryClient();

  const config = new Configuration({
    accessToken: () => token ?? sessionStorage.getItem('token') ?? '',
    basePath: import.meta.env.VITE_API_URL,
  });

  const api = new OrganizationsApi(config);

  return useMutation({
    mutationFn: async ({ id, value }: { id: number; value: Partial<Organization> }) => {
      return api.updateOrganization(id, value).then(res => res.data);
    },
    onSuccess: () => {
      queryClient.invalidateQueries({ queryKey: ['organizations'] });
    },
  });
};
```