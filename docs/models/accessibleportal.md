# AccessiblePortal

## Example Usage

```typescript
import { AccessiblePortal } from "@egain/egain-api-typescript/models";

let value: AccessiblePortal = {
  department: {
    id: "1000001035",
  },
};
```

## Fields

| Field                                                                                                 | Type                                                                                                  | Required                                                                                              | Description                                                                                           |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| `id`                                                                                                  | *string*                                                                                              | :heavy_minus_sign:                                                                                    | ID of portal. <br>A Portal ID is composed of a 2-4 letter prefix, followed by a dash and 4-15 digits. |
| `name`                                                                                                | *string*                                                                                              | :heavy_minus_sign:                                                                                    | Name of portal                                                                                        |
| `description`                                                                                         | *string*                                                                                              | :heavy_minus_sign:                                                                                    | Description of portal                                                                                 |
| `department`                                                                                          | [models.Department](../models/department.md)                                                          | :heavy_minus_sign:                                                                                    | N/A                                                                                                   |
| `shortURL`                                                                                            | [models.ShortURL](../models/shorturl.md)[]                                                            | :heavy_minus_sign:                                                                                    | N/A                                                                                                   |