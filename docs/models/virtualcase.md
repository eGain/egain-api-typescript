# VirtualCase

## Example Usage

```typescript
import { VirtualCase } from "@egain/egain-api-typescript/models";

let value: VirtualCase = {
  detailField: [
    {
      id: "PROD-9312",
    },
  ],
  displayField: [
    {
      id: "PROD-9312",
    },
  ],
  dynamicClusterId: "1000001035",
};
```

## Fields

| Field                                              | Type                                               | Required                                           | Description                                        | Example                                            |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| `id`                                               | *string*                                           | :heavy_minus_sign:                                 | ID of the case                                     |                                                    |
| `detailField`                                      | [models.DetailField](../models/detailfield.md)[]   | :heavy_minus_sign:                                 | detail fields                                      |                                                    |
| `displayField`                                     | [models.DisplayField](../models/displayfield.md)[] | :heavy_minus_sign:                                 | display fields                                     |                                                    |
| `dynamicClusterId`                                 | *string*                                           | :heavy_minus_sign:                                 | Cluster id                                         | 1000001035                                         |
| `title`                                            | *string*                                           | :heavy_minus_sign:                                 | name of the case                                   |                                                    |
| `virtualCaseId`                                    | *string*                                           | :heavy_minus_sign:                                 | virtual case id                                    |                                                    |