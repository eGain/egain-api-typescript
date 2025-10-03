# CasebaseResult

Success

## Example Usage

```typescript
import { CasebaseResult } from "@egain/egain-api-typescript/models";

let value: CasebaseResult = {
  casebase: [
    {
      casebaseId: "409601000000001",
    },
  ],
};
```

## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `casebase`                                           | [models.Casebase](../models/casebase.md)[]           | :heavy_minus_sign:                                   | Casebase releases                                    |
| `paginationInfo`                                     | [models.PaginationInfo](../models/paginationinfo.md) | :heavy_minus_sign:                                   | N/A                                                  |