# GetValidationHookVersionRequest

## Example Usage

```typescript
import { GetValidationHookVersionRequest } from "@egain/egain-api-typescript/models/operations";

let value: GetValidationHookVersionRequest = {
  hookID: 536452,
  versionID: 488403,
};
```

## Fields

| Field                                                      | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `hookID`                                                   | *number*                                                   | :heavy_check_mark:                                         | Integer ID of the Hook resource.                           |
| `versionID`                                                | *number*                                                   | :heavy_check_mark:                                         | The sequential version number of the hook (e.g., 1, 2, 3). |