# CustomAttribute

## Example Usage

```typescript
import { CustomAttribute } from "@egain/egain-api-typescript/models";

let value: CustomAttribute = {};
```

## Fields

| Field                                                          | Type                                                           | Required                                                       | Description                                                    |
| -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| `name`                                                         | *string*                                                       | :heavy_minus_sign:                                             | The custom attribute's name.                                   |
| `value`                                                        | *string*[]                                                     | :heavy_minus_sign:                                             | The custom attribute's values.                                 |
| `type`                                                         | [models.CustomAttributeType](../models/customattributetype.md) | :heavy_minus_sign:                                             | The custom attribute's type.                                   |