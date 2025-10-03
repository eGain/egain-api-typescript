# AttachmentForCreateSuggestion

This schema contains the definition of an Attachment.

## Example Usage

```typescript
import { AttachmentForCreateSuggestion } from "@egain/egain-api-typescript/models";

let value: AttachmentForCreateSuggestion = {};
```

## Fields

| Field                                                                                                                                                                                                                 | Type                                                                                                                                                                                                                  | Required                                                                                                                                                                                                              | Description                                                                                                                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `altId`                                                                                                                                                                                                               | *string*                                                                                                                                                                                                              | :heavy_minus_sign:                                                                                                                                                                                                    | The alternate Id of the Attachment that was obtained after calling **[Generate signed URL to upload an attachment](https://apidev.egain.com/api-catalog/core-filemgr/api-bundled/operation/generatePreUploadURL/)**.<br/> |