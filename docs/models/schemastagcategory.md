# SchemasTagCategory

## Example Usage

```typescript
import { SchemasTagCategory } from "@egain/egain-api-typescript/models";

let value: SchemasTagCategory = {
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

| Field                                                                  | Type                                                                   | Required                                                               | Description                                                            |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `name`                                                                 | *string*                                                               | :heavy_minus_sign:                                                     | name of the tag category.                                              |
| `tagGroup`                                                             | [models.SchemasTagGroup](../models/schemastaggroup.md)[]               | :heavy_minus_sign:                                                     | N/A                                                                    |
| `tag`                                                                  | [models.SchemasTag](../models/schemastag.md)[]                         | :heavy_minus_sign:                                                     | N/A                                                                    |
| `created`                                                              | [models.CreatedDateAndTime](../models/createddateandtime.md)           | :heavy_minus_sign:                                                     | Date the Tag Category was created.                                     |
| `lastModified`                                                         | [models.LastModifiedDateAndTime](../models/lastmodifieddateandtime.md) | :heavy_minus_sign:                                                     | Date of last modification.                                             |