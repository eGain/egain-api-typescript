# ArticleAttachment

## Example Usage

```typescript
import { ArticleAttachment } from "@egain/egain-api-typescript/models";

let value: ArticleAttachment = {
  id: "PROD-1001",
};
```

## Fields

| Field                                                                     | Type                                                                      | Required                                                                  | Description                                                               | Example                                                                   |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `id`                                                                      | *string*                                                                  | :heavy_minus_sign:                                                        | The ID of the attachment.                                                 | PROD-1001                                                                 |
| `name`                                                                    | *string*                                                                  | :heavy_minus_sign:                                                        | The name of the attachment.                                               |                                                                           |
| `size`                                                                    | *number*                                                                  | :heavy_minus_sign:                                                        | The size of the attachment in bytes. The maximum size is limited to 25MB. |                                                                           |
| `type`                                                                    | [models.ArticleAttachmentType](../models/articleattachmenttype.md)        | :heavy_minus_sign:                                                        | The type of attachment.                                                   |                                                                           |
| `link`                                                                    | [models.Link](../models/link.md)                                          | :heavy_minus_sign:                                                        | Defines the relationship between this resource and another object.        |                                                                           |