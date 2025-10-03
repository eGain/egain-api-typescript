# EditionWithContent

This schema contains information about article edition.

## Example Usage

```typescript
import { EditionWithContent } from "@egain/egain-api-typescript/models";

let value: EditionWithContent = {
  accessTags: {
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
  },
};
```

## Fields

| Field                                                                                | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `id`                                                                                 | *string*                                                                             | :heavy_minus_sign:                                                                   | ID of the edition.                                                                   |
| `name`                                                                               | *string*                                                                             | :heavy_minus_sign:                                                                   | Name of the edition.                                                                 |
| `publishProfile`                                                                     | [models.PublishProfile](../models/publishprofile.md)                                 | :heavy_minus_sign:                                                                   | This schema contains information about Profile.                                      |
| `content`                                                                            | *string*                                                                             | :heavy_minus_sign:                                                                   | The raw content of the article. The maximum allowed Article content size is 5 MB.    |
| `contentText`                                                                        | *string*                                                                             | :heavy_minus_sign:                                                                   | Plain text version of the content. The maximum allowed Article content size is 5 MB. |
| `accessTags`                                                                         | [models.EditionWithContentAccessTags](../models/editionwithcontentaccesstags.md)     | :heavy_minus_sign:                                                                   | N/A                                                                                  |
| `link`                                                                               | [models.Link](../models/link.md)                                                     | :heavy_minus_sign:                                                                   | Defines the relationship between this resource and another object.                   |