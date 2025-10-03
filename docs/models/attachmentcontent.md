# AttachmentContent

## Example Usage

```typescript
import { AttachmentContent } from "@egain/egain-api-typescript/models";

let value: AttachmentContent = {};
```

## Fields

| Field                                                                     | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `attachmentId`                                                            | *string*                                                                  | :heavy_minus_sign:                                                        | The ID of the attachment.                                                 |
| `name`                                                                    | *string*                                                                  | :heavy_minus_sign:                                                        | The name of the attachment.                                               |
| `size`                                                                    | *number*                                                                  | :heavy_minus_sign:                                                        | The size of the attachment in bytes. The maximum size is limited to 25MB. |
| `type`                                                                    | [models.AttachmentContentType](../models/attachmentcontenttype.md)        | :heavy_minus_sign:                                                        | The type of attachment.                                                   |
| `attachmentContentType`                                                   | *string*                                                                  | :heavy_minus_sign:                                                        | The type of the content.                                                  |
| `streamingUrl`                                                            | *string*                                                                  | :heavy_minus_sign:                                                        | The streaming URL of the attachment.                                      |
| `link`                                                                    | [models.Link](../models/link.md)                                          | :heavy_minus_sign:                                                        | Defines the relationship between this resource and another object.        |