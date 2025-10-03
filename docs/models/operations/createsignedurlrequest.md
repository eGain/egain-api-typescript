# CreateSignedURLRequest

## Example Usage

```typescript
import { CreateSignedURLRequest } from "@egain/egain-api-typescript/models/operations";

let value: CreateSignedURLRequest = {
  acceptLanguage: "en-US",
  attachmentUpload: {
    name: "<value>",
    size: 416743,
  },
};
```

## Fields

| Field                                                                                                                           | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     | Example                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `acceptLanguage`                                                                                                                | [models.AcceptLanguage](../../models/acceptlanguage.md)                                                                         | :heavy_check_mark:                                                                                                              | The Language locale accepted by the client (used for locale specific fields in resource representation and in error responses). | en-US                                                                                                                           |
| `attachmentUpload`                                                                                                              | [models.AttachmentUpload](../../models/attachmentupload.md)                                                                     | :heavy_check_mark:                                                                                                              | N/A                                                                                                                             |                                                                                                                                 |