# PublishView

## Example Usage

```typescript
import { PublishView } from "@egain/egain-api-typescript/models";

let value: PublishView = {
  id: "PROD-12446",
  tagCategories: [
    {
      tagCategory: [
        {
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
        },
      ],
    },
  ],
};
```

## Fields

| Field                                                                                                                               | Type                                                                                                                                | Required                                                                                                                            | Description                                                                                                                         | Example                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| `name`                                                                                                                              | *string*                                                                                                                            | :heavy_minus_sign:                                                                                                                  | name of the publish view                                                                                                            |                                                                                                                                     |
| `id`                                                                                                                                | *string*                                                                                                                            | :heavy_minus_sign:                                                                                                                  | N/A                                                                                                                                 | PROD-12446                                                                                                                          |
| `tagCategories`                                                                                                                     | [models.PublishViewTagCategory](../models/publishviewtagcategory.md)[]                                                              | :heavy_minus_sign:                                                                                                                  | Tag categories are comprised of both tags and tag groups.<br><br>Note that the total number of tag and tag groups cannot exceed 20. |                                                                                                                                     |