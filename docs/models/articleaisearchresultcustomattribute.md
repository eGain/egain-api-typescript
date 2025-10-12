# ArticleAISearchResultCustomAttribute

## Example Usage

```typescript
import { ArticleAISearchResultCustomAttribute } from "@egain/egain-api-typescript/models";

let value: ArticleAISearchResultCustomAttribute = {
  name: "loan_id",
  value: [
    "78391",
  ],
  type: "STRING",
};
```

## Fields

| Field                                                                      | Type                                                                       | Required                                                                   | Description                                                                | Example                                                                    |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `name`                                                                     | *string*                                                                   | :heavy_minus_sign:                                                         | The custom attribute's name.                                               | loan_id                                                                    |
| `value`                                                                    | *string*[]                                                                 | :heavy_minus_sign:                                                         | The custom attribute's values.                                             | 78391                                                                      |
| `type`                                                                     | [models.ArticleAISearchResultType](../models/articleaisearchresulttype.md) | :heavy_minus_sign:                                                         | The custom attribute's type.                                               | STRING                                                                     |