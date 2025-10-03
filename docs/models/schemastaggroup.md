# SchemasTagGroup

## Example Usage

```typescript
import { SchemasTagGroup } from "@egain/egain-api-typescript/models";

let value: SchemasTagGroup = {
  id: "PROD-14566",
  tagGroup: [
    {
      id: "PROD-14566",
      tag: [
        {
          id: "PROD-13206",
          name: "Blue",
        },
      ],
    },
  ],
  tag: [
    {
      id: "PROD-13206",
      name: "Blue",
    },
  ],
};
```

## Fields

| Field                                                    | Type                                                     | Required                                                 | Description                                              | Example                                                  |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `id`                                                     | *string*                                                 | :heavy_minus_sign:                                       | The unique identifier for the tag group.                 | PROD-14566                                               |
| `name`                                                   | *string*                                                 | :heavy_minus_sign:                                       | Name of the tag group.                                   |                                                          |
| `tagGroup`                                               | [models.SchemasTagGroup](../models/schemastaggroup.md)[] | :heavy_minus_sign:                                       | N/A                                                      |                                                          |
| `tag`                                                    | [models.SchemasTag](../models/schemastag.md)[]           | :heavy_minus_sign:                                       | N/A                                                      |                                                          |