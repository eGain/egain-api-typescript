# AttachmentUpload

## Example Usage

```typescript
import { AttachmentUpload } from "@egain/egain-api-typescript/models";

let value: AttachmentUpload = {
  name: "<value>",
  size: 485594,
};
```

## Fields

| Field                                                                     | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `name`                                                                    | *string*                                                                  | :heavy_check_mark:                                                        | The name of the attachment.                                               |
| `size`                                                                    | *number*                                                                  | :heavy_check_mark:                                                        | The size of the attachment in bytes. The maximum size is limited to 25MB. |