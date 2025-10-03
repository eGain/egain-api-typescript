# ArticleType

The type of the Article and its attributes.

## Example Usage

```typescript
import { ArticleType } from "@egain/egain-api-typescript/models";

let value: ArticleType = {
  articleTypeId: "932100000002020",
};
```

## Fields

| Field                                                               | Type                                                                | Required                                                            | Description                                                         | Example                                                             |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `articleCategoryId`                                                 | *number*                                                            | :heavy_minus_sign:                                                  | Specifies the article category ID.                                  |                                                                     |
| `typeName`                                                          | [models.ArticleTypeTypeName](../models/articletypetypename.md)      | :heavy_minus_sign:                                                  | Indicates the article category name.                                |                                                                     |
| `useStructuredAuthoring`                                            | *boolean*                                                           | :heavy_minus_sign:                                                  | Indicates whether to use Structured Authoring for the Article Type. |                                                                     |
| `articleTypeId`                                                     | *string*                                                            | :heavy_minus_sign:                                                  | The ID of the Article Type.                                         | 932100000002020                                                     |