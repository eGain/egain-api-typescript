# ConfigurableAttribute

## Example Usage

```typescript
import { ConfigurableAttribute } from "@egain/egain-api-typescript/models";

let value: ConfigurableAttribute = {
  name: "<value>",
  mandatory: false,
  editable: true,
};
```

## Fields

| Field                                    | Type                                     | Required                                 | Description                              |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| `name`                                   | *string*                                 | :heavy_check_mark:                       | The name of the attribute.               |
| `mandatory`                              | *boolean*                                | :heavy_check_mark:                       | Indicates if the attribute is mandatory. |
| `editable`                               | *boolean*                                | :heavy_check_mark:                       | Indicates if the attribute is editable.  |