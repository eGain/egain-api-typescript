# DynamicSearch

## Example Usage

```typescript
import { DynamicSearch } from "@egain/egain-api-typescript/models";

let value: DynamicSearch = {
  parentClusterId: "1000001035",
  virtualCase: [
    {
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
    },
  ],
};
```

## Fields

| Field                                                  | Type                                                   | Required                                               | Description                                            | Example                                                |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| `dynamicCluster`                                       | [models.DynamicCluster](../models/dynamiccluster.md)[] | :heavy_minus_sign:                                     | clusters in search                                     |                                                        |
| `parentClusterId`                                      | *string*                                               | :heavy_minus_sign:                                     | Parent cluster                                         | 1000001035                                             |
| `type`                                                 | *string*                                               | :heavy_minus_sign:                                     | type of search                                         |                                                        |
| `virtualCase`                                          | [models.VirtualCase](../models/virtualcase.md)[]       | :heavy_minus_sign:                                     | cases in search                                        |                                                        |