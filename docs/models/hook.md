# Hook

## Example Usage

```typescript
import { Hook } from "@egain/egain-api-typescript/models";

let value: Hook = {
  type: "import_post_validation_hook",
  fileObject: {},
};
```

## Fields

| Field                                        | Type                                         | Required                                     | Description                                  |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| `hookID`                                     | *number*                                     | :heavy_minus_sign:                           | ID of hook                                   |
| `name`                                       | *string*                                     | :heavy_minus_sign:                           | Name of the hook.                            |
| `type`                                       | [models.HookType](../models/hooktype.md)     | :heavy_check_mark:                           | N/A                                          |
| `fileObject`                                 | [models.FileObject](../models/fileobject.md) | :heavy_check_mark:                           | N/A                                          |