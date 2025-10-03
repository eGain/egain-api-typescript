# PublishViewTagCategory

## Example Usage

```typescript
import { PublishViewTagCategory } from "@egain/egain-api-typescript/models";

let value: PublishViewTagCategory = {
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
};
```

## Fields

| Field                                            | Type                                             | Required                                         | Description                                      |
| ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ |
| `tagCategory`                                    | [models.TagCategory](../models/tagcategory.md)[] | :heavy_minus_sign:                               | N/A                                              |