# FileObject

## Example Usage

```typescript
import { FileObject } from "@egain/egain-api-typescript/models";

let value: FileObject = {};
```

## Fields

| Field                                             | Type                                              | Required                                          | Description                                       |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| `fileID`                                          | *string*                                          | :heavy_minus_sign:                                | ID of Hook File                                   |
| `createdDate`                                     | *string*                                          | :heavy_minus_sign:                                | The date on which the resource was last modified. |
| `createdBy`                                       | [models.CreatedBy](../models/createdby.md)        | :heavy_minus_sign:                                | N/A                                               |
| `modifiedDate`                                    | *string*                                          | :heavy_minus_sign:                                | The date on which the resource was last modified. |
| `modifiedBy`                                      | [models.ModifiedBy](../models/modifiedby.md)      | :heavy_minus_sign:                                | N/A                                               |
| `version`                                         | [models.Version](../models/version.md)            | :heavy_minus_sign:                                | N/A                                               |
| `file`                                            | [models.FileT](../models/filet.md)                | :heavy_minus_sign:                                | N/A                                               |