# PortalResult

Success

## Example Usage

```typescript
import { PortalResult } from "@egain/egain-api-typescript/models";

let value: PortalResult = {
  portal: [
    {
      id: "<id>",
      name: "<value>",
      departmentId: "1000001035",
      defaultContentLanguageId: "1",
    },
  ],
};
```

## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `portal`                                             | [models.Portal](../models/portal.md)[]               | :heavy_minus_sign:                                   | portals                                              |
| `paginationInfo`                                     | [models.PaginationInfo](../models/paginationinfo.md) | :heavy_minus_sign:                                   | N/A                                                  |