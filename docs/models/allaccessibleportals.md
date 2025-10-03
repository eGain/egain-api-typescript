# AllAccessiblePortals

Success

## Example Usage

```typescript
import { AllAccessiblePortals } from "@egain/egain-api-typescript/models";

let value: AllAccessiblePortals = {
  portal: [
    {
      department: {
        id: "1000001035",
      },
    },
  ],
};
```

## Fields

| Field                                                      | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `portal`                                                   | [models.AccessiblePortal](../models/accessibleportal.md)[] | :heavy_minus_sign:                                         | portals                                                    |
| `paginationInfo`                                           | [models.PaginationInfo](../models/paginationinfo.md)       | :heavy_minus_sign:                                         | N/A                                                        |