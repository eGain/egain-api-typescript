# CreateQuickpick

## Example Usage

```typescript
import { CreateQuickpick } from "@egain/egain-api-typescript/models";

let value: CreateQuickpick = {
  casebaseReleaseId: "409601000000001",
};
```

## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          | Example                                              |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `name`                                               | *string*                                             | :heavy_minus_sign:                                   | name of the quick pick                               |                                                      |
| `comment`                                            | *string*                                             | :heavy_minus_sign:                                   | comment about quick pick                             |                                                      |
| `casebaseReleaseId`                                  | *string*                                             | :heavy_check_mark:                                   | The numerical ID of Live release of the Casebase.    | 409601000000001                                      |
| `linkToActivity`                                     | *boolean*                                            | :heavy_minus_sign:                                   | indicates if quickpick is to be linked with activity |                                                      |