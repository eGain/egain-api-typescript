# Role

## Example Usage

```typescript
import { Role } from "@egain/egain-api-typescript/models";

let value: Role = {
  id: "<id>",
  name: "<value>",
  template: {
    value: "<value>",
    displayValue: "<value>",
  },
};
```

## Fields

| Field                                            | Type                                             | Required                                         | Description                                      |
| ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------ |
| `id`                                             | *string*                                         | :heavy_check_mark:                               | ID of the object                                 |
| `name`                                           | *string*                                         | :heavy_check_mark:                               | Name of the object                               |
| `template`                                       | [models.RoleTemplate](../models/roletemplate.md) | :heavy_check_mark:                               | Role template                                    |