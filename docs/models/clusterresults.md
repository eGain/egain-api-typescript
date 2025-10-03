# ClusterResults

Success

## Example Usage

```typescript
import { ClusterResults } from "@egain/egain-api-typescript/models";

let value: ClusterResults = {
  cluster: [
    {
      id: "1000000257",
    },
  ],
};
```

## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `cluster`                                            | [models.ClusterResult](../models/clusterresult.md)[] | :heavy_minus_sign:                                   | Clusters                                             |
| `paginationInfo`                                     | [models.PaginationInfo](../models/paginationinfo.md) | :heavy_minus_sign:                                   | N/A                                                  |