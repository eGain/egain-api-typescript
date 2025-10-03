# ArticleActivityLink

## Example Usage

```typescript
import { ArticleActivityLink } from "@egain/egain-api-typescript/models";

let value: ArticleActivityLink = {
  versionId: "PROD-12416",
  editionId: "PROD-13015",
  language: {
    code: "en-US",
  },
};
```

## Fields

| Field                                                                          | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `versionId`                                                                    | *string*                                                                       | :heavy_check_mark:                                                             | An Article version's ID.                                                       |
| `editionId`                                                                    | *string*                                                                       | :heavy_minus_sign:                                                             | An Article edition's ID.                                                       |
| `language`                                                                     | [models.ArticleActivityLinkLanguage](../models/articleactivitylinklanguage.md) | :heavy_check_mark:                                                             | The knowledge base language in which the version is created.                   |