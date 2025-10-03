# QuickpickResult

## Example Usage

```typescript
import { QuickpickResult } from "@egain/egain-api-typescript/models";

let value: QuickpickResult = {
  casebaseReleaseId: "409601000000001",
};
```

## Fields

| Field                                     | Type                                      | Required                                  | Description                               | Example                                   |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| `id`                                      | *string*                                  | :heavy_minus_sign:                        | The ID of the Quickpick being accessed.<br/> |                                           |
| `name`                                    | *string*                                  | :heavy_minus_sign:                        | name of the quick pick                    |                                           |
| `comment`                                 | *string*                                  | :heavy_minus_sign:                        | comment about quick pick                  |                                           |
| `casebaseReleaseId`                       | *string*                                  | :heavy_minus_sign:                        | The numerical ID of the Casebase Release. | 409601000000001                           |