# EditionWithContentAccessTags

## Example Usage

```typescript
import { EditionWithContentAccessTags } from "@egain/egain-api-typescript/models";

let value: EditionWithContentAccessTags = {
  tagCategory: [
    {
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
    },
  ],
};
```

## Fields

| Field                                                                                      | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `tagCategory`                                                                              | [models.SchemasTagCategory](../models/schemastagcategory.md)[]                             | :heavy_minus_sign:                                                                         | An array of tag categories. Note that the total number of tag categories cannot exceed 20. |