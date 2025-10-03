# QuickpickResults

Success

## Example Usage

```typescript
import { QuickpickResults } from "@egain/egain-api-typescript/models";

let value: QuickpickResults = {
  quickpick: [
    {
      casebaseReleaseId: "409601000000001",
    },
  ],
};
```

## Fields

| Field                                                    | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `quickpick`                                              | [models.QuickpickResult](../models/quickpickresult.md)[] | :heavy_minus_sign:                                       | quick picks                                              |
| `paginationInfo`                                         | [models.PaginationInfo](../models/paginationinfo.md)     | :heavy_minus_sign:                                       | N/A                                                      |