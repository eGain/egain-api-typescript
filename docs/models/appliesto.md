# AppliesTo

The 'channel' for this prompt. If the `useFor` is set to 'knowledge' then article is used. If `useFor` is set to 'advisor', then either 'chat' or 'email' can be used.

## Example Usage

```typescript
import { AppliesTo } from "@egain/egain-api-typescript/models";

let value: AppliesTo = "email";
```

## Values

```typescript
"article" | "chat" | "email"
```