# CaseListResults

Success

## Example Usage

```typescript
import { CaseListResults } from "@egain/egain-api-typescript/models";

let value: CaseListResults = {
  case: [
    {
      id: "100000000001035",
      releaseId: "100000000001035",
      clusterId: "100000000001035",
    },
  ],
};
```

## Fields

| Field                                                  | Type                                                   | Required                                               | Description                                            |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| `case`                                                 | [models.CaseListResult](../models/caselistresult.md)[] | :heavy_minus_sign:                                     | Cases                                                  |
| `paginationInfo`                                       | [models.PaginationInfo](../models/paginationinfo.md)   | :heavy_minus_sign:                                     | N/A                                                    |