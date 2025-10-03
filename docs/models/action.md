# Action

## Example Usage

```typescript
import { Action } from "@egain/egain-api-typescript/models";

let value: Action = {
  articleType: {
    articleTypeId: "932100000002020",
  },
};
```

## Fields

| Field                                          | Type                                           | Required                                       | Description                                    |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| `id`                                           | *string*                                       | :heavy_minus_sign:                             | ID of the action                               |
| `title`                                        | *string*                                       | :heavy_minus_sign:                             | Name of the action                             |
| `type`                                         | *string*                                       | :heavy_minus_sign:                             | type of the action                             |
| `shortName`                                    | *string*                                       | :heavy_minus_sign:                             | short name of the action                       |
| `rejectCount`                                  | *number*                                       | :heavy_minus_sign:                             | number of times action was rejected.           |
| `acceptCount`                                  | *number*                                       | :heavy_minus_sign:                             | number of times action was accepted.           |
| `metadata`                                     | [models.Metadata](../models/metadata.md)[]     | :heavy_minus_sign:                             | Metadata of action                             |
| `articleType`                                  | [models.ArticleType](../models/articletype.md) | :heavy_minus_sign:                             | The type of the Article and its attributes.    |