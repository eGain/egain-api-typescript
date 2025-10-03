# AttachmentSummary

Summary attributes for an Attachment.

## Example Usage

```typescript
import { AttachmentSummary } from "@egain/egain-api-typescript/models";

let value: AttachmentSummary = {
  id: "PROD-1001",
};
```

## Fields

| Field                                                                         | Type                                                                          | Required                                                                      | Description                                                                   | Example                                                                       |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `id`                                                                          | *string*                                                                      | :heavy_minus_sign:                                                            | The ID of the Attachment.                                                     | PROD-1001                                                                     |
| `link`                                                                        | [models.Link](../models/link.md)                                              | :heavy_minus_sign:                                                            | Defines the relationship between this resource and another object.            |                                                                               |
| `fileName`                                                                    | *string*                                                                      | :heavy_minus_sign:                                                            | The name of the Attachment file.<li>This must not exceed 255 characters.</li> |                                                                               |
| `size`                                                                        | *number*                                                                      | :heavy_minus_sign:                                                            | The size of the Attachment.<li>Limited to 25MB.</li>                          |                                                                               |