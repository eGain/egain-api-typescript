# ArticleTypeAttributes

The type of the Article and its attributes.

## Example Usage

```typescript
import { ArticleTypeAttributes } from "@egain/egain-api-typescript/models";

let value: ArticleTypeAttributes = {
  typeName: "General",
  articleTypeId: 243500000023393,
};
```

## Fields

| Field                                | Type                                 | Required                             | Description                          | Example                              |
| ------------------------------------ | ------------------------------------ | ------------------------------------ | ------------------------------------ | ------------------------------------ |
| `typeName`                           | *string*                             | :heavy_minus_sign:                   | Indicates the article category name. | General                              |
| `articleTypeId`                      | *any*                                | :heavy_minus_sign:                   | The ID of the Article Type.          | 243500000023393                      |