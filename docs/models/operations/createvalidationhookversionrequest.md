# CreateValidationHookVersionRequest

## Example Usage

```typescript
import { CreateValidationHookVersionRequest } from "@egain/egain-api-typescript/models/operations";

let value: CreateValidationHookVersionRequest = {
  hookID: 33603,
  fileObject: {},
};
```

## Fields

| Field                                           | Type                                            | Required                                        | Description                                     |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| `hookID`                                        | *number*                                        | :heavy_check_mark:                              | Integer ID of the Hook resource.                |
| `fileObject`                                    | [models.FileObject](../../models/fileobject.md) | :heavy_check_mark:                              | N/A                                             |