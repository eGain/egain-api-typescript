# TagCategory

A tag category is a grouping of tags and tag groups.

## Example Usage

```typescript
import { TagCategory } from "@egain/egain-api-typescript/models";

let value: TagCategory = {
  tags: {
    tag: [
      {
        name: "Blue",
        id: "PROD-13206",
      },
    ],
  },
  tagGroups: {
    tagGroup: [
      {
        id: "PROD-14566",
      },
    ],
  },
};
```

## Fields

| Field                                                                                                               | Type                                                                                                                | Required                                                                                                            | Description                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `name`                                                                                                              | *string*                                                                                                            | :heavy_minus_sign:                                                                                                  | The name of the tag category.                                                                                       |
| `id`                                                                                                                | *string*                                                                                                            | :heavy_minus_sign:                                                                                                  | The ID of the tag category. A tag category ID is composed of a 4-letter prefix, followed by a dash and 4-15 digits. |
| `tags`                                                                                                              | [models.Tags](../models/tags.md)                                                                                    | :heavy_minus_sign:                                                                                                  | N/A                                                                                                                 |
| `tagGroups`                                                                                                         | [models.TagGroups](../models/taggroups.md)                                                                          | :heavy_minus_sign:                                                                                                  | N/A                                                                                                                 |