# Filters

## Example Usage

```typescript
import { Filters } from "@egain/egain-api-typescript/models";

let value: Filters = {
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

| Field                                                                                      | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `tagCategory`                                                                              | [models.TagCategory](../models/tagcategory.md)[]                                           | :heavy_minus_sign:                                                                         | An array of tag categories. Note that the total number of tag categories cannot exceed 20. |